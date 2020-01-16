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
| Index | True | 0-5 | Enum (AuxiliaryId) | (See auxiliary list) |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |

### ColorGeneratorHue (28)
Implementation: LibAtem.MacroOperations.ColorGeneratorHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-5 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Hue | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### ColorGeneratorLuminescence (30)
Implementation: LibAtem.MacroOperations.ColorGeneratorLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-5 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Luma | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### ColorGeneratorSaturation (29)
Implementation: LibAtem.MacroOperations.ColorGeneratorSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ColorGeneratorIndex | True | 0-5 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Saturation | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### MacroSleep (7)
Implementation: LibAtem.MacroOperations.MacroSleepMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Frames | False | 0-5 | UInt | 16 bits |

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
| ArtAbove | False | 2 | Bool (Bit 0) |  |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceArtClip (172)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Clip | False | 0-5 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceV2ArtClip (400)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Clip | False | 4-9 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceArtCutInput (168)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-5 | Enum (VideoSource) | (See video source list) |

### SuperSourceV2ArtCutInput (396)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceArtFillInput (169)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-5 | Enum (VideoSource) | (See video source list) |

### SuperSourceV2ArtFillInput (397)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceArtGain (173)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceArtGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 0-5 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |

### SuperSourceV2ArtGain (401)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ArtGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 4-9 | UInt<br/>Double Scale 65536 | 0 - 65536<br/>(0 - 1) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| Invert | False | 2 | Bool (Bit 0) |  |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| PreMultiply | False | 2 | Bool (Bit 0) |  |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| Bevel | False | 2 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| BevelPosition | False | 2 | UInt | 0 - 100 |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| BevelSoftness | False | 2 | UInt | 0 - 100 |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| Enable | False | 2 | Bool (Bit 0) |  |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBorderHue (176)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderHueMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hue | False | 0-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### SuperSourceV2BorderHue (404)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hue | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| InnerSoftness | False | 2 | UInt | 0 - 100 |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBorderInnerWidth (181)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderInnerWidthMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerWidth | False | 0-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceV2BorderInnerWidth (409)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderInnerWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerWidth | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBorderLuminescence (178)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderLuminescenceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Luma | False | 0-7 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |

### SuperSourceV2BorderLuminescence (406)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Luma | False | 4-11 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

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
| OuterSoftness | False | 2 | UInt | 0 - 100 |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBorderOuterWidth (180)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderOuterWidthMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterWidth | False | 0-7 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |

### SuperSourceV2BorderOuterWidth (408)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderOuterWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterWidth | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBorderSaturation (177)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBorderSaturationMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Saturation | False | 0-7 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |

### SuperSourceV2BorderSaturation (405)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BorderSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Saturation | False | 4-11 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxEnable (188)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 1 | Bool (Bit 0) |  |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxEnable (416)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 4 | Bool (Bit 0) |  |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxInput (189)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxInput (417)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxInputMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 4-9 | Enum (VideoSource) | (See video source list) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxMaskBottom (195)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bottom | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxMaskBottom (423)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bottom | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxMaskEnable (193)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 1 | Bool (Bit 0) |  |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxMaskEnable (421)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 4 | Bool (Bit 0) |  |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxMaskLeft (196)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Left | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxMaskLeft (424)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Left | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxMaskRight (197)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Right | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxMaskRight (425)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Right | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 2097152<br/>(0 - 32) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxMaskTop (194)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Top | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxMaskTop (422)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Top | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 1179648<br/>(0 - 18) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxSize (192)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Size | False | 4-11 | Int<br/>Double Scale 65536 | 4587 - 65536<br/>(0.0699920654296875 - 1) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxSize (420)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Size | False | 4-11 | Int<br/>Double Scale 65536 | 4587 - 65536<br/>(0.0699920654296875 - 1) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxXPosition (190)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionX | False | 4-11 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxXPosition (418)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionX | False | 4-11 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceBoxYPosition (191)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceBoxYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionY | False | 4-11 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |
| BoxIndex | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### SuperSourceV2BoxYPosition (419)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2BoxYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionY | False | 4-11 | Int<br/>Double Scale 65536 | -3145728 - 3145728<br/>(-48 - 48) |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceShadowAltitude (187)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Altitude | False | 0-5 | UInt | 10 - 100 |

### SuperSourceV2ShadowAltitude (415)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Altitude | False | 2-7 | UInt | 10 - 100 |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### SuperSourceShadowDirection (186)
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceShadowDirectionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Direction | False | 0-7 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |

### SuperSourceV2ShadowDirection (414)
#### Since V8_0
Implementation: LibAtem.MacroOperations.SuperSource.SuperSourceV2ShadowDirectionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Direction | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |

