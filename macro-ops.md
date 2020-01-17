---
#layout: page
title: "Blackmagic Design ATEM Protocol Macro Operations"
permalink: /macro-operations
---
## Macro Operations

TODO - blurb and license info

Note: The value ranges are estimates are not guaranteed to be accurate

### AuxiliaryInput (31)
Implementation: LibAtem.MacroOperations.AuxiliaryInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AuxiliaryId) | (See auxiliary list) |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### ColorGeneratorHue (28)
Implementation: LibAtem.MacroOperations.ColorGeneratorHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-1 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Hue | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### ColorGeneratorLuminescence (30)
Implementation: LibAtem.MacroOperations.ColorGeneratorLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-1 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Luma | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### ColorGeneratorSaturation (29)
Implementation: LibAtem.MacroOperations.ColorGeneratorSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-1 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Saturation | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### MacroSleep (7)
Implementation: LibAtem.MacroOperations.MacroSleepMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Frames | False | 0-1 | UInt | 16 bits |

### SuperSourceArtAbove (170)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtAboveMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ArtAbove | False | 0 | Bool (Bit 0) |  |

### SuperSourceV2ArtAbove (398)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtAboveMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| ArtAbove | False | 2 | Bool (Bit 0) |  |

### SuperSourceArtClip (172)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Clip | False | 0-1 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceV2ArtClip (400)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Clip | False | 4-5 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceArtCutInput (168)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-1 | Enum (VideoSource) | (See video source list) |

### SuperSourceV2ArtCutInput (396)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### SuperSourceArtFillInput (169)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-1 | Enum (VideoSource) | (See video source list) |

### SuperSourceV2ArtFillInput (397)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### SuperSourceArtGain (173)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 0-1 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceV2ArtGain (401)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Gain | False | 4-5 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceArtInvert (174)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Invert | False | 0 | Bool (Bit 0) |  |

### SuperSourceV2ArtInvert (402)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Invert | False | 2 | Bool (Bit 0) |  |

### SuperSourceArtPreMultiply (171)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PreMultiply | False | 0 | Bool (Bit 0) |  |

### SuperSourceV2ArtPreMultiply (399)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| PreMultiply | False | 2 | Bool (Bit 0) |  |

### SuperSourceBorderBevel (179)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderBevelMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bevel | False | 0 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |

### SuperSourceV2BorderBevel (407)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderBevelMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Bevel | False | 2 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |

### SuperSourceBorderBevelPosition (184)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderBevelPositionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BevelPosition | False | 0 | UInt | 0 - 100 |

### SuperSourceV2BorderBevelPosition (412)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderBevelPositionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BevelPosition | False | 2 | UInt | 0 - 100 |

### SuperSourceBorderBevelSoftness (185)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderBevelSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BevelSoftness | False | 0 | UInt | 0 - 100 |

### SuperSourceV2BorderBevelSoftness (413)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderBevelSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BevelSoftness | False | 2 | UInt | 0 - 100 |

### SuperSourceBorderEnable (175)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 0 | Bool (Bit 0) |  |

### SuperSourceV2BorderEnable (403)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Enable | False | 2 | Bool (Bit 0) |  |

### SuperSourceBorderHue (176)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderHueMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hue | False | 0-3 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### SuperSourceV2BorderHue (404)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Hue | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### SuperSourceBorderInnerSoftness (183)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderInnerSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerSoftness | False | 0 | UInt | 0 - 100 |

### SuperSourceV2BorderInnerSoftness (411)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderInnerSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| InnerSoftness | False | 2 | UInt | 0 - 100 |

### SuperSourceBorderInnerWidth (181)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderInnerWidthMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerWidth | False | 0-3 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceV2BorderInnerWidth (409)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderInnerWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| InnerWidth | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceBorderLuminescence (178)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderLuminescenceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Luma | False | 0-3 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### SuperSourceV2BorderLuminescence (406)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Luma | False | 4-7 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### SuperSourceBorderOuterSoftness (182)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderOuterSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterSoftness | False | 0 | UInt | 0 - 100 |

