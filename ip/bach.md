# Bach

The register listings available are for "cedric" and "infinity". The two seem totally different.
This page is about infinity.

- [Infinity1 kernel driver](https://github.com/linux-chenxing/linux_mstar_3.18/tree/taobao_sdk/drivers/mstar/sound)
- [Infinity3 kernel driver](https://github.com/linux-chenxing/linux_mstar_3.18/tree/msc316sdk/drivers/mstar/sound)


## Bank address for infinity3/mercury5

[detailed here](https://github.com/fifteenhex/SDK_pulbic/blob/c1436fa7446457e8d6547874d27ee4e34be150cf/Mercury5/proj/sc/driver/hal/mercury/audio/inc/hal_bach.h#L41)

- 0x1f2a0400
- 0x1f2a0600
- 0x1f2a0800
- 0x1f206800

## bank 1 - control/DMA registers

| offset | name                            | 15                    | 14                    | 13                    | 12                    | 11                    | 10                    | 9                     | 8                     | 7                     | 6                     | 5                     | 4                     | 3                     | 2                      | 1                     | 0                     | notes                                                                                          |
|--------|---------------------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|-----------------------|------------------------|-----------------------|-----------------------|------------------------------------------------------------------------------------------------|
| 0x000  | enable ctrl                     |                       |                       |                       |                       | bp_adc_hpf2           | bp_adc_hpf1           |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x004  | sr0 sel                         | cic_1_sel             | cic_1_sel             |                       |                       | cic_3_sel             | cic_3_sel             | writer_sel            | writer_sel            | src1_sel              | src1_sel              | src1_sel              | src1_sel              | src2_sel              | src2_sel               | src2_sel              | src2_sel              |                                                                                                |
| 0x008  | ???                             |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x00c  | mux0 sel                        |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       | mmc1 src sel          |                       |                       |                        |                       |                       |                                                                                                |
| 0x010  | mux1 sel                        | adc_hpf_n             | adc_hpf_n             | adc_hpf_n             | adc_hpf_n             |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x014  | mix1 sel                        |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x018  | not documented but used         |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x01c  | not documented but used         |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x024  | sdm ctrl                        |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x04c  | codec i2s tx ctrl               |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x074  | synth ctrl                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x090  | adc dpga cfg1                   |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x094  | adc dpga cfg2                   |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x100  | dma1 ctrl0                      | wr underrun int en    | wr overrun int en     | rd underrun int en    | rd overrun int en     | wr full int en        | rd empty int en       | wr full int clr       | rd empty int clr      |                       | sel tes bus           | rd lr swap en         | priority keep high    | rd byte swap en       | rd level cnt live mask | enable                | sw rst                |                                                                                                |
| 0x104  | dma1 ctrl1                      | rd enable             | rd init               | rd trig               | rd level cnt          | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr                | rd addr               | rd addr               | >> 3                                                                                           |
| 0x108  | dma1 ctrl2                      |                       | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr               | rd addr                | rd addr               | rd addr               | >> 3                                                                                           |
| 0x10c  | dma1 ctrl3                      | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size               | rd size                | rd size               | rd size               | >> 3                                                                                           |
| 0x110  | dma1 ctrl4                      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level      | rd trigger level       | rd trigger level      | rd trigger level      |                                                                                                |
| 0x114  | dma1 ctrl5                      | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold  | rd overrun threshold   | rd overrun threshold  | rd overrun threshold  |                                                                                                |
| 0x118  | dma1 ctrl6                      | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold | rd underrun threshold  | rd underrun threshold | rd underrun threshold |                                                                                                |
| 0x11c  | dma1 ctrl7                      | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt          | rd level cnt           | rd level cnt          | rd level cnt          | latches on rd level cnt in ctrl1?                                                              |
| 0x120  | dma1 ctrl8                      |                       |                       |                       |                       |                       |                       |                       |                       | rd localbuf empty     | wr localbuf full      | wr full flag          | rd empty flag         | rd overrun flag       | rd underrun flag       | wr overrun flag       | wr underrun flag      |                                                                                                |
| 0x124  | dma1 ctrl9                      | wr enable             | wr init               | wr trig               | wr level cnt          | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr                | wr addr               | wr addr               | >> 3                                                                                           |
| 0x128  | dma1 ctrl10                     |                       | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr               | wr addr                | wr addr               | wr addr               | >> 3                                                                                           |
| 0x12c  | dma1 ctrl11                     | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size               | wr size                | wr size               | wr size               | >> 3                                                                                           |
| 0x130  | dma1 ctrl12                     | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level      | wr trigger level       | wr trigger level      | wr trigger level      |                                                                                                |
| 0x134  | dma1 ctrl13                     | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold  | wr overrun threshold   | wr overrun threshold  | wr overrun threshold  |                                                                                                |
| 0x138  | dma1 ctrl14                     | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold | wr underrun threshold  | wr underrun threshold | wr underrun threshold |                                                                                                |
| 0x13c  | dma1 ctrl15                     | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt          | wr level cnt           | wr level cnt          | wr level cnt          | latches on wr level cnt in ctrl 9? seems to possibly include up to 8 units from "local buffer" |
| 0x140  | dma2 ctrl0                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x144  | dma2 ctrl1                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x148  | dma2 ctrl2                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x14c  | dma2 ctrl3                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x150  | dma2 ctrl4                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x154  | dma2 ctrl5                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x158  | dma2 ctrl6                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x15c  | dma2 ctrl7                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x160  | dma2 ctrl8                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x164  | dma2 ctrl9                      |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x168  | dma2 ctrl10                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x16c  | dma2 ctrl11                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x180  | dma2 ctrl12                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x184  | dma2 ctrl13                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x188  | dma2 ctrl14                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x18c  | dma2 ctrl15                     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x1d4  | dma test ctrl 5 (sine wave gen) | sine gen en           | sine gen left         | sine gen right        |                       |                       |                       |                       |                       | gain                  | gain                  | gain                  | gain                  | freq                  | freq                   | freq                  | freq                  |                                                                                                |
| 0x1d8  |                                 |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
| 0x1dc  | dma test ctrl 7                 | dma1 rd mono          | dma1 wr mono          | dma1 rd mono copy     |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |
|        |                                 |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                       |                        |                       |                       |                                                                                                |

- sr0 sel - src1 sel seems to control the clock for the DMA reader
- dma test ctrl 5 - setting the sinewave gen enables cuts the playing audio but nothing audible comes out.

## bank 2 

| offset | name          | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1      | 0      |
|--------|---------------|----|----|----|----|----|----|---|---|---|---|---|---|---|---|--------|--------|
| 0x01c  | int en        |    |    |    |    |    |    |   |   |   |   |   |   |   |   | int en |        |
| 0x038  | mux3 sel      |    |    |    |    |    |    |   |   |   |   |   |   |   |   |        |        |
| 0x058  | au sys ctrl1  |    |    |    |    |    |    |   |   |   |   |   |   |   |   |        |        |
| 0x074  | dig mic ctrl0 |    |    |    |    |    |    |   |   |   |   |   |   |   |   |        |        |
| 0x078  | dig mic ctrl1 |    |    |    |    |    |    |   |   |   |   |   |   |   |   |        |        |

## bank 3

| offset | name   | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4      | 3      | 2      | 1      | 0      |
|--------|--------|----|----|----|----|----|----|---|---|---|---|---|--------|--------|--------|--------|--------|
| 0x010  |        |    |    |    |    |    |    |   |   |   |   |   | fs_sel | fs_sel | fs_sel | fs_sel | fs_sel |
|        |        |    |    |    |    |    |    |   |   |   |   |   |        |        |        |        |        |
|        |        |    |    |    |    |    |    |   |   |   |   |   |        |        |        |        |        |

## bank 4 - analog

| offset | name         | 15        | 14        | 13        | 12             | 11             | 10            | 9                | 8                | 7              | 6              | 5             | 4             | 3                  | 2                  | 1              | 0              | notes                                 |
|--------|--------------|-----------|-----------|-----------|----------------|----------------|---------------|------------------|------------------|----------------|----------------|---------------|---------------|--------------------|--------------------|----------------|----------------|---------------------------------------|
| 0x00   | analog ctrl0 |           |           |           |                | en msp         | en itest dac  | en dit adc0      | en dac disch     | en ck dac      | en ck dac      | en ck dac     | en ck dac     |                    | en chop adc0       | en byp inmux   | en byp inmux   |                                       |
| 0x04   | analog ctrl1 |           |           |           | en vref sfydch | en vref sfydch | en vref disch | en tst ibias adc | en tst ibias adc | en shrt r adc0 | en shrt l adc0 | en qs ldo dac | en qs ldo adc | en mute mic stg1 r | en mute mic stg1 l | en mute in mux | en mute in mux |                                       |
| 0x08   | analog ctrl2 | en sw tst | en sw tst | en sw tst | en sw tst      | en sw tst      | en sw tst     | en sw tst        | en sw tst        | en sw tst      | en sw tst      | en sw tst     | en sw tst     | en sw tst          | en sw tst          | en sw tst      | en sw tst      |                                       |
| 0x0c   | analog ctrl3 |           |           |           | vref           | vi             | ref_dac       | r0_dac           | mic stg2_l       | mic stg1_l     | ldo dac        | ldo adc       | l0 dac        | inmux              | inmux              | bias dac       | adc0           | power downs, probably 1 to power down |
| 0x10   | analog ctrl4 |           |           |           |                |                |               |                  |                  | rst dac        | rst dac        | rst dac       | rst dac       |                    |                    |                | rst adc0       |                                       |
| 0x14   |              |           |           |           |                |                |               |                  |                  |                |                |               |               |                    |                    |                |                |                                       |
| 0x18   |              |           |           |           |                |                |               |                  |                  |                |                |               |               |                    |                    |                |                |                                       |
| 0x1c   |              |           |           |           |                |                |               |                  |                  |                |                |               |               |                    |                    |                |                |                                       |
| 0x20   |              |           |           |           |                |                |               |                  |                  |                |                |               |               |                    |                    |                |                |                                       |
| 0x48   |              |           |           |           |                |                |               |                  |                  |                |                |               |               |                    |                    |                |                |                                       |

### Register dumps

#### i2m, vendor u-boot

```
Wireless-tag# md.w 0x1f2a0400 0x100
1f2a0400: c1ff 0000 0080 0000 0003 0000 0080 0000    ................
1f2a0410: 0000 0000 8000 0000 0000 0000 0000 0000    ................
1f2a0420: 0000 0000 0200 0000 0000 0000 007d 0000    ............}...
1f2a0430: 0000 0000 0000 0000 3017 0000 0002 0000    .........0......
1f2a0440: 9400 0000 9400 0000 9400 0000 9400 0000    ................
1f2a0450: 8400 0000 d000 0000 9400 0000 9400 0000    ................
1f2a0460: 8400 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0470: 0000 0000 001d 0000 0000 0000 0000 0000    ................
1f2a0480: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a0490: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04a0: 0000 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04b0: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04c0: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a04e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a04f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0500: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0510: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0520: 001f 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0530: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0540: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0550: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0560: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0570: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0580: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0590: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05d0: 0000 0000 0000 0000 0000 0000 0440 0000    ............@...
1f2a05e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

```
Wireless-tag# md.w 0x1f2a0600 0x100
1f2a0600: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0610: 4000 0000 0100 0000 03e8 0000 0000 0000    .@..............
1f2a0620: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0630: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0640: 38c0 0000 3838 0000 0c04 0000 1c14 0000    .8..88..........
1f2a0650: 0001 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0660: 0000 0000 0000 0000 0000 0000 0202 0000    ................
1f2a0670: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0680: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0690: 0000 0000 1234 0000 5678 0000 0000 0000    ....4...xV......
1f2a06a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0700: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0710: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0720: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0730: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0740: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0750: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0760: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0770: 0000 0000 0000 0000 0000 0000 0080 0000    ................
1f2a0780: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0790: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07f0: 0000 0000 0000 0000 0001 0000 0000 0000    ................
```

```
Wireless-tag# md.w 0x1f2a0800 0x100
1f2a0800: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0810: 0000 0000 8000 0000 0000 0000 0000 0000    ................
1f2a0820: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0830: 0000 0000 0000 0000 0000 0000 ffff 0000    ................
1f2a0840: 00f0 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0850: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0860: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0870: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0880: 00f0 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0890: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0900: 0080 0000 0078 0000 0000 0000 0000 0000    ....x...........
1f2a0910: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0920: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0930: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0940: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0950: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0960: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0970: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0980: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0990: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

```
Wireless-tag# md.w 0x1f206800 0x100
1f206800: 0204 0000 0000 0000 0080 0000 1fff 0000    ................
1f206810: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206820: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206830: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206840: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206850: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206860: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206870: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206880: 0040 0000 f0f0 0000 0000 0000 0000 0000    @...............
1f206890: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206900: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206910: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206920: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206930: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206940: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206950: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206960: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206970: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206980: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206990: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

#### i2m, ido openwrt after boot

```
0x1F206800 - 0x00000204
0x1F206804 - 0x00000000
0x1F206808 - 0x00000080
0x1F20680C - 0x00001FFF
0x1F206810 - 0x00000000
0x1F206814 - 0x00000000
0x1F206818 - 0x00000000
0x1F20681C - 0x00000000
0x1F206820 - 0x00000000
0x1F206824 - 0x00000000
0x1F206828 - 0x00000000
0x1F20682C - 0x00000000
0x1F206830 - 0x00000000
0x1F206834 - 0x00000000
0x1F206838 - 0x00000000
0x1F20683C - 0x00000000
0x1F206840 - 0x00000000
0x1F206844 - 0x00000000
0x1F206848 - 0x00000000
0x1F20684C - 0x00000000
0x1F206850 - 0x00000000
0x1F206854 - 0x00000000
0x1F206858 - 0x00000000
0x1F20685C - 0x00000000
0x1F206860 - 0x00000000
0x1F206864 - 0x00000000
0x1F206868 - 0x00000000
0x1F20686C - 0x00000000
0x1F206870 - 0x00000000
0x1F206874 - 0x00000000
0x1F206878 - 0x00000000
0x1F20687C - 0x00000000
0x1F206880 - 0x000000C0
0x1F206884 - 0x00000F0F
0x1F206888 - 0x00000000
0x1F20688C - 0x00000000
0x1F206890 - 0x00000000
0x1F206894 - 0x00000000
0x1F206898 - 0x00000000
0x1F20689C - 0x00000000
0x1F2068A0 - 0x00000000
0x1F2068A4 - 0x00000000
0x1F2068A8 - 0x00000000
0x1F2068AC - 0x00000000
0x1F2068B0 - 0x00000000
0x1F2068B4 - 0x00000000
0x1F2068B8 - 0x00000000
0x1F2068BC - 0x00000000
0x1F2068C0 - 0x00000000
0x1F2068C4 - 0x00000000
0x1F2068C8 - 0x00000000
0x1F2068CC - 0x00000000
0x1F2068D0 - 0x00000000
0x1F2068D4 - 0x00000000
0x1F2068D8 - 0x00000000
0x1F2068DC - 0x00000000
0x1F2068E0 - 0x00000000
0x1F2068E4 - 0x00000000
0x1F2068E8 - 0x00000000
0x1F2068EC - 0x00000000
0x1F2068F0 - 0x00000000
0x1F2068F4 - 0x00000000
0x1F2068F8 - 0x00000000
0x1F2068FC - 0x00000000
0x1F206900 - 0x00000000
0x1F206904 - 0x00000000
0x1F206908 - 0x00000000
0x1F20690C - 0x00000000
0x1F206910 - 0x00000000
0x1F206914 - 0x00000000
0x1F206918 - 0x00000000
0x1F20691C - 0x00000000
0x1F206920 - 0x00000000
0x1F206924 - 0x00000000
0x1F206928 - 0x00000000
0x1F20692C - 0x00000000
0x1F206930 - 0x00000000
0x1F206934 - 0x00000000
0x1F206938 - 0x00000000
0x1F20693C - 0x00000000
0x1F206940 - 0x00000000
0x1F206944 - 0x00000000
0x1F206948 - 0x00000000
0x1F20694C - 0x00000000
0x1F206950 - 0x00000000
0x1F206954 - 0x00000000
0x1F206958 - 0x00000000
0x1F20695C - 0x00000000
0x1F206960 - 0x00000000
0x1F206964 - 0x00000000
0x1F206968 - 0x00000000
0x1F20696C - 0x00000000
0x1F206970 - 0x00000000
0x1F206974 - 0x00000000
0x1F206978 - 0x00000000
0x1F20697C - 0x00000000
0x1F206980 - 0x00000000
0x1F206984 - 0x00000000
0x1F206988 - 0x00000000
0x1F20698C - 0x00000000
0x1F206990 - 0x00000000
0x1F206994 - 0x00000000
0x1F206998 - 0x00000000
0x1F20699C - 0x00000000
0x1F2069A0 - 0x00000000
0x1F2069A4 - 0x00000000
0x1F2069A8 - 0x00000000
0x1F2069AC - 0x00000000
0x1F2069B0 - 0x00000000
0x1F2069B4 - 0x00000000
0x1F2069B8 - 0x00000000
0x1F2069BC - 0x00000000
0x1F2069C0 - 0x00000000
0x1F2069C4 - 0x00000000
0x1F2069C8 - 0x00000000
0x1F2069CC - 0x00000000
0x1F2069D0 - 0x00000000
0x1F2069D4 - 0x00000000
0x1F2069D8 - 0x00000000
0x1F2069DC - 0x00000000
0x1F2069E0 - 0x00000000
0x1F2069E4 - 0x00000000
0x1F2069E8 - 0x00000000
0x1F2069EC - 0x00000000
0x1F2069F0 - 0x00000000
0x1F2069F4 - 0x00000000
0x1F2069F8 - 0x00000000
0x1F2069FC - 0x00000000
root@OpenWrt:/# 

```

0x80 and 0x84 are constantly changing:

```
0x1F206880 - 0x00000C80
0x1F206884 - 0x0000F0F0
```

```
0x1F206880 - 0x00000000
0x1F206884 - 0x0000F0F0
```

```
0x1F206880 - 0x00000080
0x1F206884 - 0x00004F0F
```

### i3 - our u-boot

```
md.w 0x1f2a0400 0x100
1f2a0400: c1ff 0000 0080 0000 0003 0000 0080 0000    ................
1f2a0410: 0000 0000 8000 0000 0000 0000 0000 0000    ................
1f2a0420: 0000 0000 0200 0000 0000 0000 007d 0000    ............}...
1f2a0430: 0000 0000 0000 0000 3017 0000 0002 0000    .........0......
1f2a0440: 9400 0000 9400 0000 9400 0000 9400 0000    ................
1f2a0450: 8400 0000 d000 0000 9400 0000 9400 0000    ................
1f2a0460: 8400 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0470: 0000 0000 001d 0000 0000 0000 0000 0000    ................
1f2a0480: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a0490: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04a0: 0000 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04b0: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04c0: 0007 0000 0000 0000 0007 0000 0000 0000    ................
1f2a04d0: 0000 0000 0000 0000 0000 0000 03ff 0000    ................
1f2a04e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a04f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0500: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0510: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0520: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0530: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0540: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0550: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0560: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0570: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0580: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0590: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a05f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

```
=> md.w 0x1f2a0600 0x100
1f2a0600: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0610: 4000 0000 0100 0000 03e8 0000 0000 0000    .@..............
1f2a0620: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0630: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0640: 38c0 0000 3838 0000 0c04 0000 1c14 0000    .8..88..........
1f2a0650: 0001 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0660: 0000 0000 0000 0000 0000 0000 0202 0000    ................
1f2a0670: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0680: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0690: 0000 0000 1234 0000 5678 0000 0000 0000    ....4...xV......
1f2a06a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a06f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0700: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0710: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0720: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0730: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0740: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0750: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0760: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0770: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0780: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0790: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a07f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

```
=> md.w 0x1f2a0800 0x100
1f2a0800: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0810: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0820: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0830: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0840: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0850: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0860: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0870: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0880: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0890: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a08f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0900: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0910: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0920: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0930: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0940: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0950: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0960: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0970: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0980: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a0990: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2a09f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

```
=> md.w 0x1f206800 0x100
1f206800: 0204 0000 0000 0000 0080 0000 1fff 0000    ................
1f206810: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206820: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206830: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206840: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206850: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206860: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206870: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206880: 0000 0000 0101 0000 0000 0000 0000 0000    ................
1f206890: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2068f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206900: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206910: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206920: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206930: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206940: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206950: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206960: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206970: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206980: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f206990: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069a0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069b0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069c0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069d0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069e0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
1f2069f0: 0000 0000 0000 0000 0000 0000 0000 0000    ................
```

### official dev board dumps

Before and after playing the weird video

``` diff
1,2c1,2
< 0x1F206800 - 0x00000204
< 0x1F206804 - 0x00000000
---
> 0x1F206800 - 0x00000A14
> 0x1F206804 - 0x00000030
4c4
< 0x1F20680C - 0x00001FFF
---
> 0x1F20680C - 0x000001A5
9c9
< 0x1F206820 - 0x00000000
---
> 0x1F206820 - 0x00003000
34c34
< 0x1F206884 - 0x00000F0F
---
> 0x1F206884 - 0x00008787
```
- 0x00 - bit 4 and bit 11 set
- 0x04 - bit 4 and bit 5 set
- 0x0c - bit 1, 3, 4, 6, bit 9 to 12 cleared.
- 0x20 - bit 12, 13 set

``` diff
1,2c1,2
< 0x1F2A0400 - 0x0000C1FF
< 0x1F2A0404 - 0x00000080
---
> 0x1F2A0400 - 0x000089FF
> 0x1F2A0404 - 0x0000FF08
4,5c4,5
< 0x1F2A040C - 0x00000080
< 0x1F2A0410 - 0x00000000
---
> 0x1F2A040C - 0x000019B4
> 0x1F2A0410 - 0x0000F000
7,8c7,8
< 0x1F2A0418 - 0x00000000
< 0x1F2A041C - 0x00000000
---
> 0x1F2A0418 - 0x0000C09A
> 0x1F2A041C - 0x0000555A
10c10
< 0x1F2A0424 - 0x00000200
---
> 0x1F2A0424 - 0x00000209
20c20
< 0x1F2A044C - 0x00009400
---
> 0x1F2A044C - 0x0000D400
30c30
< 0x1F2A0474 - 0x0000001D
---
> 0x1F2A0474 - 0x00000000
33,34c33,34
< 0x1F2A0480 - 0x00000007
< 0x1F2A0484 - 0x00000000
---
> 0x1F2A0480 - 0x00000037
> 0x1F2A0484 - 0x00006E6E
37c37
< 0x1F2A0490 - 0x00000007
---
> 0x1F2A0490 - 0x00000037
41c41
< 0x1F2A04A0 - 0x00000000
---
> 0x1F2A04A0 - 0x00000037
49c49
< 0x1F2A04C0 - 0x00000007
---
> 0x1F2A04C0 - 0x00000037
65,69c65,69
< 0x1F2A0500 - 0x00000000
< 0x1F2A0504 - 0x00000000
< 0x1F2A0508 - 0x00000000
< 0x1F2A050C - 0x00000000
< 0x1F2A0510 - 0x00000000
---
> 0x1F2A0500 - 0x00002096
> 0x1F2A0504 - 0x00008000
> 0x1F2A0508 - 0x00000FE8
> 0x1F2A050C - 0x00002000
> 0x1F2A0510 - 0x0000007D
71,73c71,73
< 0x1F2A0518 - 0x00000000
< 0x1F2A051C - 0x00000000
< 0x1F2A0520 - 0x0000001F
---
> 0x1F2A0518 - 0x00001F00
> 0x1F2A051C - 0x00001F22
> 0x1F2A0520 - 0x0000000B
116,117c116,117
< 0x1F2A05CC - 0x00000000
< 0x1F2A05D0 - 0x00000000
---
> 0x1F2A05CC - 0x0000E2C2
> 0x1F2A05D0 - 0x0000FC30
120c120
< 0x1F2A05DC - 0x00000440
---
> 0x1F2A05DC - 0x0000A400
```

0x100 - dma ctrl, enable read underrun int

``` diff
8c8
< 0x1F2A061C - 0x00000000
---
> 0x1F2A061C - 0x00000002
15c15
< 0x1F2A0638 - 0x00000000
---
> 0x1F2A0638 - 0x00000003
23c23
< 0x1F2A0658 - 0x00000000
---
> 0x1F2A0658 - 0x00000003
76c76
< 0x1F2A072C - 0x00000000
---
> 0x1F2A072C - 0x00000001
99,102c99,102
< 0x1F2A0788 - 0x00000000
< 0x1F2A078C - 0x00000000
< 0x1F2A0790 - 0x00000000
< 0x1F2A0794 - 0x00000000
---
> 0x1F2A0788 - 0x0000089D
> 0x1F2A078C - 0x0000129D
> 0x1F2A0790 - 0x000071D2
> 0x1F2A0794 - 0x00006D5A
108,109c108,109
< 0x1F2A07AC - 0x00000000
< 0x1F2A07B0 - 0x00000000
---
> 0x1F2A07AC - 0x0000FF3E
> 0x1F2A07B0 - 0x000009F3
112c112
< 0x1F2A07BC - 0x00000000
---
> 0x1F2A07BC - 0x000078F4
115,116c115,116
< 0x1F2A07C8 - 0x00000000
< 0x1F2A07CC - 0x00000000
---
> 0x1F2A07C8 - 0x0000E3AB
> 0x1F2A07CC - 0x00000582
119,121c119,121
< 0x1F2A07D8 - 0x00000000
< 0x1F2A07DC - 0x00000000
< 0x1F2A07E0 - 0x00000000
---
> 0x1F2A07D8 - 0x0000FE7B
> 0x1F2A07DC - 0x0000F949
> 0x1F2A07E0 - 0x000078F4
125c125
< 0x1F2A07F0 - 0x00000000
---
> 0x1F2A07F0 - 0x00006B65
```

``` diff
2c2
< 0x1F2A0804 - 0x00000000
---
> 0x1F2A0804 - 0x00000021
5c5
< 0x1F2A0810 - 0x00000000
---
> 0x1F2A0810 - 0x0000000A
7c7
< 0x1F2A0818 - 0x00000000
---
> 0x1F2A0818 - 0x0000011F
17,21c17,21
< 0x1F2A0840 - 0x000000F0
< 0x1F2A0844 - 0x00000000
< 0x1F2A0848 - 0x00000000
< 0x1F2A084C - 0x00000000
< 0x1F2A0850 - 0x00000000
---
> 0x1F2A0840 - 0x00000000
> 0x1F2A0844 - 0x00000001
> 0x1F2A0848 - 0x00008000
> 0x1F2A084C - 0x00000001
> 0x1F2A0850 - 0x00008000
33c33
< 0x1F2A0880 - 0x000000F0
---
> 0x1F2A0880 - 0x00000001
113,114c113,114
< 0x1F2A09C0 - 0x00000003
< 0x1F2A09C4 - 0x00000000
---
> 0x1F2A09C0 - 0x00000000
> 0x1F2A09C4 - 0x00000B0B
116,117c116,117
< 0x1F2A09CC - 0x00000000
< 0x1F2A09D0 - 0x00000000
---
> 0x1F2A09CC - 0x00004A4A
> 0x1F2A09D0 - 0x00004A4A
120,121c120,121
< 0x1F2A09DC - 0x00000000
< 0x1F2A09E0 - 0x00000000
---
> 0x1F2A09DC - 0x00004949
> 0x1F2A09E0 - 0x00004949
```

## While audio is playing

``` diff
--- /tmp/a
+++ /tmp/b
@@ -63,13 +63,13 @@
 0x1F2A04F8 - 0x00000000
 0x1F2A04FC - 0x00000000
 0x1F2A0500 - 0x00002096
-0x1F2A0504 - 0x0000A000
+0x1F2A0504 - 0x00008000
 0x1F2A0508 - 0x00000FE8
 0x1F2A050C - 0x00002000
 0x1F2A0510 - 0x0000007D
 0x1F2A0514 - 0x00000000
 0x1F2A0518 - 0x00001F00
-0x1F2A051C - 0x00001F5B
+0x1F2A051C - 0x00001F13
 0x1F2A0520 - 0x0000000B
 0x1F2A0524 - 0x00000000
 0x1F2A0528 - 0x00000000
@@ -113,8 +113,8 @@
 0x1F2A05C0 - 0x00000000
 0x1F2A05C4 - 0x00000000
 0x1F2A05C8 - 0x00000000
-0x1F2A05CC - 0x00000B66
-0x1F2A05D0 - 0x0000E0F4
+0x1F2A05CC - 0x000002A6
+0x1F2A05D0 - 0x0000FA2E
 0x1F2A05D4 - 0x00000000
 0x1F2A05D8 - 0x00000000
 0x1F2A05DC - 0x0000A400
 ```
 
 ``` diff
 --- /tmp/b
+++ /tmp/c
@@ -62,14 +62,14 @@
 0x1F2A04F4 - 0x00000000
 0x1F2A04F8 - 0x00000000
 0x1F2A04FC - 0x00000000
-0x1F2A0500 - 0x00002096
-0x1F2A0504 - 0x00008000
+0x1F2A0500 - 0x00000496
+0x1F2A0504 - 0x0000A000
 0x1F2A0508 - 0x00000FE8
 0x1F2A050C - 0x00002000
 0x1F2A0510 - 0x0000007D
 0x1F2A0514 - 0x00000000
 0x1F2A0518 - 0x00001F00
-0x1F2A051C - 0x00001F13
+0x1F2A051C - 0x00001F42
 0x1F2A0520 - 0x0000000B
 0x1F2A0524 - 0x00000000
 0x1F2A0528 - 0x00000000
@@ -113,8 +113,8 @@
 0x1F2A05C0 - 0x00000000
 0x1F2A05C4 - 0x00000000
 0x1F2A05C8 - 0x00000000
-0x1F2A05CC - 0x000002A6
-0x1F2A05D0 - 0x0000FA2E
+0x1F2A05CC - 0x0000ED83
+0x1F2A05D0 - 0x000019C3
 0x1F2A05D4 - 0x00000000
 0x1F2A05D8 - 0x00000000
 0x1F2A05DC - 0x0000A400
 ```

``` diff
--- /tmp/a
+++ /tmp/b
@@ -96,33 +96,33 @@
 0x1F2A077C - 0x00000001
 0x1F2A0780 - 0x00000000
 0x1F2A0784 - 0x00000000
-0x1F2A0788 - 0x00000B6C
-0x1F2A078C - 0x00001D39
-0x1F2A0790 - 0x00005A0F
-0x1F2A0794 - 0x00007FFF
+0x1F2A0788 - 0x0000EE92
+0x1F2A078C - 0x0000EB34
+0x1F2A0790 - 0x00007847
+0x1F2A0794 - 0x00007379
 0x1F2A0798 - 0x00000000
 0x1F2A079C - 0x00000000
 0x1F2A07A0 - 0x00000000
 0x1F2A07A4 - 0x00000000
 0x1F2A07A8 - 0x00000000
-0x1F2A07AC - 0x00000001
-0x1F2A07B0 - 0x0000FFFF
+0x1F2A07AC - 0x0000FFFB
+0x1F2A07B0 - 0x0000FFFC
 0x1F2A07B4 - 0x00000000
 0x1F2A07B8 - 0x00000000
 0x1F2A07BC - 0x000078F4
 0x1F2A07C0 - 0x00000000
 0x1F2A07C4 - 0x00000000
-0x1F2A07C8 - 0x0000FFFC
-0x1F2A07CC - 0x00000007
+0x1F2A07C8 - 0x00000010
+0x1F2A07CC - 0x0000FFFF
 0x1F2A07D0 - 0x00000000
 0x1F2A07D4 - 0x00000000
-0x1F2A07D8 - 0x0000FFF6
-0x1F2A07DC - 0x00000000
+0x1F2A07D8 - 0x0000FFF5
+0x1F2A07DC - 0x00000008
 0x1F2A07E0 - 0x000078F4
 0x1F2A07E4 - 0x00000000
 0x1F2A07E8 - 0x00000000
 0x1F2A07EC - 0x00000000
-0x1F2A07F0 - 0x0000701C
+0x1F2A07F0 - 0x00006DDC
 0x1F2A07F4 - 0x00000000
 0x1F2A07F8 - 0x00000001
 0x1F2A07FC - 0x00000000
 ```
 
 ``` diff
 --- /tmp/a
+++ /tmp/b
@@ -110,7 +110,7 @@
 0x1F2A09B4 - 0x00000000
 0x1F2A09B8 - 0x00000000
 0x1F2A09BC - 0x00000000
-0x1F2A09C0 - 0x00000000
+0x1F2A09C0 - 0x00000050
 0x1F2A09C4 - 0x00000B0B
 0x1F2A09C8 - 0x00000000
 0x1F2A09CC - 0x00004A4A
 ```
 
 ``` diff
 @@ -30,8 +30,8 @@
 0x1F206874 - 0x00000000
 0x1F206878 - 0x00000000
 0x1F20687C - 0x00000000
-0x1F206880 - 0x00000040
-0x1F206884 - 0x00001EC3
+0x1F206880 - 0x00000080
+0x1F206884 - 0x0000F00F
 0x1F206888 - 0x00000000
 0x1F20688C - 0x00000000
 0x1F206890 - 0x00000000
 ```

## atop init from i2m kernel

```
0x206800 - 0x0a14
0x206804 - 0x0030
0x206808 - 0x0080
0x20680c - 0x0000
0x206810 - 0x0000
0x206814 - 0x0077
0x206818 - 0x0000
0x20681c - 0x0000
0x206820 - 0x3000
0x206848 - 0x0000
```
