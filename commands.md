---
#layout: page
title: "Blackmagic Design ATEM Protocol Commands"
permalink: /commands
---
## Commands
TODO - blurb and license info

Note: The value ranges are estimates are not guaranteed to be accurate

### AuxS
Implementation: LibAtem.Commands.AuxSourceGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Id | True | 0 | Enum (AuxiliaryId) | (See auxiliary list) |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CAuS
Implementation: LibAtem.Commands.AuxSourceSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | UInt | 8 bits |
| Id | True | 1 | Enum (AuxiliaryId) | (See auxiliary list) |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### ColV
Implementation: LibAtem.Commands.ColorGeneratorGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Hue | False | 2-3 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Saturation | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Luma | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |

### CClV
Implementation: LibAtem.Commands.ColorGeneratorSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Hue<br/>Bit 1 = Saturation<br/>Bit 2 = Luma |
| Index | True | 1 | Enum (ColorGeneratorId) | 0 = One<br/>1 = Two |
| Hue | False | 2-3 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Saturation | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Luma | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |

### InCm
TODO - support generating this

### SRcl
Implementation: LibAtem.Commands.StartupStateClearCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Data | False | 0-3 | Bytes |  |

### SRsv
Implementation: LibAtem.Commands.StartupStateSaveCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Data | False | 0-3 | Bytes |  |

### TlIn
TODO - support generating this

### TlSr
TODO - support generating this

### _TlC
Implementation: LibAtem.Commands.TallyChannelConfigCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Unknown | False | 0-3 | Bytes |  |
| InputCount | False | 4 | UInt | 0 - 20 |

### TlFc
TODO - support generating this

### Time
Implementation: LibAtem.Commands.TimeCodeCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Hour | False | 0 | UInt | 0 - 23 |
| Minute | False | 1 | UInt | 0 - 59 |
| Second | False | 2 | UInt | 0 - 59 |
| Frame | False | 3 | UInt | 0 - 59 |
| IsDropFrame | False | 5 | Bool (Bit 0) |  |

### TiRq
Implementation: LibAtem.Commands.TimeCodeRequestCommand

Payload length: 0

Direction: ToServer

Command has no properties

### Warn
Implementation: LibAtem.Commands.WarningCommand

Payload length: 44

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Text | False | 0-43 | String |  |

### SSBd
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourceBorderGetCommand

Payload length: 24

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Enabled | False | 1 | Bool (Bit 0) |  |
| Bevel | False | 2 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| OuterWidth | False | 4-5 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| InnerWidth | False | 6-7 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| OuterSoftness | False | 8 | UInt | 0 - 100 |
| InnerSoftness | False | 9 | UInt | 0 - 100 |
| BevelSoftness | False | 10 | UInt | 0 - 100 |
| BevelPosition | False | 11 | UInt | 0 - 100 |
| Hue | False | 12-13 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Saturation | False | 14-15 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Luma | False | 16-17 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| LightSourceDirection | False | 18-19 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| LightSourceAltitude | False | 20 | UInt<br/>Double Scale 1 | 0 - 100<br/>(0 - 100) |

### CSBd
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourceBorderSetCommand

Payload length: 24

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Enabled<br/>Bit 1 = Bevel<br/>Bit 2 = OuterWidth<br/>Bit 3 = InnerWidth<br/>Bit 4 = OuterSoftness<br/>Bit 5 = InnerSoftness<br/>Bit 6 = BevelSoftness<br/>Bit 7 = BevelPosition<br/>Bit 8 = Hue<br/>Bit 9 = Saturation<br/>Bit 10 = Luma<br/>Bit 11 = LightSourceDirection<br/>Bit 12 = LightSourceAltitude |
| SSrcId | True | 2 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Enabled | False | 3 | Bool (Bit 0) |  |
| Bevel | False | 4 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| OuterWidth | False | 6-7 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| InnerWidth | False | 8-9 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| OuterSoftness | False | 10 | UInt | 0 - 100 |
| InnerSoftness | False | 11 | UInt | 0 - 100 |
| BevelSoftness | False | 12 | UInt | 0 - 100 |
| BevelPosition | False | 13 | UInt | 0 - 100 |
| Hue | False | 14-15 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Saturation | False | 16-17 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Luma | False | 18-19 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| LightSourceDirection | False | 20-21 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| LightSourceAltitude | False | 22 | UInt | 0 - 100 |

### SSBP
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourceBoxGetV8Command

Payload length: 24

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 1 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enabled | False | 2 | Bool (Bit 0) |  |
| Source | False | 4-5 | Enum (VideoSource) | (See video source list) |
| PositionX | False | 6-7 | Int<br/>Double Scale 100 | -4800 - 4800<br/>(-48 - 48) |
| PositionY | False | 8-9 | Int<br/>Double Scale 100 | -3400 - 3400<br/>(-34 - 34) |
| Size | False | 10-11 | UInt<br/>Double Scale 1000 | 70 - 1000<br/>(0.07 - 1) |
| Cropped | False | 12 | Bool (Bit 0) |  |
| CropTop | False | 14-15 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropBottom | False | 16-17 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropLeft | False | 18-19 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |
| CropRight | False | 20-21 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |

#### Older
Implementation: LibAtem.Commands.SuperSource.SuperSourceBoxGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enabled | False | 1 | Bool (Bit 0) |  |
| InputSource | False | 2-3 | Enum (VideoSource) | (See video source list) |
| PositionX | False | 4-5 | Int<br/>Double Scale 100 | -4800 - 4800<br/>(-48 - 48) |
| PositionY | False | 6-7 | Int<br/>Double Scale 100 | -3400 - 3400<br/>(-34 - 34) |
| Size | False | 8-9 | UInt<br/>Double Scale 1000 | 70 - 1000<br/>(0.07 - 1) |
| Cropped | False | 10 | Bool (Bit 0) |  |
| CropTop | False | 12-13 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropBottom | False | 14-15 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropLeft | False | 16-17 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |
| CropRight | False | 18-19 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |

### CSBP
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourceBoxSetV8Command

Payload length: 24

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Enabled<br/>Bit 1 = Source<br/>Bit 2 = PositionX<br/>Bit 3 = PositionY<br/>Bit 4 = Size<br/>Bit 5 = Cropped<br/>Bit 6 = CropTop<br/>Bit 7 = CropBottom<br/>Bit 8 = CropLeft<br/>Bit 9 = CropRight |
| SSrcId | True | 2 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| BoxIndex | True | 3 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enabled | False | 4 | Bool (Bit 0) |  |
| Source | False | 6-7 | Enum (VideoSource) | (See video source list) |
| PositionX | False | 8-9 | Int<br/>Double Scale 100 | -4800 - 4800<br/>(-48 - 48) |
| PositionY | False | 10-11 | Int<br/>Double Scale 100 | -3400 - 3400<br/>(-34 - 34) |
| Size | False | 12-13 | UInt<br/>Double Scale 1000 | 70 - 1000<br/>(0.07 - 1) |
| Cropped | False | 14 | Bool (Bit 0) |  |
| CropTop | False | 16-17 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropBottom | False | 18-19 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropLeft | False | 20-21 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |
| CropRight | False | 22-23 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |

#### Older
Implementation: LibAtem.Commands.SuperSource.SuperSourceBoxSetCommand