### SuperSourceV2BorderOuterSoftness (410)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderOuterSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| OuterSoftness | False | 2 | UInt | 0 - 100 |

### SuperSourceBorderOuterWidth (180)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderOuterWidthMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterWidth | False | 0-3 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceV2BorderOuterWidth (408)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderOuterWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| OuterWidth | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceBorderSaturation (177)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderSaturationMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Saturation | False | 0-3 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |

### SuperSourceV2BorderSaturation (405)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Saturation | False | 4-7 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |

### SuperSourceBoxEnable (188)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 1 | Bool (Bit 0) |  |

### SuperSourceV2BoxEnable (416)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 4 | Bool (Bit 0) |  |

### SuperSourceBoxInput (189)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### SuperSourceV2BoxInput (417)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxInputMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 4-5 | Enum (VideoSource) | (See video source list) |

### SuperSourceBoxMaskBottom (195)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bottom | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |

### SuperSourceV2BoxMaskBottom (423)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bottom | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |

### SuperSourceBoxMaskEnable (193)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 1 | Bool (Bit 0) |  |

### SuperSourceV2BoxMaskEnable (421)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 4 | Bool (Bit 0) |  |

### SuperSourceBoxMaskLeft (196)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Left | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |

### SuperSourceV2BoxMaskLeft (424)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Left | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |

### SuperSourceBoxMaskRight (197)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Right | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |

### SuperSourceV2BoxMaskRight (425)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Right | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |

### SuperSourceBoxMaskTop (194)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Top | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |

### SuperSourceV2BoxMaskTop (422)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Top | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |

### SuperSourceBoxSize (192)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Size | False | 4-7 | Int<br/>Double Scale 65536 | 4587 - 65536<br/>(0.0699920654296875 - 1) |

### SuperSourceV2BoxSize (420)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Size | False | 4-7 | Int<br/>Double Scale 65536 | 4587 - 65536<br/>(0.0699920654296875 - 1) |

### SuperSourceBoxXPosition (190)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionX | False | 4-7 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |

### SuperSourceV2BoxXPosition (418)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionX | False | 4-7 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |

### SuperSourceBoxYPosition (191)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionY | False | 4-7 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |

### SuperSourceV2BoxYPosition (419)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionY | False | 4-7 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |

### SuperSourceShadowAltitude (187)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Altitude | False | 0-1 | UInt | 10 - 100 |

### SuperSourceV2ShadowAltitude (415)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Altitude | False | 2-3 | UInt | 10 - 100 |

### SuperSourceShadowDirection (186)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceShadowDirectionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Direction | False | 0-3 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### SuperSourceV2ShadowDirection (414)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ShadowDirectionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Direction | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### DownConvertMode (26)
Implementation: LibAtem.MacroOperations.Settings.DownConvertModeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| DownConvertMode | False | 0-1 | Enum (DownConvertMode) | 0 = CentreCut<br/>1 = Letterbox<br/>2 = Anamorphic |

### InputVideoPort (27)
Implementation: LibAtem.MacroOperations.Settings.InputVideoPortMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-1 | Enum (VideoSource) | (See video source list) |
| Port | False | 2-3 | Enum (MacroPortType) | 0 = SDI<br/>1 = HDMI<br/>2 = Component |

### MultiViewLayout (33)
Implementation: LibAtem.MacroOperations.Settings.MultiViewLayoutMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiViewIndex | False | 0 | UInt | 8 bits |
| Layout | False | 1 | Enum (MultiViewLayout) | 0 = ProgramTop<br/>1 = ProgramBottom<br/>2 = ProgramLeft<br/>3 = ProgramRight |

### MultiViewWindowInput (32)
Implementation: LibAtem.MacroOperations.Settings.MultiViewWindowInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiViewIndex | False | 0 | UInt | 8 bits |
| WindowIndex | False | 1 | UInt | 8 bits |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### SetSerialPortFunction (259)
Implementation: LibAtem.MacroOperations.Settings.SetSerialPortFunctionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ExternalSerialPortIndex | False | 0 | UInt | 0 - 0 |
| SerialMode | False | 1 | Enum (SerialMode) | 0 = None<br/>1 = PtzVisca<br/>2 = Gvg100 |

