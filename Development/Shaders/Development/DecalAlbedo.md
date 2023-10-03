---
title: Game shaders - albedo decal
description: Describes all technical details related to the albedo decal
published: true
date: 2023-10-03T09:12:34.355Z
tags: mapping, shaders, decal, decals
editor: markdown
dateCreated: 2023-10-03T09:12:34.355Z
---

# Game shaders - albedo decal

The albedo decal is relies on the `TDecals` and `TDecalsXP` techniques. You can find the latest version of these techniques by searching through [terrain.fx](https://github.com/FAForever/fa/blob/deploy/fafdevelop/effects/terrain.fx). For convenience we'll copy the details as of writing into this wiki article at the end as a reference.

<todo></todo>

## Code snippets

```hlsl
// This snippet may be outdated, find the latest at https://github.com/FAForever/fa/blob/deploy/fafdevelop/effects/terrain.fx

technique TDecals
{
    pass P0
    {
        AlphaState( AlphaBlend_SrcAlpha_InvSrcAlpha_Write_RGB )
        DepthState( Depth_Enable_LessEqual_Write_None )
        RasterizerState( Rasterizer_Bias_Decal )

        VertexShader = compile vs_2_0 DecalsVS( true );
        PixelShader = compile ps_2_a DecalsPS( true);
    }
}

// (...)

float4 DecalsPS( VS_OUTPUT inV, uniform bool inShadows) : COLOR
{
    // sample all the textures we'll need
    float4 decalAlbedo = tex2Dproj(DecalAlbedoSampler, inV.mTexDecal);
    float4 decalSpec = tex2Dproj(DecalSpecSampler, inV.mTexDecal);
    float4 decalMask = tex2Dproj(DecalMaskSampler, inV.mTexDecal).xxxx;
    float3 normal = SampleScreen(NormalSampler, inV.mTexSS).xyz * 2 -1;

    float waterDepth = tex2Dproj(UtilitySamplerC, inV.mTexWT * TerrainScale).g;

    float3 color = CalculateLighting(normal, inV.mTexWT.xyz, decalAlbedo.xyz, decalSpec.r, waterDepth, inV.mShadow, inShadows).xyz;

    return float4(color.rgb, decalAlbedo.w * decalMask.w * DecalAlpha);
}
```

```hlsl
// This snippet may be outdated, find the latest at https://github.com/FAForever/fa/blob/deploy/fafdevelop/effects/terrain.fx

technique TDecalsXP
{
    pass P0
    {
        AlphaState(AlphaBlend_SrcAlpha_InvSrcAlpha_Write_RGB)
        DepthState(Depth_Enable_LessEqual_Write_None)
        RasterizerState(Rasterizer_Bias_Decal)

        VertexShader = compile vs_2_0 DecalsVS(true);
        PixelShader = compile ps_2_0 DecalAlbedoXP(true);
    }
}

// (...)

float4 DecalAlbedoXP( VS_OUTPUT inV, uniform bool inShadows) : COLOR
{
    float4 albedo = tex2Dproj(DecalAlbedoSampler,inV.mTexDecal);
    float  specularAmount = tex2Dproj(DecalSpecSampler,inV.mTexDecal).a;
    float  mask = tex2Dproj(DecalMaskSampler,inV.mTexDecal).a;
    float3 normal = normalize(2*SampleScreen(NormalSampler,inV.mTexSS).xyz-1);

    float3 r = reflect(normalize(inV.mViewDirection),normal);
    float3 specular = pow(saturate(dot(r,SunDirection)),80)*specularAmount*SpecularColor.a*SpecularColor.rgb;

    float dotSunNormal = dot(SunDirection,normal);

    float  shadow = tex2D(ShadowSampler,inV.mShadow.xy).g;
    float3 light = SunColor*saturate(dotSunNormal)*shadow + SunAmbience;
    light = LightingMultiplier*light + ShadowFillColor*(1-light);
    albedo.rgb = light * ( albedo.rgb + specular.rgb );

    float waterDepth = tex2Dproj(UtilitySamplerC,inV.mTexWT*TerrainScale).g;
    float4 water = tex1D(WaterRampSampler,waterDepth);
    albedo.rgb = lerp(albedo.rgb,water.rgb,water.a);

    return float4(albedo.rgb,DecalAlpha*albedo.a*mask);
}
```