Payload length: 24

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Enabled<br/>Bit 1 = Source<br/>Bit 2 = PositionX<br/>Bit 3 = PositionY<br/>Bit 4 = Size<br/>Bit 5 = Cropped<br/>Bit 6 = CropTop<br/>Bit 7 = CropBottom<br/>Bit 8 = CropLeft<br/>Bit 9 = CropRight |
| BoxIndex | True | 2 | Enum (SuperSourceBoxId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Enabled | False | 3 | Bool (Bit 0) |  |
| Source | False | 4-5 | Enum (VideoSource) | (See video source list) |
| PositionX | False | 6-7 | Int<br/>Double Scale 100 | -4800 - 4800<br/>(-48 - 48) |
| PositionY | False | 8-9 | Int<br/>Double Scale 100 | -3400 - 3400<br/>(-34 - 34) |
| Size | False | 10-11 | UInt<br/>Double Scale 1000 | 70 - 1000<br/>(0.07 - 1) |
| Cropped | False | 12 | Bool (Bit 0) |  |
| CropTop | False | 14-15 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropBottom | False | 16-17 | UInt<br/>Double Scale 1000 | 0 - 18000<br/>(0 - 18) |
| CropLeft | False | 18-19 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |
| CropRight | False | 20-21 | UInt<br/>Double Scale 1000 | 0 - 32000<br/>(0 - 32) |

### SSrc
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourcePropertiesGetV8Command

Payload length: 16

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | True | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| ArtFillSource | False | 2-3 | Enum (VideoSource) | (See video source list) |
| ArtCutSource | False | 4-5 | Enum (VideoSource) | (See video source list) |
| ArtOption | False | 6 | Enum (SuperSourceArtOption) | 0 = Background<br/>1 = Foreground |
| ArtPreMultiplied | False | 7 | Bool (Bit 0) |  |
| ArtClip | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtGain | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtInvertKey | False | 12 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.SuperSource.SuperSourcePropertiesGetCommand

Payload length: 32

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ArtFillInput | False | 0-1 | Enum (VideoSource) | (See video source list) |
| ArtKeyInput | False | 2-3 | Enum (VideoSource) | (See video source list) |
| ArtOption | False | 4 | Enum (SuperSourceArtOption) | 0 = Background<br/>1 = Foreground |
| ArtPreMultiplied | False | 5 | Bool (Bit 0) |  |
| ArtClip | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtGain | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtInvertKey | False | 10 | Bool (Bit 0) |  |
| BorderEnabled | False | 11 | Bool (Bit 0) |  |
| BorderBevel | False | 12 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| BorderOuterWidth | False | 14-15 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderInnerWidth | False | 16-17 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderOuterSoftness | False | 18 | UInt | 0 - 100 |
| BorderInnerSoftness | False | 19 | UInt | 0 - 100 |
| BorderBevelSoftness | False | 20 | UInt | 0 - 100 |
| BorderBevelPosition | False | 21 | UInt | 0 - 100 |
| BorderHue | False | 22-23 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderSaturation | False | 24-25 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLuma | False | 26-27 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLightSourceDirection | False | 28-29 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderLightSourceAltitude | False | 30 | UInt<br/>Double Scale 1 | 0 - 100<br/>(0 - 100) |

### CSSc
#### Since V8_0
Implementation: LibAtem.Commands.SuperSource.SuperSourcePropertiesSetV8Command

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = ArtFillSource<br/>Bit 1 = ArtCutSource<br/>Bit 2 = ArtOption<br/>Bit 3 = ArtPreMultiplied<br/>Bit 4 = ArtClip<br/>Bit 5 = ArtGain<br/>Bit 6 = ArtInvertKey |
| SSrcId | True | 1 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| ArtFillSource | False | 2-3 | Enum (VideoSource) | (See video source list) |
| ArtCutSource | False | 4-5 | Enum (VideoSource) | (See video source list) |
| ArtOption | False | 6 | Enum (SuperSourceArtOption) | 0 = Background<br/>1 = Foreground |
| ArtPreMultiplied | False | 7 | Bool (Bit 0) |  |
| ArtClip | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtGain | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtInvertKey | False | 12 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.SuperSource.SuperSourcePropertiesSetCommand

Payload length: 36

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-3 | Enum (MaskFlags) | Bit 0 = ArtFillSource<br/>Bit 1 = ArtCutSource<br/>Bit 2 = ArtOption<br/>Bit 3 = ArtPreMultiplied<br/>Bit 4 = ArtClip<br/>Bit 5 = ArtGain<br/>Bit 6 = ArtInvertKey<br/>Bit 7 = BorderEnabled<br/>Bit 8 = BorderBevel<br/>Bit 9 = BorderOuterWidth<br/>Bit 10 = BorderInnerWidth<br/>Bit 11 = BorderOuterSoftness<br/>Bit 12 = BorderInnerSoftness<br/>Bit 13 = BorderBevelSoftness<br/>Bit 14 = BorderBevelPosition<br/>Bit 15 = BorderHue<br/>Bit 16 = BorderSaturation<br/>Bit 17 = BorderLuma<br/>Bit 18 = BorderLightSourceDirection<br/>Bit 19 = BorderLightSourceAltitude |
| ArtFillSource | False | 4-5 | Enum (VideoSource) | (See video source list) |
| ArtCutSource | False | 6-7 | Enum (VideoSource) | (See video source list) |
| ArtOption | False | 8 | Enum (SuperSourceArtOption) | 0 = Background<br/>1 = Foreground |
| ArtPreMultiplied | False | 9 | Bool (Bit 0) |  |
| ArtClip | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtGain | False | 12-13 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| ArtInvertKey | False | 14 | Bool (Bit 0) |  |
| BorderEnabled | False | 15 | Bool (Bit 0) |  |
| BorderBevel | False | 16 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| BorderOuterWidth | False | 18-19 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderInnerWidth | False | 20-21 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderOuterSoftness | False | 22 | UInt | 0 - 100 |
| BorderInnerSoftness | False | 23 | UInt | 0 - 100 |
| BorderBevelSoftness | False | 24 | UInt | 0 - 100 |
| BorderBevelPosition | False | 25 | UInt | 0 - 100 |
| BorderHue | False | 26-27 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderSaturation | False | 28-29 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLuma | False | 30-31 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLightSourceDirection | False | 32-33 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderLightSourceAltitude | False | 34 | UInt | 0 - 100 |

### DHVm
Implementation: LibAtem.Commands.Settings.DownConvertAvailableModesCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| CoreVideoMode | False | 0 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |
| DownConvertedMode | False | 1 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

### DcOt
Implementation: LibAtem.Commands.Settings.DownConvertModeGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| DownConvertMode | False | 0 | Enum (DownConvertMode) | 0 = CentreCut<br/>1 = Letterbox<br/>2 = Anamorphic |

### CDcO
Implementation: LibAtem.Commands.Settings.DownConvertModeSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| DownConvertMode | False | 0 | Enum (DownConvertMode) | 0 = CentreCut<br/>1 = Letterbox<br/>2 = Anamorphic |

### InPr
TODO - support generating this

### CInL
Implementation: LibAtem.Commands.Settings.InputPropertiesSetCommand

Payload length: 32

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = LongName<br/>Bit 1 = ShortName<br/>Bit 2 = ExternalPortType |
| Id | True | 2-3 | Enum (VideoSource) | (See video source list) |
| LongName | False | 4-23 | String |  |
| ShortName | False | 24-27 | String |  |
| ExternalPortType | False | 28-29 | Enum (ExternalPortTypeFlags) | Bit -∞ = Unknown<br/>Bit 0 = SDI<br/>Bit 1 = HDMI<br/>Bit 2 = Component<br/>Bit 3 = Composite<br/>Bit 4 = SVideo<br/>Bit 5 = Internal<br/>Bit 6 = XLR<br/>Bit 7 = AESEBU<br/>Bit 8 = RCA<br/>Bit 9 = TSJack |

### V3sl
Implementation: LibAtem.Commands.Settings.SDI3GLevelOutputGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SDI3GOutputLevel | False | 0 | Enum (SDI3GOutputLevel) | 0 = LevelB<br/>1 = LevelA |

### C3sl
Implementation: LibAtem.Commands.Settings.SDI3GLevelOutputSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SDI3GOutputLevel | False | 0 | Enum (SDI3GOutputLevel) | 0 = LevelB<br/>1 = LevelA |

### SPtM
Implementation: LibAtem.Commands.Settings.SerialPortModeCommand

Payload length: 4

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SerialMode | False | 0 | Enum (SerialMode) | 0 = None<br/>1 = PtzVisca<br/>2 = Gvg100 |

### VidM
Implementation: LibAtem.Commands.Settings.VideoModeGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| VideoMode | False | 0 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

### CVdM
Implementation: LibAtem.Commands.Settings.VideoModeSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| VideoMode | False | 0 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

### MvVM
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewerAvailableModesCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| CoreVideoMode | False | 0 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |
| MultiviewMode | False | 1 | Enum (VideoMode) | 0 = N525i5994NTSC<br/>1 = P625i50PAL<br/>2 = N525i5994169<br/>3 = P625i50169<br/>4 = P720p50<br/>5 = N720p5994<br/>6 = P1080i50<br/>7 = N1080i5994<br/>8 = N1080p2398<br/>9 = N1080p24<br/>10 = P1080p25<br/>11 = N1080p2997<br/>12 = P1080p50<br/>13 = N1080p5994<br/>14 = N4KHDp2398<br/>15 = N4KHDp24<br/>16 = P4KHDp25<br/>17 = N4KHDp2997<br/>18 = P4KHDp5000<br/>19 = N4KHDp5994<br/>20 = N8KHDp2398<br/>21 = N8KHDp24<br/>22 = P8KHDp25<br/>23 = N8KHDp2997<br/>24 = P8KHDp50<br/>25 = N8KHDp5994<br/>26 = N1080p30<br/>27 = N1080p60 |

### MvPr
#### Since V8_0
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewPropertiesGetV8Command

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 0 - 3 |
| Layout | False | 1 | Enum (MultiViewLayoutV8) | Bit -∞ = Default<br/>Bit 0 = TopLeftSmall<br/>Bit 1 = TopRightSmall<br/>Bit 1.584962500721156 = ProgramBottom<br/>Bit 2 = BottomLeftSmall<br/>Bit 2.321928094887362 = ProgramRight<br/>Bit 3 = BottomRightSmall<br/>Bit 3.321928094887362 = ProgramLeft<br/>Bit 3.584962500721156 = ProgramTop |
| SafeAreaEnabled | False | 2 | Bool (Bit 0) |  |
| ProgramPreviewSwapped | False | 3 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewPropertiesGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 0 - 1 |
| Layout | False | 1 | Enum (MultiViewLayout) | 0 = ProgramTop<br/>1 = ProgramBottom<br/>2 = ProgramLeft<br/>3 = ProgramRight |
| SafeAreaEnabled | False | 2 | Bool (Bit 0) |  |
| ProgramPreviewSwapped | False | 3 | Bool (Bit 0) |  |

### CMvP
#### Since V8_0
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewPropertiesSetV8Command

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Layout<br/>Bit 1 = ProgramPreviewSwapped |
| MultiviewIndex | True | 1 | UInt | 8 bits |
| Layout | False | 2 | Enum (MultiViewLayoutV8) | Bit -∞ = Default<br/>Bit 0 = TopLeftSmall<br/>Bit 1 = TopRightSmall<br/>Bit 1.584962500721156 = ProgramBottom<br/>Bit 2 = BottomLeftSmall<br/>Bit 2.321928094887362 = ProgramRight<br/>Bit 3 = BottomRightSmall<br/>Bit 3.321928094887362 = ProgramLeft<br/>Bit 3.584962500721156 = ProgramTop |
| ProgramPreviewSwapped | False | 3 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewPropertiesSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Layout<br/>Bit 1 = SafeAreaEnabled<br/>Bit 2 = ProgramPreviewSwapped |
| MultiviewIndex | True | 1 | UInt | 8 bits |
| Layout | False | 2 | Enum (MultiViewLayout) | 0 = ProgramTop<br/>1 = ProgramBottom<br/>2 = ProgramLeft<br/>3 = ProgramRight |
| SafeAreaEnabled | False | 3 | Bool (Bit 0) |  |
| ProgramPreviewSwapped | False | 4 | Bool (Bit 0) |  |

### VuMo
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewVuOpacityCommand

Payload length: 4

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| Opacity | False | 1 | UInt<br/>Double Scale 1 | 0 - 100<br/>(0 - 100) |

### MvIn
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewWindowInputGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| WindowIndex | True | 1 | UInt | 0 - 15 |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CMvI
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewWindowInputSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| WindowIndex | True | 1 | UInt | 0 - 15 |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### SaMw
#### Since V8_0
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewWindowSafeAreaCommand

Payload length: 4

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| WindowIndex | True | 1 | UInt | 0 - 15 |
| SafeAreaEnabled | False | 2 | Bool (Bit 0) |  |

### VuMC
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewWindowVuMeterGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| WindowIndex | True | 1 | UInt | 0 - 15 |
| VuEnabled | False | 2 | Bool (Bit 0) |  |

### VuMS
Implementation: LibAtem.Commands.Settings.Multiview.MultiviewWindowVuMeterSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MultiviewIndex | True | 0 | UInt | 8 bits |
| WindowIndex | True | 1 | UInt | 0 - 15 |
| VuEnabled | False | 2 | Bool (Bit 0) |  |

### RXCC
TODO - support generating this

### RXCP
TODO - support generating this

### RXSS
TODO - support generating this

### RXMS
Implementation: LibAtem.Commands.Settings.HyperDeck.HyperDeckSettingsGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Id | True | 0-1 | UInt | 0 - 4 |
| NetworkAddressBytes | False | 4-7 | Bytes |  |
| Input | False | 8-9 | Enum (VideoSource) | (See video source list) |
| AutoRoll | False | 10 | Bool (Bit 0) |  |
| AutoRollFrameDelay | False | 12 | UInt | 0 - 60 |

### CXMS
Implementation: LibAtem.Commands.Settings.HyperDeck.HyperDeckSettingsSetCommand

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = NetworkAddress<br/>Bit 1 = Source<br/>Bit 2 = AutoRoll<br/>Bit 3 = AutoRollFrameDelay |
| Id | True | 2-3 | UInt | 0 - 4 |
| NetworkAddress | False | 4-7 | Bytes |  |
| Source | False | 8-9 | Enum (VideoSource) | (See video source list) |
| AutoRoll | False | 10 | Bool (Bit 0) |  |
| AutoRollFrameDelay | False | 12 | UInt | 0 - 60 |

### FtbA
Implementation: LibAtem.Commands.MixEffects.FadeToBlackAutoCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### FCut
Implementation: LibAtem.Commands.MixEffects.FadeToBlackCutCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| IsFullyBlack | False | 1 | Bool (Bit 0) |  |

### FtbP
Implementation: LibAtem.Commands.MixEffects.FadeToBlackPropertiesGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 0 - 250 |

### FtbC
Implementation: LibAtem.Commands.MixEffects.FadeToBlackRateSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |

### FtbS
Implementation: LibAtem.Commands.MixEffects.FadeToBlackStateCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| IsFullyBlack | False | 1 | Bool (Bit 0) |  |
| InTransition | False | 2 | Bool (Bit 0) |  |
| RemainingFrames | False | 3 | UInt | 0 - 250 |

### DAut
Implementation: LibAtem.Commands.MixEffects.MixEffectAutoCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### DCut
Implementation: LibAtem.Commands.MixEffects.MixEffectCutCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### PrvI
Implementation: LibAtem.Commands.MixEffects.PreviewInputGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CPvI
Implementation: LibAtem.Commands.MixEffects.PreviewInputSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### PrgI
Implementation: LibAtem.Commands.MixEffects.ProgramInputGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CPgI
Implementation: LibAtem.Commands.MixEffects.ProgramInputSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 2-3 | Enum (VideoSource) | (See video source list) |

### TDpP
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionDipGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 8 bits |
| Input | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CTDp
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionDipSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Rate<br/>Bit 1 = Input |
| Index | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 2 | UInt | 0 - 250 |
| Input | False | 4-5 | Enum (VideoSource) | (See video source list) |

### TDvP
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionDVEGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 1 - 250 |
| LogoRate | False | 2 | UInt | 1 - 250 |
| Style | False | 3 | Enum (DVEEffect) | 0 = SwooshTopLeft<br/>1 = SwooshTop<br/>2 = SwooshTopRight<br/>3 = SwooshLeft<br/>4 = SwooshRight<br/>5 = SwooshBottomLeft<br/>6 = SwooshBottom<br/>7 = SwooshBottomRight<br/>8 = SpinCWTopLeft<br/>9 = SpinCWTopRight<br/>10 = SpinCWBottomLeft<br/>11 = SpinCWBottomRight<br/>12 = SpinCCWTopLeft<br/>13 = SpinCCWTopRight<br/>14 = SpinCCWBottomLeft<br/>15 = SpinCCWBottomRight<br/>16 = SqueezeTopLeft<br/>17 = SqueezeTop<br/>18 = SqueezeTopRight<br/>19 = SqueezeLeft<br/>20 = SqueezeRight<br/>21 = SqueezeBottomLeft<br/>22 = SqueezeBottom<br/>23 = SqueezeBottomRight<br/>24 = PushTopLeft<br/>25 = PushTop<br/>26 = PushTopRight<br/>27 = PushLeft<br/>28 = PushRight<br/>29 = PushBottomLeft<br/>30 = PushBottom<br/>31 = PushBottomRight<br/>32 = GraphicCWSpin<br/>33 = GraphicCCWSpin<br/>34 = GraphicLogoWipe |
| FillSource | False | 4-5 | Enum (VideoSource) | (See video source list) |
| KeySource | False | 6-7 | Enum (VideoSource) | (See video source list) |
| EnableKey | False | 8 | Bool (Bit 0) |  |
| PreMultiplied | False | 9 | Bool (Bit 0) |  |
| Clip | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 12-13 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| InvertKey | False | 14 | Bool (Bit 0) |  |
| Reverse | False | 15 | Bool (Bit 0) |  |
| FlipFlop | False | 16 | Bool (Bit 0) |  |

### CTDv
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionDVESetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Rate<br/>Bit 1 = LogoRate<br/>Bit 2 = Style<br/>Bit 3 = FillSource<br/>Bit 4 = KeySource<br/>Bit 5 = EnableKey<br/>Bit 6 = PreMultiplied<br/>Bit 7 = Clip<br/>Bit 8 = Gain<br/>Bit 9 = InvertKey<br/>Bit 10 = Reverse<br/>Bit 11 = FlipFlop |
| Index | True | 2 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 3 | UInt | 1 - 250 |
| LogoRate | False | 4 | UInt | 1 - 250 |
| Style | False | 5 | Enum (DVEEffect) | 0 = SwooshTopLeft<br/>1 = SwooshTop<br/>2 = SwooshTopRight<br/>3 = SwooshLeft<br/>4 = SwooshRight<br/>5 = SwooshBottomLeft<br/>6 = SwooshBottom<br/>7 = SwooshBottomRight<br/>8 = SpinCWTopLeft<br/>9 = SpinCWTopRight<br/>10 = SpinCWBottomLeft<br/>11 = SpinCWBottomRight<br/>12 = SpinCCWTopLeft<br/>13 = SpinCCWTopRight<br/>14 = SpinCCWBottomLeft<br/>15 = SpinCCWBottomRight<br/>16 = SqueezeTopLeft<br/>17 = SqueezeTop<br/>18 = SqueezeTopRight<br/>19 = SqueezeLeft<br/>20 = SqueezeRight<br/>21 = SqueezeBottomLeft<br/>22 = SqueezeBottom<br/>23 = SqueezeBottomRight<br/>24 = PushTopLeft<br/>25 = PushTop<br/>26 = PushTopRight<br/>27 = PushLeft<br/>28 = PushRight<br/>29 = PushBottomLeft<br/>30 = PushBottom<br/>31 = PushBottomRight<br/>32 = GraphicCWSpin<br/>33 = GraphicCCWSpin<br/>34 = GraphicLogoWipe |
| FillSource | False | 6-7 | Enum (VideoSource) | (See video source list) |
| KeySource | False | 8-9 | Enum (VideoSource) | (See video source list) |
| EnableKey | False | 10 | Bool (Bit 0) |  |
| PreMultiplied | False | 11 | Bool (Bit 0) |  |
| Clip | False | 12-13 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 14-15 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| InvertKey | False | 16 | Bool (Bit 0) |  |
| Reverse | False | 17 | Bool (Bit 0) |  |
| FlipFlop | False | 18 | Bool (Bit 0) |  |

### TMxP
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionMixGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 8 bits |

### CTMx
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionMixSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 0 - 250 |

### TrPs
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPositionGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| InTransition | False | 1 | Bool (Bit 0) |  |
| RemainingFrames | False | 2 | UInt | 0 - 250 |
| HandlePosition | False | 4-5 | UInt<br/>Double Scale 10000 | 0 - 9999<br/>(0 - 0.9999) |

### CTPs
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPositionSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| HandlePosition | False | 2-3 | UInt<br/>Double Scale 10000 | 0 - 9999<br/>(0 - 0.9999) |

### TrPr
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPreviewGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreviewTransition | False | 1 | Bool (Bit 0) |  |

### CTPr
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPreviewSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreviewTransition | False | 1 | Bool (Bit 0) |  |

### TrSS
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPropertiesGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Style | False | 1 | Enum (TransitionStyle) | 0 = Mix<br/>1 = Dip<br/>2 = Wipe<br/>3 = DVE<br/>4 = Stinger |
| Selection | False | 2 | Enum (TransitionLayer) | Bit 0 = Background<br/>Bit 1 = Key1<br/>Bit 2 = Key2<br/>Bit 3 = Key3<br/>Bit 4 = Key4 |
| NextStyle | False | 3 | Enum (TransitionStyle) | 0 = Mix<br/>1 = Dip<br/>2 = Wipe<br/>3 = DVE<br/>4 = Stinger |
| NextSelection | False | 4 | Enum (TransitionLayer) | Bit 0 = Background<br/>Bit 1 = Key1<br/>Bit 2 = Key2<br/>Bit 3 = Key3<br/>Bit 4 = Key4 |

### CTTp
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionPropertiesSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = NextStyle<br/>Bit 1 = NextSelection |
| Index | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| NextStyle | False | 2 | Enum (TransitionStyle) | 0 = Mix<br/>1 = Dip<br/>2 = Wipe<br/>3 = DVE<br/>4 = Stinger |
| NextSelection | False | 3 | Enum (TransitionLayer) | Bit 0 = Background<br/>Bit 1 = Key1<br/>Bit 2 = Key2<br/>Bit 3 = Key3<br/>Bit 4 = Key4 |

### TStP
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionStingerGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 1 | Enum (StingerSource) | 0 = None<br/>1 = MediaPlayer1<br/>2 = MediaPlayer2<br/>3 = MediaPlayer3<br/>4 = MediaPlayer4 |
| PreMultipliedKey | False | 2 | Bool (Bit 0) |  |
| Clip | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 8 | Bool (Bit 0) |  |
| Preroll | False | 10-11 | UInt | 16 bits |
| ClipDuration | False | 12-13 | UInt | 16 bits |
| TriggerPoint | False | 14-15 | UInt | 16 bits |
| MixRate | False | 16-17 | UInt | 16 bits |

### CTSt
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionStingerSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Source<br/>Bit 1 = PreMultipliedKey<br/>Bit 2 = Clip<br/>Bit 3 = Gain<br/>Bit 4 = Invert<br/>Bit 5 = Preroll<br/>Bit 6 = ClipDuration<br/>Bit 7 = TriggerPoint<br/>Bit 8 = MixRate<br/>Bit 8.906890595608518 = Durations |
| Index | True | 2 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Source | False | 3 | Enum (StingerSource) | 0 = None<br/>1 = MediaPlayer1<br/>2 = MediaPlayer2<br/>3 = MediaPlayer3<br/>4 = MediaPlayer4 |
| PreMultipliedKey | False | 4 | Bool (Bit 0) |  |
| Clip | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 10 | Bool (Bit 0) |  |
| Preroll | False | 12-13 | UInt | 16 bits |
| ClipDuration | False | 14-15 | UInt | 16 bits |
| TriggerPoint | False | 16-17 | UInt | 16 bits |
| MixRate | False | 18-19 | UInt | 16 bits |

### TWpP
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionWipeGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 1 - 250 |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| BorderWidth | False | 4-5 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| BorderInput | False | 6-7 | Enum (VideoSource) | (See video source list) |
| Symmetry | False | 8-9 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| BorderSoftness | False | 10-11 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| XPosition | False | 12-13 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| YPosition | False | 14-15 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| ReverseDirection | False | 16 | Bool (Bit 0) |  |
| FlipFlop | False | 17 | Bool (Bit 0) |  |

### CTWp
Implementation: LibAtem.Commands.MixEffects.Transition.TransitionWipeSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = Rate<br/>Bit 1 = Pattern<br/>Bit 2 = BorderWidth<br/>Bit 3 = BorderInput<br/>Bit 4 = Symmetry<br/>Bit 5 = BorderSoftness<br/>Bit 6 = XPosition<br/>Bit 7 = YPosition<br/>Bit 8 = ReverseDirection<br/>Bit 9 = FlipFlop |
| Index | True | 2 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 3 | UInt | 1 - 250 |
| Pattern | False | 4 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| BorderWidth | False | 6-7 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| BorderInput | False | 8-9 | Enum (VideoSource) | (See video source list) |
| Symmetry | False | 10-11 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| BorderSoftness | False | 12-13 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| XPosition | False | 14-15 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| YPosition | False | 16-17 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| ReverseDirection | False | 18 | Bool (Bit 0) |  |
| FlipFlop | False | 19 | Bool (Bit 0) |  |

### KACk
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyAdvancedChromaPropertiesGetCommand

Payload length: 24

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| ForegroundLevel | False | 2-3 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BackgroundLevel | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| KeyEdge | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| SpillSuppression | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| FlareSuppression | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Brightness | False | 12-13 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Contrast | False | 14-15 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Saturation | False | 16-17 | UInt<br/>Double Scale 10 | 0 - 2000<br/>(0 - 200) |
| Red | False | 18-19 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Green | False | 20-21 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Blue | False | 22-23 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |

### CACK
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyAdvancedChromaPropertiesSetCommand

Payload length: 28

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = ForegroundLevel<br/>Bit 1 = BackgroundLevel<br/>Bit 2 = KeyEdge<br/>Bit 3 = SpillSuppression<br/>Bit 4 = FlareSuppression<br/>Bit 5 = Brightness<br/>Bit 6 = Contrast<br/>Bit 7 = Saturation<br/>Bit 8 = Red<br/>Bit 9 = Green<br/>Bit 10 = Blue |
| MixEffectIndex | True | 2 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 3 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| ForegroundLevel | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BackgroundLevel | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| KeyEdge | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| SpillSuppression | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| FlareSuppression | False | 12-13 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Brightness | False | 14-15 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Contrast | False | 16-17 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Saturation | False | 18-19 | UInt<br/>Double Scale 10 | 0 - 2000<br/>(0 - 200) |
| Red | False | 20-21 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Green | False | 22-23 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |
| Blue | False | 24-25 | Int<br/>Double Scale 10 | -1000 - 1000<br/>(-100 - 100) |

### RACK
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyAdvancedChromaResetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyAdjustments | False | 3 | Bool (Bit 0) |  |
| ChromaCorrection | False | 3 | Bool (Bit 1) |  |
| ColorAdjustments | False | 3 | Bool (Bit 2) |  |

### KACC
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyAdvancedChromaSampleGetCommand

Payload length: 16

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| EnableCursor | False | 2 | Bool (Bit 0) |  |
| Preview | False | 3 | Bool (Bit 0) |  |
| CursorX | False | 4-5 | Int<br/>Double Scale 1000 | -15383 - 15383<br/>(-15.383 - 15.383) |
| CursorY | False | 6-7 | Int<br/>Double Scale 1000 | -8383 - 8383<br/>(-8.383 - 8.383) |
| CursorSize | False | 8-9 | UInt<br/>Double Scale 100 | 625 - 9925<br/>(6.25 - 99.25) |
| SampledY | False | 10-11 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| SampledCb | False | 12-13 | Int<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| SampledCr | False | 14-15 | Int<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |

### CACC
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyAdvancedChromaSampleSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = EnableCursor<br/>Bit 1 = Preview<br/>Bit 2 = CursorX<br/>Bit 3 = CursorY<br/>Bit 4 = CursorSize<br/>Bit 5 = SampledY<br/>Bit 6 = SampledCb<br/>Bit 7 = SampledCr |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| EnableCursor | False | 3 | Bool (Bit 0) |  |
| Preview | False | 4 | Bool (Bit 0) |  |
| CursorX | False | 6-7 | Int<br/>Double Scale 1000 | -15383 - 15383<br/>(-15.383 - 15.383) |
| CursorY | False | 8-9 | Int<br/>Double Scale 1000 | -8383 - 8383<br/>(-8.383 - 8.383) |
| CursorSize | False | 10-11 | UInt<br/>Double Scale 100 | 625 - 9925<br/>(6.25 - 99.25) |
| SampledY | False | 12-13 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| SampledCb | False | 14-15 | Int<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| SampledCr | False | 16-17 | Int<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |

### KeCk
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyChromaGetCommand

Payload length: 12

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Hue | False | 2-3 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Gain | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| YSuppress | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Lift | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Narrow | False | 10 | Bool (Bit 0) |  |

### CKCk
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyChromaSetCommand

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Hue<br/>Bit 1 = Gain<br/>Bit 2 = YSuppress<br/>Bit 3 = Lift<br/>Bit 4 = Narrow |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Hue | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| YSuppress | False | 8-9 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Lift | False | 10-11 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Narrow | False | 12 | Bool (Bit 0) |  |

### CKeC
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyCutSourceSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| CutSource | False | 2-3 | Enum (VideoSource) | (See video source list) |

### KeDV
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyDVEGetCommand

Payload length: 60

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SizeX | False | 4-7 | UInt<br/>Double Scale 1000 | 0 - 99990<br/>(0 - 99.99) |
| SizeY | False | 8-11 | UInt<br/>Double Scale 1000 | 0 - 99990<br/>(0 - 99.99) |
| PositionX | False | 12-15 | Int<br/>Double Scale 1000 | -1000000 - 1000000<br/>(-1000 - 1000) |
| PositionY | False | 16-19 | Int<br/>Double Scale 1000 | -1000000 - 1000000<br/>(-1000 - 1000) |
| Rotation | False | 20-23 | Int<br/>Double Scale 10 | -332230 - 332230<br/>(-33223 - 33223) |
| BorderEnabled | False | 24 | Bool (Bit 0) |  |
| BorderShadowEnabled | False | 25 | Bool (Bit 0) |  |
| BorderBevel | False | 26 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| BorderOuterWidth | False | 28-29 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderInnerWidth | False | 30-31 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderOuterSoftness | False | 32 | UInt | 0 - 100 |
| BorderInnerSoftness | False | 33 | UInt | 0 - 100 |
| BorderBevelSoftness | False | 34 | UInt | 0 - 100 |
| BorderBevelPosition | False | 35 | UInt | 0 - 100 |
| BorderOpacity | False | 36 | UInt | 0 - 100 |
| BorderHue | False | 38-39 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderSaturation | False | 40-41 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLuma | False | 42-43 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| LightSourceDirection | False | 44-45 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| LightSourceAltitude | False | 46 | UInt | 0 - 100 |
| MaskEnabled | False | 47 | Bool (Bit 0) |  |
| MaskTop | False | 48-49 | UInt<br/>Double Scale 1000 | 0 - 38000<br/>(0 - 38) |
| MaskBottom | False | 50-51 | UInt<br/>Double Scale 1000 | 0 - 38000<br/>(0 - 38) |
| MaskLeft | False | 52-53 | UInt<br/>Double Scale 1000 | 0 - 52000<br/>(0 - 52) |
| MaskRight | False | 54-55 | UInt<br/>Double Scale 1000 | 0 - 52000<br/>(0 - 52) |
| Rate | False | 56 | UInt | 1 - 250 |

### CKDV
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyDVESetCommand

Payload length: 64

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-3 | Enum (MaskFlags) | Bit 0 = SizeX<br/>Bit 1 = SizeY<br/>Bit 2 = PositionX<br/>Bit 3 = PositionY<br/>Bit 4 = Rotation<br/>Bit 5 = BorderEnabled<br/>Bit 6 = BorderShadowEnabled<br/>Bit 7 = BorderBevel<br/>Bit 8 = BorderOuterWidth<br/>Bit 9 = BorderInnerWidth<br/>Bit 10 = BorderOuterSoftness<br/>Bit 11 = BorderInnerSoftness<br/>Bit 12 = BorderBevelSoftness<br/>Bit 13 = BorderBevelPosition<br/>Bit 14 = BorderOpacity<br/>Bit 15 = BorderHue<br/>Bit 16 = BorderSaturation<br/>Bit 17 = BorderLuma<br/>Bit 18 = LightSourceDirection<br/>Bit 19 = LightSourceAltitude<br/>Bit 20 = MaskEnabled<br/>Bit 21 = MaskTop<br/>Bit 22 = MaskBottom<br/>Bit 23 = MaskLeft<br/>Bit 24 = MaskRight<br/>Bit 25 = Rate |
| MixEffectIndex | True | 4 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 5 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SizeX | False | 8-11 | UInt<br/>Double Scale 1000 | 0 - 99990<br/>(0 - 99.99) |
| SizeY | False | 12-15 | UInt<br/>Double Scale 1000 | 0 - 99990<br/>(0 - 99.99) |
| PositionX | False | 16-19 | Int<br/>Double Scale 1000 | -1000 - 1000<br/>(-1 - 1) |
| PositionY | False | 20-23 | Int<br/>Double Scale 1000 | -1000 - 1000<br/>(-1 - 1) |
| Rotation | False | 24-27 | Int<br/>Double Scale 1000 | -1000 - 1000<br/>(-1 - 1) |
| BorderEnabled | False | 28 | Bool (Bit 0) |  |
| BorderShadowEnabled | False | 29 | Bool (Bit 0) |  |
| BorderBevel | False | 30 | Enum (BorderBevel) | 0 = None<br/>1 = InOut<br/>2 = In<br/>3 = Out |
| BorderOuterWidth | False | 32-33 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderInnerWidth | False | 34-35 | UInt<br/>Double Scale 100 | 0 - 1600<br/>(0 - 16) |
| BorderOuterSoftness | False | 36 | UInt | 0 - 100 |
| BorderInnerSoftness | False | 37 | UInt | 0 - 100 |
| BorderBevelSoftness | False | 38 | UInt | 0 - 100 |
| BorderBevelPosition | False | 39 | UInt | 0 - 100 |
| BorderOpacity | False | 40 | UInt | 0 - 100 |
| BorderHue | False | 42-43 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| BorderSaturation | False | 44-45 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| BorderLuma | False | 46-47 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| LightSourceDirection | False | 48-49 | UInt<br/>Double Scale 10 | 0 - 3599<br/>(0 - 359.9) |
| LightSourceAltitude | False | 50 | UInt | 0 - 100 |
| MaskEnabled | False | 51 | Bool (Bit 0) |  |
| MaskTop | False | 52-53 | UInt<br/>Double Scale 1000 | 0 - 38000<br/>(0 - 38) |
| MaskBottom | False | 54-55 | UInt<br/>Double Scale 1000 | 0 - 38000<br/>(0 - 38) |
| MaskLeft | False | 56-57 | UInt<br/>Double Scale 1000 | 0 - 52000<br/>(0 - 52) |
| MaskRight | False | 58-59 | UInt<br/>Double Scale 1000 | 0 - 52000<br/>(0 - 52) |
| Rate | False | 60 | UInt | 1 - 250 |

### CKeF
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyFillSourceSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| FillSource | False | 2-3 | Enum (VideoSource) | (See video source list) |

### KKFP
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyFlyKeyframeGetCommand

Payload length: 52

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyFrame | True | 2 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |
| SizeX | False | 4-7 | UInt<br/>Double Scale 1000 | 0 - 32767999<br/>(0 - 32767.999) |
| SizeY | False | 8-11 | UInt<br/>Double Scale 1000 | 0 - 32767999<br/>(0 - 32767.999) |
| PositionX | False | 12-15 | Int<br/>Double Scale 1000 | -32768000 - 32768000<br/>(-32768 - 32768) |
| PositionY | False | 16-19 | Int<br/>Double Scale 1000 | -32768000 - 32768000<br/>(-32768 - 32768) |
| Rotation | False | 20-23 | Int<br/>Double Scale 10 | -327680 - 327680<br/>(-32768 - 32768) |
| OuterWidth | False | 24-25 | UInt<br/>Double Scale 100 | 0 - 65535<br/>(0 - 655.35) |
| InnerWidth | False | 26-27 | UInt<br/>Double Scale 100 | 0 - 65535<br/>(0 - 655.35) |
| OuterSoftness | False | 28 | UInt | 0 - 254 |
| InnerSoftness | False | 29 | UInt | 0 - 254 |
| BevelSoftness | False | 30 | UInt | 0 - 254 |
| BevelPosition | False | 31 | UInt | 0 - 254 |
| BorderOpacity | False | 32 | UInt | 0 - 255 |
| BorderHue | False | 34-35 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| BorderSaturation | False | 36-37 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| BorderLuma | False | 38-39 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| LightSourceDirection | False | 40-41 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| LightSourceAltitude | False | 42 | UInt | 0 - 254 |
| MaskTop | False | 44-45 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 46-47 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 48-49 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 50-51 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### CKFP
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyFlyKeyframeSetCommand

Payload length: 56

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-3 | Enum (MaskFlags) | Bit 0 = SizeX<br/>Bit 1 = SizeY<br/>Bit 2 = PositionX<br/>Bit 3 = PositionY<br/>Bit 4 = Rotation<br/>Bit 5 = OuterWidth<br/>Bit 6 = InnerWidth<br/>Bit 7 = OuterSoftness<br/>Bit 8 = InnerSoftness<br/>Bit 9 = BevelSoftness<br/>Bit 10 = BevelPosition<br/>Bit 11 = BorderOpacity<br/>Bit 12 = BorderHue<br/>Bit 13 = BorderSaturation<br/>Bit 14 = BorderLuma<br/>Bit 15 = LightSourceDirection<br/>Bit 16 = LightSourceAltitude<br/>Bit 17 = MaskTop<br/>Bit 18 = MaskBottom<br/>Bit 19 = MaskLeft<br/>Bit 20 = MaskRight |
| MixEffectIndex | True | 4 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 5 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyFrame | True | 6 | Enum (FlyKeyKeyFrameId) | 1 = One<br/>2 = Two |
| SizeX | False | 8-11 | UInt<br/>Double Scale 1000 | 0 - 32767999<br/>(0 - 32767.999) |
| SizeY | False | 12-15 | UInt<br/>Double Scale 1000 | 0 - 32767999<br/>(0 - 32767.999) |
| PositionX | False | 16-19 | Int<br/>Double Scale 1000 | -32768000 - 32768000<br/>(-32768 - 32768) |
| PositionY | False | 20-23 | Int<br/>Double Scale 1000 | -32768000 - 32768000<br/>(-32768 - 32768) |
| Rotation | False | 24-27 | Int<br/>Double Scale 10 | -327680 - 327680<br/>(-32768 - 32768) |
| OuterWidth | False | 28-29 | UInt<br/>Double Scale 100 | 0 - 65535<br/>(0 - 655.35) |
| InnerWidth | False | 30-31 | UInt<br/>Double Scale 100 | 0 - 65535<br/>(0 - 655.35) |
| OuterSoftness | False | 32 | UInt | 0 - 254 |
| InnerSoftness | False | 33 | UInt | 0 - 254 |
| BevelSoftness | False | 34 | UInt | 0 - 254 |
| BevelPosition | False | 35 | UInt | 0 - 254 |
| BorderOpacity | False | 36 | UInt | 0 - 255 |
| BorderHue | False | 38-39 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| BorderSaturation | False | 40-41 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| BorderLuma | False | 42-43 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| LightSourceDirection | False | 44-45 | UInt<br/>Double Scale 10 | 0 - 65535<br/>(0 - 6553.5) |
| LightSourceAltitude | False | 46 | UInt | 0 - 254 |
| MaskTop | False | 48-49 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 50-51 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 52-53 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 54-55 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### KeFS
TODO - support generating this

### KeLm
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyLumaGetCommand

Payload length: 12

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultiplied | False | 2 | Bool (Bit 0) |  |
| Clip | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 8 | Bool (Bit 0) |  |

### CKLm
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyLumaSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = PreMultiplied<br/>Bit 1 = Clip<br/>Bit 2 = Gain<br/>Bit 3 = Invert |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultiplied | False | 3 | Bool (Bit 0) |  |
| Clip | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 8 | Bool (Bit 0) |  |

### CKMs
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyMaskSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = MaskEnabled<br/>Bit 1 = MaskTop<br/>Bit 2 = MaskBottom<br/>Bit 3 = MaskLeft<br/>Bit 4 = MaskRight |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| MaskEnabled | False | 3 | Bool (Bit 0) |  |
| MaskTop | False | 4-5 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 6-7 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 8-9 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 10-11 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### KeOn
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyOnAirGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 2 | Bool (Bit 0) |  |

### CKOn
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyOnAirSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 2 | Bool (Bit 0) |  |

### KePt
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyPatternGetCommand

Payload length: 16

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Pattern | False | 2 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| Size | False | 4-5 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| Symmetry | False | 6-7 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| Softness | False | 8-9 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| XPosition | False | 10-11 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| YPosition | False | 12-13 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| Inverse | False | 14 | Bool (Bit 0) |  |

### CKPt
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyPatternSetCommand

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Pattern<br/>Bit 1 = Size<br/>Bit 2 = Symmetry<br/>Bit 3 = Softness<br/>Bit 4 = XPosition<br/>Bit 5 = YPosition<br/>Bit 6 = Inverse |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Pattern | False | 3 | Enum (Pattern) | 0 = LeftToRightBar<br/>1 = TopToBottomBar<br/>2 = HorizontalBarnDoor<br/>3 = VerticalBarnDoor<br/>4 = CornersInFourBox<br/>5 = RectangleIris<br/>6 = DiamondIris<br/>7 = CircleIris<br/>8 = TopLeftBox<br/>9 = TopRightBox<br/>10 = BottomRightBox<br/>11 = BottomLeftBox<br/>12 = TopCentreBox<br/>13 = RightCentreBox<br/>14 = BottomCentreBox<br/>15 = LeftCentreBox<br/>16 = TopLeftDiagonal<br/>17 = TopRightDiagonal |
| Size | False | 4-5 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| Symmetry | False | 6-7 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| Softness | False | 8-9 | UInt<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| XPosition | False | 10-11 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| YPosition | False | 12-13 | UInt<br/>Double Scale 10000 | 0 - 10000<br/>(0 - 1) |
| Inverse | False | 14 | Bool (Bit 0) |  |

### KeBP
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyPropertiesGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectIndex | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 1 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyType | False | 2 | Enum (MixEffectKeyType) | 0 = Luma<br/>1 = Chroma<br/>2 = Pattern<br/>3 = DVE |
| FlyEnabled | False | 5 | Bool (Bit 0) |  |
| FillSource | False | 6-7 | Enum (VideoSource) | (See video source list) |
| CutSource | False | 8-9 | Enum (VideoSource) | (See video source list) |
| MaskEnabled | False | 10 | Bool (Bit 0) |  |
| MaskTop | False | 12-13 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 14-15 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 16-17 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 18-19 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### CKTp
Implementation: LibAtem.Commands.MixEffects.Key.MixEffectKeyTypeSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = KeyType<br/>Bit 1 = FlyEnabled |
| MixEffectIndex | True | 1 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyerIndex | True | 2 | Enum (UpstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyType | False | 3 | Enum (MixEffectKeyType) | 0 = Luma<br/>1 = Chroma<br/>2 = Pattern<br/>3 = DVE |
| FlyEnabled | False | 4 | Bool (Bit 0) |  |

### RCPS
Implementation: LibAtem.Commands.Media.MediaPlayerClipStatusGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Playing | False | 1 | Bool (Bit 0) |  |
| Loop | False | 2 | Bool (Bit 0) |  |
| AtBeginning | False | 3 | Bool (Bit 0) |  |
| ClipFrame | False | 4-5 | UInt | 16 bits |

### SCPS
Implementation: LibAtem.Commands.Media.MediaPlayerClipStatusSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Playing<br/>Bit 1 = Loop<br/>Bit 2 = AtBeginning<br/>Bit 3 = ClipFrame |
| Index | True | 1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Playing | False | 2 | Bool (Bit 0) |  |
| Loop | False | 3 | Bool (Bit 0) |  |
| AtBeginning | False | 4 | Bool (Bit 0) |  |
| ClipFrame | False | 6-7 | UInt | 16 bits |

### MPCE
Implementation: LibAtem.Commands.Media.MediaPlayerSourceGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SourceType | False | 1 | Enum (MediaPlayerSource) | 1 = Still<br/>2 = Clip |
| SourceIndex | False | 2 | UInt | 8 bits |

### MPSS
Implementation: LibAtem.Commands.Media.MediaPlayerSourceSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = SourceType<br/>Bit 1 = StillIndex<br/>Bit 2 = ClipIndex |
| Index | True | 1 | Enum (MediaPlayerId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| SourceType | False | 2 | Enum (MediaPlayerSource) | 1 = Still<br/>2 = Clip |
| ClipIndex | False | 3 | UInt | 8 bits |
| StillIndex | False | 4 | UInt | 8 bits |

### MPAS
Implementation: LibAtem.Commands.Media.MediaPoolAudioDescriptionCommand

Payload length: 84

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 8 bits |
| IsUsed | False | 1 | Bool (Bit 0) |  |
| Hash | False | 2-17 | Bytes |  |
| Name | False | 18-81 | String |  |

### Capt
Implementation: LibAtem.Commands.Media.MediaPoolCaptureStillCommand

Payload length: 0

Direction: ToServer

Command has no properties

### CMPA
Implementation: LibAtem.Commands.Media.MediaPoolClearAudioCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 8 bits |

### CMPC
Implementation: LibAtem.Commands.Media.MediaPoolClearClipCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 8 bits |

### CSTL
Implementation: LibAtem.Commands.Media.MediaPoolClearStillCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 8 bits |

### MPCS
Implementation: LibAtem.Commands.Media.MediaPoolClipDescriptionCommand

Payload length: 68

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | UInt | 8 bits |
| IsUsed | False | 1 | Bool (Bit 0) |  |
| Name | False | 2-65 | String |  |
| FrameCount | False | 66-67 | UInt | 16 bits |

### MPfe
Implementation: LibAtem.Commands.Media.MediaPoolFrameDescriptionCommand

Payload length: -1

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Bank | True | 0 | Enum (MediaPoolFileType) | 0 = Still<br/>1 = Clip1<br/>2 = Clip2 |
| Index | True | 2-3 | UInt | 16 bits |
| IsUsed | False | 4 | Bool (Bit 0) |  |
| Hash | False | 5-20 | Bytes |  |
| Filename | False | 22-23<br/>?? | Length<br/>String | 0 - 20<br/>  |

### SMPC
Implementation: LibAtem.Commands.Media.MediaPoolSetClipCommand

Payload length: 68

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| B0 | False | 0 | UInt | 8 bits |
| Index | True | 1 | UInt | 8 bits |
| Name | False | 2-45 | String |  |
| Frames | False | 66-67 | UInt | 16 bits |

### MPSp
TODO - support generating this

### CMPS
TODO - support generating this

### MAct
Implementation: LibAtem.Commands.Macro.MacroActionCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |
| Action | False | 2 | Enum (MacroAction) | 0 = Run<br/>1 = Stop<br/>2 = StopRecord<br/>3 = InsertUserWait<br/>4 = Continue<br/>5 = Delete |

### MSlp
Implementation: LibAtem.Commands.Macro.MacroAddTimedPauseCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Frames | False | 2-3 | UInt | 0 - 2500 |

### MPrp
Implementation: LibAtem.Commands.Macro.MacroPropertiesGetCommand

Payload length: -1

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |
| IsUsed | False | 2 | Bool (Bit 0) |  |
| Name | False | 4-5<br/>?? | Length<br/>String | 0 - 128<br/>  |
| Description | False | 6-7<br/>?? | Length<br/>String | 0 - 128<br/>  |

### CMPr
Implementation: LibAtem.Commands.Macro.MacroPropertiesSetCommand

Payload length: -1

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Name<br/>Bit 1 = Description |
| Index | True | 2-3 | UInt | 16 bits |
| Name | False | 4-5<br/>?? | Length<br/>String | 0 - 128<br/>  |
| Description | False | 6-7<br/>?? | Length<br/>String | 0 - 128<br/>  |

### MSRc
Implementation: LibAtem.Commands.Macro.MacroRecordCommand

Payload length: -1

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |
| Name | False | 2-3<br/>?? | Length<br/>String | 0 - 128<br/>  |
| Description | False | 4-5<br/>?? | Length<br/>String | 0 - 128<br/>  |

### MRcS
Implementation: LibAtem.Commands.Macro.MacroRecordingStatusGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| IsRecording | False | 0 | Bool (Bit 0) |  |
| Index | False | 2-3 | UInt | 16 bits |

### MRCP
Implementation: LibAtem.Commands.Macro.MacroRunStatusSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | 1 = Loop |
| Loop | False | 1 | Bool (Bit 0) |  |

### MRPr
Implementation: LibAtem.Commands.Macro.MacroRunStatusGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| IsRunning | False | 0 | Bool (Bit 0) |  |
| IsWaiting | False | 0 | Bool (Bit 1) |  |
| Loop | False | 1 | Bool (Bit 0) |  |
| Index | False | 2-3 | UInt | 16 bits |

### DDsA
#### Since V8_0
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyAutoV8Command

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = IsTowardsOnAir |
| Index | True | 1 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| IsTowardsOnAir | False | 2 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyAutoCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |

### CDsC
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyCutSourceSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| CutSource | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CDsF
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyFillSourceSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| FillSource | False | 2-3 | Enum (VideoSource) | (See video source list) |

### CDsG
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyGeneralSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = PreMultipliedKey<br/>Bit 1 = Clip<br/>Bit 2 = Gain<br/>Bit 3 = Invert |
| Index | True | 1 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| PreMultipliedKey | False | 2 | Bool (Bit 0) |  |
| Clip | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 8 | Bool (Bit 0) |  |

### CDsM
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyMaskSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = MaskEnabled<br/>Bit 1 = MaskTop<br/>Bit 2 = MaskBottom<br/>Bit 3 = MaskLeft<br/>Bit 4 = MaskRight |
| Index | True | 1 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| MaskEnabled | False | 2 | Bool (Bit 0) |  |
| MaskTop | False | 4-5 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 6-7 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 8-9 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 10-11 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### CDsL
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyOnAirSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 1 | Bool (Bit 0) |  |

### DskP
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyPropertiesGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Tie | False | 1 | Bool (Bit 0) |  |
| Rate | False | 2 | UInt | 0 - 250 |
| PreMultipliedKey | False | 3 | Bool (Bit 0) |  |
| Clip | False | 4-5 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Gain | False | 6-7 | UInt<br/>Double Scale 10 | 0 - 1000<br/>(0 - 100) |
| Invert | False | 8 | Bool (Bit 0) |  |
| MaskEnabled | False | 9 | Bool (Bit 0) |  |
| MaskTop | False | 10-11 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskBottom | False | 12-13 | Int<br/>Double Scale 1000 | -9000 - 9000<br/>(-9 - 9) |
| MaskLeft | False | 14-15 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |
| MaskRight | False | 16-17 | Int<br/>Double Scale 1000 | -16000 - 16000<br/>(-16 - 16) |

### CDsR
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyRateSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Rate | False | 1 | UInt | 0 - 250 |

### DskB
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeySourceGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| FillSource | False | 2-3 | Enum (VideoSource) | (See video source list) |
| CutSource | False | 4-5 | Enum (VideoSource) | (See video source list) |

### DskS
#### Since V8_0
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyStateGetV8Command

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 1 | Bool (Bit 0) |  |
| InTransition | False | 2 | Bool (Bit 0) |  |
| IsAuto | False | 3 | Bool (Bit 0) |  |
| IsTowardsOnAir | False | 4 | Bool (Bit 0) |  |
| RemainingFrames | False | 5 | UInt | 0 - 250 |

#### Older
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyStateGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| OnAir | False | 1 | Bool (Bit 0) |  |
| InTransition | False | 2 | Bool (Bit 0) |  |
| IsAuto | False | 3 | Bool (Bit 0) |  |
| RemainingFrames | False | 4 | UInt | 0 - 250 |

### CDsT
Implementation: LibAtem.Commands.DownstreamKey.DownstreamKeyTieSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (DownstreamKeyId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| Tie | False | 1 | Bool (Bit 0) |  |

### _AMC
Implementation: LibAtem.Commands.DeviceProfile.AudioMixerConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Inputs | False | 0 | UInt | 8 bits |
| Monitors | False | 1 | UInt | 8 bits |

### _DVE
TODO - support generating this

### _FAC
#### Since V8_0
Implementation: LibAtem.Commands.DeviceProfile.FairlightAudioMixerConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Inputs | False | 0 | UInt | 8 bits |
| Monitors | False | 1 | UInt | 8 bits |

### _MAC
Implementation: LibAtem.Commands.DeviceProfile.MacroPoolConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MacroCount | False | 0 | UInt | 8 bits |

### _mpl
Implementation: LibAtem.Commands.DeviceProfile.MediaPoolConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| StillCount | False | 0 | UInt | 8 bits |
| ClipCount | False | 1 | UInt | 8 bits |

### _MeC
Implementation: LibAtem.Commands.DeviceProfile.MixEffectBlockConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0 | Enum (MixEffectBlockId) | 0 = One<br/>1 = Two<br/>2 = Three<br/>3 = Four |
| KeyCount | False | 1 | UInt | 8 bits |

### _MvC
#### Since V8_0
Implementation: LibAtem.Commands.DeviceProfile.MultiviewerConfigV8Command

Payload length: 12

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Count | False | 0 | UInt | 8 bits |
| WindowCount | False | 1 | UInt | 8 bits |
| CanRouteWindows | False | 3 | Bool (Bit 0) |  |
| CanSwapPreviewProgram | False | 5 | Bool (Bit 0) |  |
| SupportsVuMeters | False | 6 | Bool (Bit 0) |  |
| CanToggleSafeArea | False | 7 | Bool (Bit 0) |  |
| SupportsQuadrants | False | 9 | Bool (Bit 0) |  |

#### Older
Implementation: LibAtem.Commands.DeviceProfile.MultiviewerConfigCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Count | False | 0 | UInt | 8 bits |
| WindowCount | False | 1 | UInt | 8 bits |
| CanRouteInputs | False | 3 | Bool (Bit 0) |  |
| CanSwapPreviewProgram | False | 5 | Bool (Bit 0) |  |
| CanToggleSafeArea | False | 7 | Bool (Bit 0) |  |

### Powr
Implementation: LibAtem.Commands.DeviceProfile.PowerStatusCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Pin1 | False | 0 | Bool (Bit 0) |  |
| Pin2 | False | 0 | Bool (Bit 1) |  |

### _pin
Implementation: LibAtem.Commands.DeviceProfile.ProductIdentifierCommand

Payload length: 44

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Name | False | 0-39 | String |  |
| Model | False | 40 | Enum (ModelId) | 0 = Unknown<br/>1 = TVStudio<br/>2 = OneME<br/>3 = TwoME<br/>4 = PS4K<br/>5 = OneME4K<br/>6 = TwoMe4K<br/>7 = TwoMEBS4K<br/>8 = TVStudioHD<br/>11 = Constellation8K |

### _SSC
#### Since V8_0
Implementation: LibAtem.Commands.DeviceProfile.SuperSourceConfigV8Command

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SSrcId | False | 0 | Enum (SuperSourceId) | 0 = One<br/>1 = Two |
| Boxes | False | 2 | UInt | 8 bits |

#### Older
Implementation: LibAtem.Commands.DeviceProfile.SuperSourceConfigCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Boxes | False | 0 | UInt | 8 bits |

### _top
#### Since V8_0
Implementation: LibAtem.Commands.DeviceProfile.TopologyV8Command

Payload length: 24

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectBlocks | False | 0 | UInt | 8 bits |
| VideoSources | False | 1 | UInt | 8 bits |
| DownstreamKeyers | False | 2 | UInt | 8 bits |
| Auxiliaries | False | 3 | UInt | 8 bits |
| MixMinusOutputs | False | 4 | UInt | 8 bits |
| MediaPlayers | False | 5 | UInt | 8 bits |
| SerialPort | False | 6 | UInt | 8 bits |
| HyperDecks | False | 7 | UInt | 8 bits |
| DVE | False | 8 | UInt | 8 bits |
| Stingers | False | 9 | UInt | 8 bits |
| SuperSource | False | 10 | UInt | 8 bits |

#### Older
Implementation: LibAtem.Commands.DeviceProfile.TopologyCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MixEffectBlocks | False | 0 | UInt | 8 bits |
| VideoSources | False | 1 | UInt | 8 bits |
| DownstreamKeyers | False | 2 | UInt | 8 bits |
| Auxiliaries | False | 3 | UInt | 8 bits |
| MixMinusOutputs | False | 4 | UInt | 8 bits |
| MediaPlayers | False | 5 | UInt | 8 bits |
| SerialPort | False | 6 | UInt | 8 bits |
| HyperDecks | False | 7 | UInt | 8 bits |
| DVE | False | 8 | UInt | 8 bits |
| Stingers | False | 9 | UInt | 8 bits |
| SuperSource | False | 10 | UInt | 8 bits |

### _ver
Implementation: LibAtem.Commands.DeviceProfile.VersionCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| ProtocolVersion | False | 0-3 | Enum (ProtocolVersion) | 131094 = Minimum<br/>131094 = Minimum<br/>131097 = V7_X<br/>131100 = V8_0<br/>131101 = V8_0_1<br/>131101 = V8_0_1 |

### _VMC
TODO - support generating this

### TcLk
#### Since V8_0
Implementation: LibAtem.Commands.DeviceProfile.TimecodeLockedCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Locked | False | 0 | Bool (Bit 0) |  |

### FTUA
Implementation: LibAtem.Commands.DataTransfer.DataTransferAckCommand

Payload length: 4

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| TransferIndex | False | 2 | UInt | 8 bits |

### FTDC
Implementation: LibAtem.Commands.DataTransfer.DataTransferCompleteCommand

Payload length: 4

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |

### FTDa
TODO - support generating this

### FTSU
Implementation: LibAtem.Commands.DataTransfer.DataTransferDownloadRequestCommand

Payload length: 12

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| TransferStoreId | False | 2-3 | UInt | 16 bits |
| TransferIndex | False | 7 | UInt | 8 bits |
| Unknown | False | 8-9 | UInt | 16 bits |
| Unknown2 | False | 10-11 | UInt | 16 bits |

### FTDE
Implementation: LibAtem.Commands.DataTransfer.DataTransferErrorCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| ErrorCode | False | 2 | UInt | 8 bits |

### FTFD
Implementation: LibAtem.Commands.DataTransfer.DataTransferFileDescriptionCommand

Payload length: 212

Direction: Both

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| Name | False | 2-65 | String |  |
| Description | False | 66-193 | String |  |
| FileHash | False | 194-209 | Bytes |  |

### FTCD
Implementation: LibAtem.Commands.DataTransfer.DataTransferUploadContinueCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| Unknown | False | 2 | UInt | 8 bits |
| ChunkSize | False | 6-7 | UInt | 16 bits |
| ChunkCount | False | 8-9 | UInt | 16 bits |
| Test3 | False | 10-11 | UInt | 16 bits |

### FTSD
Implementation: LibAtem.Commands.DataTransfer.DataTransferUploadRequestCommand

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| TransferId | True | 0-1 | UInt | 16 bits |
| TransferStoreId | False | 2-3 | UInt | 16 bits |
| TransferIndex | False | 6-7 | UInt | 16 bits |
| Size | False | 8-11 | Int | 32 bits |
| Mode | False | 12-13 | Enum (TransferMode) | Bit -∞ = NoOp<br/>Bit 0 = Write<br/>Bit 1 = Clear<br/>Bit 8 = Write2<br/>Bit 9 = Clear2 |

### LKOB
Implementation: LibAtem.Commands.DataTransfer.LockObtainedCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |

### LKST
Implementation: LibAtem.Commands.DataTransfer.LockStateChangedCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |
| Locked | False | 2 | Bool (Bit 0) |  |

### LOCK
Implementation: LibAtem.Commands.DataTransfer.LockStateSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | UInt | 16 bits |
| Locked | False | 2 | Bool (Bit 0) |  |

### CCst
TODO - support generating this

### AMIP
#### Since V8_0
Implementation: LibAtem.Commands.Audio.AudioMixerInputGetV8Command

Payload length: 16

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceType | False | 2 | Enum (AudioSourceType) | 0 = ExternalVideo<br/>1 = MediaPlayer<br/>2 = ExternalAudio |
| IndexOfSourceType | False | 4-5 | UInt | 16 bits |
| PortType | False | 6-7 | Enum (AudioPortType) | 0 = Unknown<br/>1 = SDI<br/>2 = HDMI<br/>32 = XLR<br/>64 = AESEBU<br/>128 = RCA<br/>256 = Internal<br/>512 = Headset |
| MixOption | False | 8 | Enum (AudioMixOption) | 0 = Off<br/>1 = On<br/>2 = AudioFollowVideo |
| Gain | False | 10-11 | UInt | 16 bits |
| Balance | False | 12-13 | Int<br/>Double Scale 200 | -10000 - 10000<br/>(-50 - 50) |

#### Older
Implementation: LibAtem.Commands.Audio.AudioMixerInputGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceType | False | 2 | Enum (AudioSourceType) | 0 = ExternalVideo<br/>1 = MediaPlayer<br/>2 = ExternalAudio |
| IndexOfSourceType | False | 4-5 | UInt | 16 bits |
| PortType | False | 6-7 | Enum (AudioPortType) | 0 = Unknown<br/>1 = SDI<br/>2 = HDMI<br/>32 = XLR<br/>64 = AESEBU<br/>128 = RCA<br/>256 = Internal<br/>512 = Headset |
| MixOption | False | 8 | Enum (AudioMixOption) | 0 = Off<br/>1 = On<br/>2 = AudioFollowVideo |
| Gain | False | 10-11 | UInt | 16 bits |
| Balance | False | 12-13 | Int<br/>Double Scale 200 | -10000 - 10000<br/>(-50 - 50) |

### CAMI
Implementation: LibAtem.Commands.Audio.AudioMixerInputSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = MixOption<br/>Bit 1 = Gain<br/>Bit 2 = Balance |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| MixOption | False | 4 | Enum (AudioMixOption) | 0 = Off<br/>1 = On<br/>2 = AudioFollowVideo |
| Gain | False | 6-7 | UInt | 16 bits |
| Balance | False | 8-9 | Int<br/>Double Scale 200 | -10000 - 10000<br/>(-50 - 50) |

### AMLv
TODO - support generating this

### AMMO
Implementation: LibAtem.Commands.Audio.AudioMixerMasterGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 0-1 | UInt | 16 bits |
| Balance | False | 2-3 | Int<br/>Double Scale 200 | -10000 - 10000<br/>(-50 - 50) |
| FollowFadeToBlack | False | 4 | Bool (Bit 0) |  |

### CAMM
Implementation: LibAtem.Commands.Audio.AudioMixerMasterSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Gain<br/>Bit 1 = Balance<br/>Bit 2 = FollowFadeToBlack |
| Gain | False | 2-3 | UInt | 16 bits |
| Balance | False | 4-5 | Int<br/>Double Scale 200 | -10000 - 10000<br/>(-50 - 50) |
| FollowFadeToBlack | False | 6 | Bool (Bit 0) |  |

### AMmO
Implementation: LibAtem.Commands.Audio.AudioMixerMonitorGetCommand

Payload length: 12

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Enabled | False | 0 | Bool (Bit 0) |  |
| Gain | False | 2-3 | UInt | 16 bits |
| Mute | False | 4 | Bool (Bit 0) |  |
| Solo | False | 5 | Bool (Bit 0) |  |
| SoloSource | False | 6-7 | Enum (AudioSource) | (See audio source list) |
| Dim | False | 8 | Bool (Bit 0) |  |

### CAMm
Implementation: LibAtem.Commands.Audio.AudioMixerMonitorSetCommand

Payload length: 12

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Enabled<br/>Bit 1 = Gain<br/>Bit 2 = Mute<br/>Bit 3 = Solo<br/>Bit 4 = SoloSource<br/>Bit 5 = Dim |
| Enabled | False | 1 | Bool (Bit 0) |  |
| Gain | False | 2-3 | UInt | 16 bits |
| Mute | False | 4 | Bool (Bit 0) |  |
| Solo | False | 5 | Bool (Bit 0) |  |
| SoloSource | False | 6-7 | Enum (AudioSource) | (See audio source list) |
| Dim | False | 8 | Bool (Bit 0) |  |

### AMPP
Implementation: LibAtem.Commands.Audio.AudioMixerPropertiesGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| AudioFollowVideo | False | 0 | Bool (Bit 0) |  |

### CAMP
Implementation: LibAtem.Commands.Audio.AudioMixerPropertiesSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = AudioFollowVideo |
| AudioFollowVideo | False | 1 | Bool (Bit 0) |  |

### RAMP
Implementation: LibAtem.Commands.Audio.AudioMixerResetPeaksCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = All<br/>Bit 1 = Input<br/>Bit 2 = Master<br/>Bit 3 = Monitor |
| All | False | 1 | Bool (Bit 0) |  |
| Input | False | 2-3 | Enum (AudioSource) | (See audio source list) |
| Master | False | 4 | Bool (Bit 0) |  |
| Monitor | False | 5 | Bool (Bit 0) |  |

### SALN
Implementation: LibAtem.Commands.Audio.AudioMixerSendLevelsCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SendLevels | False | 0 | Bool (Bit 0) |  |

### ATMP
Implementation: LibAtem.Commands.Audio.AudioMixerTalkbackPropertiesGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| MuteSDI | False | 1 | Bool (Bit 0) |  |

### CAMT
Implementation: LibAtem.Commands.Audio.AudioMixerTalkbackPropertiesSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = MuteSDI |
| MuteSDI | False | 2 | Bool (Bit 0) |  |

### AMTl
TODO - support generating this

### TMIP
#### Since V8_0
Implementation: LibAtem.Commands.Audio.TalkbackMixerInputPropertiesGetCommand

Payload length: 8

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Channel | True | 0 | Enum (TalkbackChannel) | 0 = Production<br/>1 = Engineering |
| Index | True | 2-3 | Enum (VideoSource) | (See video source list) |
| MuteSDI | False | 6 | Bool (Bit 0) |  |

### CTIP
#### Since V8_0
Implementation: LibAtem.Commands.Audio.TalkbackMixerInputPropertiesSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = MuteSDI |
| Channel | True | 1 | Enum (TalkbackChannel) | 0 = Production<br/>1 = Engineering |
| Index | True | 2-3 | Enum (VideoSource) | (See video source list) |
| MuteSDI | False | 6 | Bool (Bit 0) |  |

### FAAI
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerAnalogAudioGetCommand

Payload length: 4

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SupportedInputLevel | False | 2 | Enum (FairlightAnalogInputLevel) | 1 = Microphone<br/>2 = ConsumerLine |
| InputLevel | False | 3 | Enum (FairlightAnalogInputLevel) | 1 = Microphone<br/>2 = ConsumerLine |

### CFAA
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerAnalogAudioSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| InputLevel | False | 2 | Enum (FairlightAnalogInputLevel) | 1 = Microphone<br/>2 = ConsumerLine |

### FAIP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerInputGetCommand

Payload length: 16

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| InputType | False | 2 | Enum (FairlightInputType) | 0 = EmbeddedWithVideo<br/>1 = MediaPlayer<br/>2 = AudioIn<br/>4 = MADI |
| ExternalPortType | False | 6-7 | Enum (ExternalPortType) | 0 = Internal<br/>1 = SDI<br/>2 = HDMI<br/>3 = Composite<br/>4 = Component<br/>5 = SVideo<br/>32 = XLR<br/>64 = AESEBU<br/>128 = RCA<br/>512 = TSJack<br/>1024 = MADI<br/>2048 = TRS |
| SupportsRcaToXlr | False | 8 | Bool (Bit 0) |  |
| RcaToXlrEnabled | False | 9 | Bool (Bit 0) |  |
| SupportedConfigurations | False | 11 | Enum (FairlightInputConfiguration) | 1 = Mono<br/>2 = Stereo<br/>4 = DualMono |
| ActiveConfiguration | False | 12 | Enum (FairlightInputConfiguration) | 1 = Mono<br/>2 = Stereo<br/>4 = DualMono |

### CFIP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerInputSetCommand

Payload length: 8

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = RcaToXlrEnabled<br/>Bit 1 = ActiveConfiguration |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| RcaToXlrEnabled | False | 4 | Bool (Bit 0) |  |
| ActiveConfiguration | False | 5 | Enum (FairlightInputConfiguration) | 1 = Mono<br/>2 = Stereo<br/>4 = DualMono |

### MOCP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterCompressorGetCommand

Payload length: 24

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| CompressorEnabled | False | 0 | Bool (Bit 0) |  |
| Threshold | False | 4-7 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Ratio | False | 8-9 | Int<br/>Double Scale 100 | 120 - 2000<br/>(1.2 - 20) |
| Attack | False | 12-15 | Int<br/>Double Scale 100 | 70 - 10000<br/>(0.7 - 100) |
| Hold | False | 16-19 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 20-23 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### CMCP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterCompressorSetCommand

Payload length: 24

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = CompressorEnabled<br/>Bit 1 = Threshold<br/>Bit 2 = Ratio<br/>Bit 3 = Attack<br/>Bit 4 = Hold<br/>Bit 5 = Release |
| CompressorEnabled | False | 1 | Bool (Bit 0) |  |
| Threshold | False | 4-7 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Ratio | False | 8-9 | Int<br/>Double Scale 100 | 120 - 2000<br/>(1.2 - 20) |
| Attack | False | 12-15 | Int<br/>Double Scale 100 | 70 - 10000<br/>(0.7 - 100) |
| Hold | False | 16-19 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 20-23 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### RMOD
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterDynamicsResetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Dynamics | False | 1 | Bool (Bit 0) |  |
| Expander | False | 1 | Bool (Bit 1) |  |
| Compressor | False | 1 | Bool (Bit 2) |  |
| Limiter | False | 1 | Bool (Bit 3) |  |

### AMBP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterEqualizerBandGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Band | True | 0 | UInt | 0 - 5 |
| BandEnabled | False | 1 | Bool (Bit 0) |  |
| Shape | False | 3 | Enum (FairlightEqualizerBandShape) | 1 = LowShelf<br/>2 = LowPass<br/>4 = BandPass<br/>8 = Notch<br/>16 = HighPass<br/>32 = HighShelf |
| FrequencyRange | False | 5 | Enum (FairlightEqualizerFrequencyRange) | 1 = Low<br/>2 = MidLow<br/>4 = MidHigh<br/>8 = High |
| Frequency | False | 8-11 | UInt | 30 - 21700 |
| Gain | False | 12-15 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| QFactor | False | 16-17 | Int<br/>Double Scale 100 | 30 - 1030<br/>(0.3 - 10.3) |

### CMBP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterEqualizerBandSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = BandEnabled<br/>Bit 1 = Shape<br/>Bit 2 = FrequencyRange<br/>Bit 3 = Frequency<br/>Bit 4 = Gain<br/>Bit 5 = QFactor |
| Band | True | 1 | UInt | 0 - 5 |
| BandEnabled | False | 2 | Bool (Bit 0) |  |
| Shape | False | 3 | Enum (FairlightEqualizerBandShape) | 1 = LowShelf<br/>2 = LowPass<br/>4 = BandPass<br/>8 = Notch<br/>16 = HighPass<br/>32 = HighShelf |
| FrequencyRange | False | 4 | Enum (FairlightEqualizerFrequencyRange) | 1 = Low<br/>2 = MidLow<br/>4 = MidHigh<br/>8 = High |
| Frequency | False | 8-11 | UInt | 30 - 21700 |
| Gain | False | 12-15 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| QFactor | False | 16-17 | Int<br/>Double Scale 100 | 30 - 1030<br/>(0.3 - 10.3) |

### RMOE
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterEqualizerResetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Equalizer | False | 1 | Bool (Bit 0) |  |

### FAMP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| EqualizerEnabled | False | 1 | Bool (Bit 0) |  |
| EqualizerGain | False | 4-7 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| MakeUpGain | False | 8-11 | Int<br/>Double Scale 100 | 0 - 2000<br/>(0 - 20) |
| Gain | False | 12-15 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| FollowFadeToBlack | False | 16 | Bool (Bit 0) |  |

### FDLv
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterLevelsCommand

Payload length: 28

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| InputLeftLevel | False | 0-1 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputRightLevel | False | 2-3 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputLeftPeak | False | 4-5 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputRightPeak | False | 6-7 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| CompressorGainReduction | False | 8-9 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LimiterGainReduction | False | 10-11 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputLeftLevel | False | 12-13 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputRightLevel | False | 14-15 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputLeftPeak | False | 16-17 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputRightPeak | False | 18-19 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LeftLevel | False | 20-21 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| RightLevel | False | 22-23 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LeftPeak | False | 24-25 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| RightPeak | False | 26-27 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |

### AMLP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterLimiterGetCommand

Payload length: 20

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| LimiterEnabled | False | 0 | Bool (Bit 0) |  |
| Threshold | False | 4-7 | Int<br/>Double Scale 100 | -3000 - 0<br/>(-30 - 0) |
| Attack | False | 8-11 | Int<br/>Double Scale 100 | 70 - 3000<br/>(0.7 - 30) |
| Hold | False | 12-15 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 16-19 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### CMLP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterLimiterSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = LimiterEnabled<br/>Bit 1 = Threshold<br/>Bit 2 = Attack<br/>Bit 3 = Hold<br/>Bit 4 = Release |
| LimiterEnabled | False | 1 | Bool (Bit 0) |  |
| Threshold | False | 4-7 | Int<br/>Double Scale 100 | -3000 - 0<br/>(-30 - 0) |
| Attack | False | 8-11 | Int<br/>Double Scale 100 | 70 - 3000<br/>(0.7 - 30) |
| Hold | False | 12-15 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 16-19 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### FMPP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterPropertiesGetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| AudioFollowVideoCrossfadeTransitionEnabled | False | 0 | Bool (Bit 0) |  |

### CMPP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterPropertiesSetCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = AudioFollowVideoCrossfadeTransitionEnabled |
| AudioFollowVideoCrossfadeTransitionEnabled | False | 1 | Bool (Bit 0) |  |

### CFMP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMasterSetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = EqualizerEnabled<br/>Bit 1 = EqualizerGain<br/>Bit 2 = MakeUpGain<br/>Bit 3 = Gain<br/>Bit 4 = FollowFadeToBlack |
| EqualizerEnabled | False | 1 | Bool (Bit 0) |  |
| EqualizerGain | False | 4-7 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| MakeUpGain | False | 8-11 | Int<br/>Double Scale 100 | 0 - 2000<br/>(0 - 20) |
| Gain | False | 12-15 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| FollowFadeToBlack | False | 16 | Bool (Bit 0) |  |

### FMHP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMonitorGetCommand

Payload length: 32

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Gain | False | 0-3 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| InputMasterGain | False | 4-7 | Int<br/>Double Scale 100 | -6000 - 600<br/>(-60 - 6) |
| InputTalkbackGain | False | 12-15 | Int<br/>Double Scale 100 | -6000 - 600<br/>(-60 - 6) |
| InputSidetoneGain | False | 28-31 | Int<br/>Double Scale 100 | -6000 - 600<br/>(-60 - 6) |

### CFMH
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerMonitorSetCommand

Payload length: 36

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = Gain<br/>Bit 1 = InputMasterGain<br/>Bit 3 = InputTalkbackGain<br/>Bit 7 = InputSidetoneGain |
| Gain | False | 4-7 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| InputMasterGain | False | 8-11 | Int<br/>Double Scale 100 | -6000 - 600<br/>(-60 - 6) |
| InputTalkbackGain | False | 16-19 | Int<br/>Double Scale 100 | -6000 - 0<br/>(-60 - 0) |
| InputSidetoneGain | False | 32-35 | Int<br/>Double Scale 100 | -6000 - 600<br/>(-60 - 6) |

### RFLP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerResetPeakLevelsCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| All | False | 0 | Bool (Bit 0) |  |
| Master | False | 0 | Bool (Bit 1) |  |

### SFLN
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSendLevelsCommand

Payload length: 4

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SendLevels | False | 0 | Bool (Bit 0) |  |

### AICP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceCompressorGetCommand

Payload length: 40

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| CompressorEnabled | False | 16 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Ratio | False | 24-25 | Int<br/>Double Scale 100 | 120 - 2000<br/>(1.2 - 20) |
| Attack | False | 28-31 | Int<br/>Double Scale 100 | 70 - 10000<br/>(0.7 - 100) |
| Hold | False | 32-35 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 36-39 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### CICP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceCompressorSetCommand

Payload length: 40

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = CompressorEnabled<br/>Bit 1 = Threshold<br/>Bit 2 = Ratio<br/>Bit 3 = Attack<br/>Bit 4 = Hold<br/>Bit 5 = Release |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| CompressorEnabled | False | 16 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Ratio | False | 24-25 | Int<br/>Double Scale 100 | 120 - 2000<br/>(1.2 - 20) |
| Attack | False | 28-31 | Int<br/>Double Scale 100 | 70 - 10000<br/>(0.7 - 100) |
| Hold | False | 32-35 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 36-39 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### FASD
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceDeleteCommand

Payload length: 16

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |

### RICD
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceDynamicsResetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| Dynamics | False | 17 | Bool (Bit 0) |  |
| Expander | False | 17 | Bool (Bit 1) |  |
| Compressor | False | 17 | Bool (Bit 2) |  |
| Limiter | False | 17 | Bool (Bit 3) |  |

### AEBP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceEqualizerBandGetCommand

Payload length: 36

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| Band | True | 16 | UInt | 0 - 5 |
| BandEnabled | False | 17 | Bool (Bit 0) |  |
| Shape | False | 19 | Enum (FairlightEqualizerBandShape) | 1 = LowShelf<br/>2 = LowPass<br/>4 = BandPass<br/>8 = Notch<br/>16 = HighPass<br/>32 = HighShelf |
| FrequencyRange | False | 21 | Enum (FairlightEqualizerFrequencyRange) | 1 = Low<br/>2 = MidLow<br/>4 = MidHigh<br/>8 = High |
| Frequency | False | 24-27 | UInt | 30 - 21700 |
| Gain | False | 28-31 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| QFactor | False | 32-33 | Int<br/>Double Scale 100 | 30 - 1030<br/>(0.3 - 10.3) |

### CEBP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceEqualizerBandSetCommand

Payload length: 32

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = BandEnabled<br/>Bit 1 = Shape<br/>Bit 2 = FrequencyRange<br/>Bit 3 = Frequency<br/>Bit 4 = Gain<br/>Bit 5 = QFactor |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| Band | True | 16 | UInt | 0 - 5 |
| BandEnabled | False | 17 | Bool (Bit 0) |  |
| Shape | False | 18 | Enum (FairlightEqualizerBandShape) | 1 = LowShelf<br/>2 = LowPass<br/>4 = BandPass<br/>8 = Notch<br/>16 = HighPass<br/>32 = HighShelf |
| FrequencyRange | False | 19 | Enum (FairlightEqualizerFrequencyRange) | 1 = Low<br/>2 = MidLow<br/>4 = MidHigh<br/>8 = High |
| Frequency | False | 20-23 | UInt | 30 - 21700 |
| Gain | False | 24-27 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| QFactor | False | 28-29 | Int<br/>Double Scale 100 | 30 - 1030<br/>(0.3 - 10.3) |

### RICE
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceEqualizerResetCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| Equalizer | False | 16 | Bool (Bit 0) |  |

### AIXP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceExpanderGetCommand

Payload length: 40

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| ExpanderEnabled | False | 16 | Bool (Bit 0) |  |
| GateEnabled | False | 17 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Range | False | 24-25 | Int<br/>Double Scale 100 | 0 - 6000<br/>(0 - 60) |
| Ratio | False | 26-27 | Int<br/>Double Scale 100 | 110 - 300<br/>(1.1 - 3) |
| Attack | False | 28-31 | Int<br/>Double Scale 100 | 50 - 10000<br/>(0.5 - 100) |
| Hold | False | 32-35 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 36-39 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### CIXP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceExpanderSetCommand

Payload length: 40

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = ExpanderEnabled<br/>Bit 1 = GateEnabled<br/>Bit 2 = Threshold<br/>Bit 3 = Range<br/>Bit 4 = Ratio<br/>Bit 5 = Attack<br/>Bit 6 = Hold<br/>Bit 7 = Release |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| ExpanderEnabled | False | 16 | Bool (Bit 0) |  |
| GateEnabled | False | 17 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -5000 - 0<br/>(-50 - 0) |
| Range | False | 24-25 | Int<br/>Double Scale 100 | 0 - 6000<br/>(0 - 60) |
| Ratio | False | 26-27 | Int<br/>Double Scale 100 | 110 - 300<br/>(1.1 - 3) |
| Attack | False | 28-31 | Int<br/>Double Scale 100 | 50 - 10000<br/>(0.5 - 100) |
| Hold | False | 32-35 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 36-39 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### FASP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceGetCommand

Payload length: 52

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| SourceType | False | 16 | Enum (FairlightAudioSourceType) | 0 = Mono<br/>1 = Stereo |
| MaxFramesDelay | False | 17 | UInt | 8 bits |
| FramesDelay | False | 18 | UInt | 8 bits |
| Gain | False | 20-23 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| HasStereoSimulation | False | 24 | Bool (Bit 0) |  |
| StereoSimulation | False | 26-27 | Int<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| EqualizerEnabled | False | 29 | Bool (Bit 0) |  |
| EqualizerGain | False | 32-35 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| MakeUpGain | False | 36-39 | Int<br/>Double Scale 100 | 0 - 2000<br/>(0 - 20) |
| Balance | False | 40-41 | Int<br/>Double Scale 100 | -10000 - 10000<br/>(-100 - 100) |
| FaderGain | False | 44-47 | Int<br/>Double Scale 100 | -10000 - 1000<br/>(-100 - 10) |
| SupportedMixOptions | False | 48 | Enum (FairlightAudioMixOption) | 1 = Off<br/>2 = On<br/>4 = AudioFollowVideo |
| MixOption | False | 49 | Enum (FairlightAudioMixOption) | 1 = Off<br/>2 = On<br/>4 = AudioFollowVideo |

### FMLv
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceLevelsCommand

Payload length: 40

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| SourceId | True | 0-7 | Int | 64 bits |
| Index | True | 8-9 | Enum (AudioSource) | (See audio source list) |
| InputLeftLevel | False | 10-11 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputRightLevel | False | 12-13 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputLeftPeak | False | 14-15 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| InputRightPeak | False | 16-17 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| ExpanderGainReduction | False | 18-19 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| CompressorGainReduction | False | 20-21 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LimiterGainReduction | False | 22-23 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputLeftLevel | False | 24-25 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputRightLevel | False | 26-27 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputLeftPeak | False | 28-29 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| OutputRightPeak | False | 30-31 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LeftLevel | False | 32-33 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| RightLevel | False | 34-35 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| LeftPeak | False | 36-37 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |
| RightPeak | False | 38-39 | Int<br/>Double Scale 100 | -10000 - 0<br/>(-100 - 0) |

### AILP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceLimiterGetCommand

Payload length: 36

Direction: ToClient

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| LimiterEnabled | False | 16 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -3000 - 0<br/>(-30 - 0) |
| Attack | False | 24-27 | Int<br/>Double Scale 100 | 70 - 3000<br/>(0.7 - 30) |
| Hold | False | 28-31 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 32-35 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### CILP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceLimiterSetCommand

Payload length: 36

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0 | Enum (MaskFlags) | Bit 0 = LimiterEnabled<br/>Bit 1 = Threshold<br/>Bit 2 = Attack<br/>Bit 3 = Hold<br/>Bit 4 = Release |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| LimiterEnabled | False | 16 | Bool (Bit 0) |  |
| Threshold | False | 20-23 | Int<br/>Double Scale 100 | -3000 - 0<br/>(-30 - 0) |
| Attack | False | 24-27 | Int<br/>Double Scale 100 | 70 - 3000<br/>(0.7 - 30) |
| Hold | False | 28-31 | Int<br/>Double Scale 100 | 0 - 400000<br/>(0 - 4000) |
| Release | False | 32-35 | Int<br/>Double Scale 100 | 5000 - 400000<br/>(50 - 4000) |

### RFIP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceResetPeakLevelsCommand

Payload length: 20

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Index | True | 0-1 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| Output | False | 17 | Bool (Bit 2) |  |
| DynamicsInput | False | 17 | Bool (Bit 0) |  |
| DynamicsOutput | False | 17 | Bool (Bit 1) |  |

### CFSP
Implementation: LibAtem.Commands.Audio.Fairlight.FairlightMixerSourceSetCommand

Payload length: 48

Direction: ToServer

| Name | IsId | Bytes | Type | Values |
| --- | --- | --- | --- | --- |
| Mask | False | 0-1 | Enum (MaskFlags) | Bit 0 = FramesDelay<br/>Bit 1 = Gain<br/>Bit 2 = StereoSimulation<br/>Bit 3 = EqualizerEnabled<br/>Bit 4 = EqualizerGain<br/>Bit 5 = MakeUpGain<br/>Bit 6 = Balance<br/>Bit 7 = FaderGain<br/>Bit 8 = MixOption |
| Index | True | 2-3 | Enum (AudioSource) | (See audio source list) |
| SourceId | True | 8-15 | Int | 64 bits |
| FramesDelay | False | 16 | UInt | 8 bits |
| Gain | False | 20-23 | Int<br/>Double Scale 100 | -10000 - 600<br/>(-100 - 6) |
| StereoSimulation | False | 24-25 | Int<br/>Double Scale 100 | 0 - 10000<br/>(0 - 100) |
| EqualizerEnabled | False | 26 | Bool (Bit 0) |  |
| EqualizerGain | False | 28-31 | Int<br/>Double Scale 100 | -2000 - 2000<br/>(-20 - 20) |
| MakeUpGain | False | 32-35 | Int<br/>Double Scale 100 | 0 - 2000<br/>(0 - 20) |
| Balance | False | 36-37 | Int<br/>Double Scale 100 | -10000 - 10000<br/>(-100 - 100) |
| FaderGain | False | 40-43 | Int<br/>Double Scale 100 | -10000 - 1000<br/>(-100 - 10) |
| MixOption | False | 44 | Enum (FairlightAudioMixOption) | 1 = Off<br/>2 = On<br/>4 = AudioFollowVideo |

### FMTl
TODO - support generating this