### VideoMode (12)
Implementation: LibAtem.MacroOperations.Settings.VideoModeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| VideoMode | False | 0-1 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

### AutoTransition (5)
Implementation: LibAtem.MacroOperations.MixEffects.AutoTransitionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### CutTransition (4)
Implementation: LibAtem.MacroOperations.MixEffects.CutTransitionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FadeToBlackAuto (167)
Implementation: LibAtem.MacroOperations.MixEffects.FadeToBlackAutoMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FadeToBlackRate (165)
Implementation: LibAtem.MacroOperations.MixEffects.FadeToBlackRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### PreviewInput (3)
Implementation: LibAtem.MacroOperations.MixEffects.PreviewInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### ProgramInput (2)
Implementation: LibAtem.MacroOperations.MixEffects.ProgramInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TransitionMixRate (135)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionMixRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### TransitionPosition (133)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Position | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionPreview (134)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionPreviewMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Preview | False | 1 | Bool (Bit 0) |  |

### TransitionSource (132)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionSourceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2 | Enum (TransitionLayer) | Bit 0 = Background<br/>Bit 1 = Key1<br/>Bit 2 = Key2<br/>Bit 3 = Key3<br/>Bit 4 = Key4 |

### TransitionStyle (131)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionStyleMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Style | False | 1 | Enum (TransitionStyle) | 0 = Mix<br/>1 = Dip<br/>2 = Wipe<br/>3 = DVE<br/>4 = Stinger |

### TransitionWipeAndDVEFlipFlop (130)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeAndDVEFlipFlopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| FlipFlop | False | 1 | Bool (Bit 0) |  |

### TransitionWipeAndDVEReverse (129)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeAndDVEReverseMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| ReverseDirection | False | 1 | Bool (Bit 0) |  |

### TransitionWipeBorderFillInput (128)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TransitionWipeBorderSoftness (127)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderSoftnessMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| BorderSoftness | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionWipeBorderWidth (126)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| BorderWidth | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionWipePattern (125)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipePatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |

### TransitionWipeRate (124)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### TransitionWipeSymmetry (20)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeSymmetryMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Symmetry | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionWipeXPosition (21)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| XPosition | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionWipeYPosition (22)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| YPosition | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionDVECutInputEnable (217)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVECutInputEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 1 | Bool (Bit 0) |  |

### TransitionDVECutInput (216)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVECutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TransitionDVEFillInput (215)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVEFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TransitionStingerClipDuration (141)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerClipDurationMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| ClipDuration | False | 2-3 | UInt | 16 bits |

### TransitionStingerDVEClip (146)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Clip | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionStingerDVEGain (147)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Gain | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### TransitionStingerDVEInvert (148)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Invert | False | 1 | Bool (Bit 0) |  |

### TransitionStingerDVEPreMultiply (149)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultiply | False | 1 | Bool (Bit 0) |  |

### TransitionStingerMixRate (143)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerMixRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| MixRate | False | 2 | UInt | 0 - 250 |

### TransitionStingerPreRoll (144)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerPreRollMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Preroll | False | 2 | UInt | 0 - 250 |

### TransitionStingerRate (138)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### TransitionStingerResetDurations (145)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerResetDurationsMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerSourceMediaPlayer (140)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerSourceMediaPlayerMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2 | Enum (StingerSource) | 0 = None<br/>1 = MediaPlayer1<br/>2 = MediaPlayer2<br/>3 = MediaPlayer3<br/>4 = MediaPlayer4 |

### TransitionStingerTriggerPoint (142)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerTriggerPointMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| TriggerPoint | False | 2-3 | UInt | 16 bits |