### DownConvertMode (26)
Implementation: LibAtem.MacroOperations.Settings.DownConvertModeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| DownConvertMode | False | 0-5 | Enum (DownConvertMode) | 0 = CentreCut<br/>1 = Letterbox<br/>2 = Anamorphic |

### InputVideoPort (27)
Implementation: LibAtem.MacroOperations.Settings.InputVideoPortMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 0-5 | Enum (VideoSource) | (See video source list) |
| Port | False | 2-7 | Enum (MacroPortType) | 0 = SDI<br/>1 = HDMI<br/>2 = Component |

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
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |

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
| VideoMode | False | 0-5 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

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
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PreviewInput (3)
Implementation: LibAtem.MacroOperations.MixEffects.PreviewInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ProgramInput (2)
Implementation: LibAtem.MacroOperations.MixEffects.ProgramInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionMixRate (135)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionMixRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionPosition (133)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Position | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionPreview (134)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionPreviewMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Preview | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionSource (132)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionSourceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2 | Enum (TransitionLayer) | Bit 0 = Background<br/>Bit 1 = Key1<br/>Bit 2 = Key2<br/>Bit 3 = Key3<br/>Bit 4 = Key4 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStyle (131)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.TransitionStyleMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Style | False | 1 | Enum (TransitionStyle) | 0 = Mix<br/>1 = Dip<br/>2 = Wipe<br/>3 = DVE<br/>4 = Stinger |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeAndDVEFlipFlop (130)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeAndDVEFlipFlopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| FlipFlop | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeAndDVEReverse (129)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeAndDVEReverseMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ReverseDirection | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeBorderFillInput (128)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeBorderSoftness (127)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderSoftnessMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BorderSoftness | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeBorderWidth (126)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeBorderWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BorderWidth | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipePattern (125)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipePatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeRate (124)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeSymmetry (20)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeSymmetryMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Symmetry | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeXPosition (21)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| XPosition | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionWipeYPosition (22)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Wipe.TransitionWipeYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| YPosition | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDVECutInputEnable (217)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVECutInputEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDVECutInput (216)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVECutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDVEFillInput (215)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionDVEFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerClipDuration (141)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerClipDurationMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ClipDuration | False | 2-7 | UInt | 16 bits |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerDVEClip (146)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Clip | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerDVEGain (147)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerDVEInvert (148)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Invert | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerDVEPreMultiply (149)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerDVEPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PreMultiply | False | 1 | Bool (Bit 0) |  |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerMixRate (143)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerMixRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixRate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerPreRoll (144)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerPreRollMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Preroll | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerRate (138)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

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
| Source | False | 2 | Enum (StingerSource) | 0 = None<br/>1 = MediaPlayer1<br/>2 = MediaPlayer2<br/>3 = MediaPlayer3<br/>4 = MediaPlayer4 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionStingerTriggerPoint (142)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Stinger.TransitionStingerTriggerPointMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TriggerPoint | False | 2-7 | UInt | 16 bits |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDVEPattern (52)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.DVE.TransitionDVEPatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Pattern | False | 1 | Enum (DVEEffect) | 0 = SwooshTopLeft<br/>1 = SwooshTop<br/>2 = SwooshTopRight<br/>3 = SwooshLeft<br/>4 = SwooshRight<br/>5 = SwooshBottomLeft<br/>6 = SwooshBottom<br/>7 = SwooshBottomRight<br/>8 = SpinCWTopLeft<br/>9 = SpinCWTopRight<br/>10 = SpinCWBottomLeft<br/>11 = SpinCWBottomRight<br/>12 = SpinCCWTopLeft<br/>13 = SpinCCWTopRight<br/>14 = SpinCCWBottomLeft<br/>15 = SpinCCWBottomRight<br/>16 = SqueezeTopLeft<br/>17 = SqueezeTop<br/>18 = SqueezeTopRight<br/>19 = SqueezeLeft<br/>20 = SqueezeRight<br/>21 = SqueezeBottomLeft<br/>22 = SqueezeBottom<br/>23 = SqueezeBottomRight<br/>24 = PushTopLeft<br/>25 = PushTop<br/>26 = PushTopRight<br/>27 = PushLeft<br/>28 = PushRight<br/>29 = PushBottomLeft<br/>30 = PushBottom<br/>31 = PushBottomRight<br/>32 = GraphicCWSpin<br/>33 = GraphicCCWSpin<br/>34 = GraphicLogoWipe |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDVERate (58)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.DVE.TransitionDVERateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDipInput (137)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Dip.TransitionDipInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### TransitionDipRate (136)
Implementation: LibAtem.MacroOperations.MixEffects.Transition.Dip.TransitionDipRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2 | UInt | 0 - 250 |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyCutInput (37)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyFillInput (38)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Source | False | 2-7 | Enum (VideoSource) | (See video source list) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyFlyEnable (43)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyFlyEnableMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 4 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyMaskBottom (49)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bottom | False | 4-11 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyMaskEnable (47)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyMaskLeft (50)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Left | False | 4-11 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyMaskRight (51)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Right | False | 4-11 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyMaskTop (48)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Top | False | 4-11 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyOnAir (39)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyOnAirMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OnAir | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### KeyType (40)
Implementation: LibAtem.MacroOperations.MixEffects.Key.KeyTypeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyType | False | 2 | Enum (MixEffectKeyType) | 0 = Luma<br/>1 = Chroma<br/>2 = Pattern<br/>3 = DVE |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeyPattern (64)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyPatternMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeySize (65)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Size | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeySoftness (66)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySoftnessMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Softness | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeySymmetry (69)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeySymmetryMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Symmetry | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeyXPosition (67)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| XPosition | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PatternKeyYPosition (68)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Pattern.PatternKeyYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| YPosition | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### LumaKeyClip (41)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyClipMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Clip | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### LumaKeyGain (42)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### LumaKeyInvert (44)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Invert | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### LumaKeyPreMultiply (45)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Luma.LumaKeyPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PreMultiply | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyRate (70)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2-7 | UInt | 16 bits |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyRotation (79)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyRotationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rotation | False | 4-11 | Int<br/>Double Scale 65536 | -2147483648 - 2147483647<br/>(-32768 - 32767.99998474121) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyXPosition (74)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyXPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionX | False | 4-11 | Int<br/>Double Scale 65536 | -65536000 - 65536000<br/>(-1000 - 1000) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyXSize (71)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyXSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SizeX | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 131072<br/>(0 - 2) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyYPosition (75)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyYPositionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PositionY | False | 4-11 | Int<br/>Double Scale 65536 | -65536000 - 65536000<br/>(-1000 - 1000) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEAndFlyKeyYSize (72)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEAndFlyKeyYSizeMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SizeY | False | 4-11 | Int<br/>Double Scale 65536 | 0 - 131072<br/>(0 - 2) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderBevel (93)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bevel | False | 2 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderBevelPosition (99)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelPositionMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BevelPosition | False | 2 | UInt | 0 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderBevelSoftness (100)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderBevelSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| BevelSoftness | False | 2 | UInt | 0 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderEnable (78)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderHue (90)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hue | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderInnerSoftness (97)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderInnerSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerSoftness | False | 2 | UInt | 0 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderInnerWidth (95)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderInnerWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InnerWidth | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderLuminescence (92)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderLuminescenceMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Luma | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderOpacity (98)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOpacityMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Opacity | False | 2 | UInt | 0 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderOuterSoftness (96)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOuterSoftnessMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterSoftness | False | 2 | UInt | 0 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderOuterWidth (94)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderOuterWidthMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OuterWidth | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 1048576<br/>(0 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyBorderSaturation (91)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyBorderSaturationMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Saturation | False | 4-11 | UInt<br/>Double Scale 65535.99998474121 | 0 - 65535<br/>(0 - 0.9999847414437646) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyMaskBottom (55)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bottom | False | 4-11 | Int<br/>Double Scale 65536 | -589824 - 589824<br/>(-9 - 9) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyMaskEnable (53)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyMaskLeft (56)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Left | False | 4-11 | Int<br/>Double Scale 65536 | -1048576 - 1048576<br/>(-16 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyMaskRight (57)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Right | False | 4-11 | Int<br/>Double Scale 65536 | -1048576 - 1048576<br/>(-16 - 16) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyMaskTop (54)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Top | False | 4-11 | Int<br/>Double Scale 65536 | -589824 - 589824<br/>(-9 - 9) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyShadowAltitude (89)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowAltitudeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Altitude | False | 2 | UInt | 10 - 100 |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyShadowDirection (88)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowDirectionMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Direction | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DVEKeyShadowEnable (77)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.DVEKeyShadowEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FlyKeyRunToFull (82)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToAllMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FlyKeyRunToInfinity (86)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToInfinityMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Location | False | 2 | Enum (FlyKeyLocation) | 0 = CentreOfKey<br/>1 = TopLeft<br/>2 = TopCentre<br/>3 = TopRight<br/>4 = MiddleLeft<br/>5 = MiddleCentre<br/>6 = MiddleRight<br/>7 = BottomLeft<br/>8 = BottomCentre<br/>9 = BottomRight |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FlyKeyRunToKeyFrame (84)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeyRunToKeyFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyFrameIndex | True | 2 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FlyKeySetKeyFrame (80)
Implementation: LibAtem.MacroOperations.MixEffects.Key.DVE.FlyKeySetKeyFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| KeyFrameIndex | True | 2 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ChromaKeyGain (60)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ChromaKeyHue (61)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyHueMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hue | False | 4-11 | UInt<br/>Double Scale 65536 | 0 - 23592960<br/>(0 - 360) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ChromaKeyLift (62)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyLiftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Lift | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ChromaKeyNarrow (63)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyNarrowMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Narrow | False | 2 | Bool (Bit 0) |  |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### ChromaKeyClip (59)
Implementation: LibAtem.MacroOperations.MixEffects.Key.Chroma.ChromaKeyYSuppressMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| YSuppress | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerGoToBeginning (220)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerGoToBeginningMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerGoToFrame (221)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerGoToFrameMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Frame | False | 2-7 | UInt | 16 bits |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerLoop (224)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerLoopMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Loop | False | 2 | Bool (Bit 0) |  |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerPause (223)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerPauseMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerPlay (222)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerPlayMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceClipIndex (219)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceClipIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MediaIndex | False | 2-7 | UInt | 16 bits |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceClip (73)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceStillIndex (218)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceStillIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MediaIndex | False | 2-7 | UInt | 16 bits |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### MediaPlayerSourceStill (225)
Implementation: LibAtem.MacroOperations.Media.MediaPlayerSourceStillMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

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
| Loop | False | 2 | Bool (Bit 0) |  |
| Index | True | 0 | UInt | 0 - 3 |

### HyperDeckSetSingleClip (283)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSingleClipMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SingleClipEnabled | False | 2 | Bool (Bit 0) |  |
| Index | True | 0 | UInt | 0 - 3 |

### HyperDeckSetSourceClipIndex (273)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSourceClipIndexMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ClipIndex | False | 2-7 | UInt | 16 bits |
| Index | True | 0 | UInt | 0 - 3 |

### HyperDeckSetSpeed (278)
Implementation: LibAtem.MacroOperations.HyperDeck.HyperDeckSetSpeedMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SpeedPercent | False | 2-7 | UInt | 0 - 100 |
| Index | True | 0 | UInt | 0 - 3 |

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
| Clip | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyCutInput (151)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyCutInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyFillInput (150)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyFillInputMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 2-7 | Enum (VideoSource) | (See video source list) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyGain (157)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyGainMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 2-9 | UInt<br/>Double Scale 4294967295 | 0 - 4294967295<br/>(0 - 1) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyInvert (163)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyInvertMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Invert | False | 1 | Bool (Bit 0) |  |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyMaskBottom (160)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskBottomMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bottom | False | 4-11 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyMaskEnable (158)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskEnableMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enable | False | 1 | Bool (Bit 0) |  |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyMaskLeft (161)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskLeftMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Left | False | 4-11 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyMaskRight (162)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskRightMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Right | False | 4-11 | Int<br/>Double Scale 65535 | -1048560 - 1048560<br/>(-16 - 16) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyMaskTop (159)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyMaskTopMacroOp

Payload length: 8

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Top | False | 4-11 | Int<br/>Double Scale 65535 | -589815 - 589815<br/>(-9 - 9) |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyOnAir (154)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyOnAirMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| OnAir | False | 1 | Bool (Bit 0) |  |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyPreMultiply (164)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyPreMultiplyMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| PreMultiply | False | 1 | Bool (Bit 0) |  |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyRate (152)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyRateMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Rate | False | 2-7 | UInt | 16 bits |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DownstreamKeyTie (155)
Implementation: LibAtem.MacroOperations.DownStreamKey.DownstreamKeyTieMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Tie | False | 1 | Bool (Bit 0) |  |
| KeyIndex | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

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
| Index | True | 0-5 | Enum (AudioSource) | (See audio source list) |
| Balance | False | 4-11 | Int<br/>Double Scale 65535 | -3276750 - 3276750<br/>(-50 - 50) |

### AudioMixerInputGain (199)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputGainMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (AudioSource) | (See audio source list) |
| RawGain | False | 2-7 | UInt | 16 bits |

### AudioMixerInputMixType (198)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputMixTypeMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-5 | Enum (AudioSource) | (See audio source list) |
| MixOption | False | 2 | Enum (AudioMixOption) | 0 = Off<br/>1 = On<br/>2 = AudioFollowVideo |

### AudioMixerInputResetPeaks (211)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerInputResetPeaksMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Input | False | 0-5 | Enum (AudioSource) | (See audio source list) |

### AudioMixerMasterOutBalance (202)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMasterOutBalanceMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Balance | False | 0-7 | Int<br/>Double Scale 65535 | -3276750 - 3276750<br/>(-50 - 50) |

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
| RawGain | False | 0-5 | UInt | 16 bits |

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
| RawGain | False | 0-5 | UInt | 16 bits |

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
| Input | False | 0-5 | Enum (AudioSource) | (See audio source list) |

### AudioMixerMonitorOutSolo (207)
Implementation: LibAtem.MacroOperations.Audio.AudioMixerMonitorOutSoloMacroOp

Payload length: 4

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Solo | False | 0 | Bool (Bit 0) |  |