### TransitionDVEPattern (52)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.DVE.TransitionDVEPatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Pattern | False | 1 | Enum (DVEEffect) | 0 = SwooshTopLeft<br/>1 = SwooshTop<br/>2 = SwooshTopRight<br/>3 = SwooshLeft<br/>4 = SwooshRight<br/>5 = SwooshBottomLeft<br/>6 = SwooshBottom<br/>7 = SwooshBottomRight<br/>8 = SpinCWTopLeft<br/>9 = SpinCWTopRight<br/>10 = SpinCWBottomLeft<br/>11 = SpinCWBottomRight<br/>12 = SpinCCWTopLeft<br/>13 = SpinCCWTopRight<br/>14 = SpinCCWBottomLeft<br/>15 = SpinCCWBottomRight<br/>16 = SqueezeTopLeft<br/>17 = SqueezeTop<br/>18 = SqueezeTopRight<br/>19 = SqueezeLeft<br/>20 = SqueezeRight<br/>21 = SqueezeBottomLeft<br/>22 = SqueezeBottom<br/>23 = SqueezeBottomRight<br/>24 = PushTopLeft<br/>25 = PushTop<br/>26 = PushTopRight<br/>27 = PushLeft<br/>28 = PushRight<br/>29 = PushBottomLeft<br/>30 = PushBottom<br/>31 = PushBottomRight<br/>32 = GraphicCWSpin<br/>33 = GraphicCCWSpin<br/>34 = GraphicLogoWipe |

### TransitionDVERate (58)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.DVE.TransitionDVERateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### TransitionDipInput (137)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Dip.TransitionDipInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TransitionDipRate (136)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Dip.TransitionDipRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### KeyCutInput (37)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### KeyFillInput (38)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### KeyFlyEnable (43)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyFlyEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 4 | Bool (Bit 0) |  |

### KeyMaskBottom (49)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bottom | False | 4-7 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |

### KeyMaskEnable (47)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 2 | Bool (Bit 0) |  |

### KeyMaskLeft (50)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Left | False | 4-7 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |

### KeyMaskRight (51)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Right | False | 4-7 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |

### KeyMaskTop (48)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Top | False | 4-7 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |

### KeyOnAir (39)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyOnAirMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 2 | Bool (Bit 0) |  |

### KeyType (40)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyTypeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyType | False | 2 | Enum (MixEffectKeyType) | 0 = Luma<br/>1 = Chroma<br/>2 = Pattern<br/>3 = DVE |

### PatternKeyPattern (64)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyPatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |

### PatternKeySize (65)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Size | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### PatternKeySoftness (66)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySoftnessMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Softness | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### PatternKeySymmetry (69)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySymmetryMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Symmetry | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### PatternKeyXPosition (67)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| XPosition | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### PatternKeyYPosition (68)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| YPosition | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### LumaKeyClip (41)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Clip | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### LumaKeyGain (42)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Gain | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### LumaKeyInvert (44)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Invert | False | 2 | Bool (Bit 0) |  |

### LumaKeyPreMultiply (45)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultiply | False | 2 | Bool (Bit 0) |  |

### DVEAndFlyKeyRate (70)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2-3 | UInt | 16 bits |

### DVEAndFlyKeyRotation (79)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyRotationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rotation | False | 4-7 | Int<br/>Double Scale 65536 | -2147483648 - 2147483647<br/>(-32768 - 32767.99998474121) |

### DVEAndFlyKeyXPosition (74)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionX | False | 4-7 | Int<br/>Double Scale 65536 | -65536000 - 65536000<br/>(-1000 - 1000) |

### DVEAndFlyKeyXSize (71)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyXSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SizeX | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 131072<br/>(0 - 2) |

### DVEAndFlyKeyYPosition (75)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PositionY | False | 4-7 | Int<br/>Double Scale 65536 | -65536000 - 65536000<br/>(-1000 - 1000) |

### DVEAndFlyKeyYSize (72)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyYSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SizeY | False | 4-7 | Int<br/>Double Scale 65536 | 0 - 131072<br/>(0 - 2) |

### DVEKeyBorderBevel (93)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bevel | False | 2 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |

### DVEKeyBorderBevelPosition (99)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelPositionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| BevelPosition | False | 2 | UInt | 0 - 100 |

### DVEKeyBorderBevelSoftness (100)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| BevelSoftness | False | 2 | UInt | 0 - 100 |

### DVEKeyBorderEnable (78)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 2 | Bool (Bit 0) |  |

### DVEKeyBorderHue (90)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Hue | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### DVEKeyBorderInnerSoftness (97)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderInnerSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| InnerSoftness | False | 2 | UInt | 0 - 100 |

### DVEKeyBorderInnerWidth (95)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderInnerWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| InnerWidth | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### DVEKeyBorderLuminescence (92)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Luma | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### DVEKeyBorderOpacity (98)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOpacityMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Opacity | False | 2 | UInt | 0 - 100 |

### DVEKeyBorderOuterSoftness (96)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOuterSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OuterSoftness | False | 2 | UInt | 0 - 100 |

### DVEKeyBorderOuterWidth (94)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOuterWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OuterWidth | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### DVEKeyBorderSaturation (91)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Saturation | False | 4-7 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |

### DVEKeyMaskBottom (55)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bottom | False | 4-7 | Int<br/>Double Scale 65536 | -589824 - 589824<br/>(-9 - 9) |

### DVEKeyMaskEnable (53)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 2 | Bool (Bit 0) |  |

### DVEKeyMaskLeft (56)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Left | False | 4-7 | Int<br/>Double Scale 65536 | -1048576 - 1048576<br/>(-16 - 16) |

### DVEKeyMaskRight (57)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Right | False | 4-7 | Int<br/>Double Scale 65536 | -1048576 - 1048576<br/>(-16 - 16) |

### DVEKeyMaskTop (54)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Top | False | 4-7 | Int<br/>Double Scale 65536 | -589824 - 589824<br/>(-9 - 9) |

### DVEKeyShadowAltitude (89)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Altitude | False | 2 | UInt | 10 - 100 |

### DVEKeyShadowDirection (88)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowDirectionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Direction | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### DVEKeyShadowEnable (77)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 2 | Bool (Bit 0) |  |

### FlyKeyRunToFull (82)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToAllMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FlyKeyRunToInfinity (86)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToInfinityMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Location | False | 2 | Enum (FlyKeyLocation) | 0 = CentreOfKey<br/>1 = TopLeft<br/>2 = TopCentre<br/>3 = TopRight<br/>4 = MiddleLeft<br/>5 = MiddleCentre<br/>6 = MiddleRight<br/>7 = BottomLeft<br/>8 = BottomCentre<br/>9 = BottomRight |

### FlyKeyRunToKeyFrame (84)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToKeyFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyFrameIndex | True | 2 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |

### FlyKeySetKeyFrame (80)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeySetKeyFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyFrameIndex | True | 2 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |

### ChromaKeyGain (60)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Gain | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### ChromaKeyHue (61)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Hue | False | 4-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### ChromaKeyLift (62)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyLiftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Lift | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### ChromaKeyNarrow (63)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyNarrowMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Narrow | False | 2 | Bool (Bit 0) |  |

### ChromaKeyClip (59)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyYSuppressMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| YSuppress | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### MediaPlayerGoToBeginning (220)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerGoToBeginningMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerGoToFrame (221)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerGoToFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Frame | False | 2-3 | UInt | 16 bits |

### MediaPlayerLoop (224)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerLoopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Loop | False | 2 | Bool (Bit 0) |  |

### MediaPlayerPause (223)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerPauseMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerPlay (222)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerPlayMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceClipIndex (219)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceClipIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| MediaIndex | False | 2-3 | UInt | 16 bits |

### MediaPlayerSourceClip (73)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceStillIndex (218)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceStillIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| MediaIndex | False | 2-3 | UInt | 16 bits |

### MediaPlayerSourceStill (225)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceStillMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### HyperDeckPlay (279)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckPlayMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |

### HyperDeckSetLoop (277)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetLoopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |
| Loop | False | 2 | Bool (Bit 0) |  |

### HyperDeckSetSingleClip (283)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSingleClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |
| SingleClipEnabled | False | 2 | Bool (Bit 0) |  |

### HyperDeckSetSourceClipIndex (273)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSourceClipIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |
| ClipIndex | False | 2-3 | UInt | 16 bits |

### HyperDeckSetSpeed (278)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSpeedMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |
| SpeedPercent | False | 2-3 | UInt | 0 - 100 |

### HyperDeckStop (280)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckStopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 0 - 3 |

### DownstreamKeyAuto (153)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyAutoMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyClip (156)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Clip | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### DownstreamKeyCutInput (151)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### DownstreamKeyFillInput (150)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### DownstreamKeyGain (157)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Gain | False | 2-5 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### DownstreamKeyInvert (163)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Invert | False | 1 | Bool (Bit 0) |  |

### DownstreamKeyMaskBottom (160)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Bottom | False | 4-7 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |

### DownstreamKeyMaskEnable (158)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enable | False | 1 | Bool (Bit 0) |  |

### DownstreamKeyMaskLeft (161)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Left | False | 4-7 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |

### DownstreamKeyMaskRight (162)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Right | False | 4-7 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |

### DownstreamKeyMaskTop (159)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Top | False | 4-7 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |

### DownstreamKeyOnAir (154)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyOnAirMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 1 | Bool (Bit 0) |  |

### DownstreamKeyPreMultiply (164)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultiply | False | 1 | Bool (Bit 0) |  |

### DownstreamKeyRate (152)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2-3 | UInt | 16 bits |

### DownstreamKeyTie (155)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyTieMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Tie | False | 1 | Bool (Bit 0) |  |

### AudioMixerAfvFollowTransition (299)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerAfvFollowTransitionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 0 | Bool (Bit 0) |  |

### AudioMixerInputBalance (200)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputBalanceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| Balance | False | 4-7 | Int<br/>Double Scale 65535 | -3276750 - 3276750<br/>(-50 - 50) |

### AudioMixerInputGain (199)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| RawGain | False | 2-3 | UInt | 16 bits |

### AudioMixerInputMixType (198)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputMixTypeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| MixOption | False | 2 | Enum (AudioMixOption) | 0 = Off<br/>1 = On<br/>2 = AudioFollowVideo |

### AudioMixerInputResetPeaks (211)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputResetPeaksMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 0-1 | Enum (AudioSource) | (See audio source list) |

### AudioMixerMasterOutBalance (202)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMasterOutBalanceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Balance | False | 0-3 | Int<br/>Double Scale 65535 | -3276750 - 3276750<br/>(-50 - 50) |

### AudioMixerMasterOutFollowFadeToBlackMixEffectBlock1 (203)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMasterOutFollowFadeToBlackMixEffectBlock1MacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Follow | False | 0 | Bool (Bit 0) |  |

### AudioMixerMasterOutGain (201)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMasterOutGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| RawGain | False | 0-1 | UInt | 16 bits |

### AudioMixerMasterOutResetPeaks (213)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMasterOutResetPeaksMacroOp

Payload length: 0

Command has no properties

### AudioMixerMonitorOutDim (209)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutDimMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Dim | False | 0 | Bool (Bit 0) |  |

### AudioMixerMonitorOutGain (205)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| RawGain | False | 0-1 | UInt | 16 bits |

### AudioMixerMonitorOut (204)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 0 | Bool (Bit 0) |  |

### AudioMixerMonitorOutMute (206)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutMuteMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mute | False | 0 | Bool (Bit 0) |  |

### AudioMixerMonitorOutResetPeaks (214)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutResetPeaksMacroOp

Payload length: 0

Command has no properties

### AudioMixerMonitorOutSoloInput (208)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutSoloInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 0-1 | Enum (AudioSource) | (See audio source list) |

### AudioMixerMonitorOutSolo (207)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutSoloMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Solo | False | 0 | Bool (Bit 0) |  |

