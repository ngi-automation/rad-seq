# Automated RAD-seq Installation Guide #
**For Agilent NGS Workstation Option B**

## Contents ##
1. [Description](#description)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Protocol](#protocol)
5. [License](#license)

## Description ##
This README describes how to set up NGI Stockholms RAD-seq method for the Agilent NGS Workstation. This protocol can be used to prepare up to 96 samples with the in-house RAD-seq protocol.

## Requirements ##
- Agilent NGS Workstation :warning: <i><b>Option B only</i></b>
- Consumables
   - Eppendorf twin.tec 96 PCR plate (Eppendorf, cat# 0030 128.672 (int); 951020460 (US))
   - Nunc deepwell 1.3 mL plate (Thermo Scientific, cat# 260251)
   - ABgene 2.2 mL storage plate Mk.II (Thermo Scientific, cat# AB-0933)
- Deepwell plate adaptor on position 6 (Agilent Technologies, cat# G5498B#012) and supporting device file
- Labware definitions*
- Liquid classes definition*

\* provided in `all_labware_liquids.vzp`

#### Included files ####
```
README.md
all_labware_liquids.vzp
illumina_double-spri.pro
illumina_spri.pro
rad-seq.VWForm
rad-seq.js
rad-seq.rst
rad-seq_ligation.pro
rad-seq_pcr.pro
rad-seq_reaction.pro
rad-seq_setup1.pro
rad-seq_setup2.pro
rad-seq_setup3.pro
rad-seq_setup4.pro
rad-seq_setup5.pro
resources
resources/clear_inventory.bat
resources/1313497517_media_controls_light_play.png
resources/clear_inventory.sql
resources/1313497192_media_controls_light_pause.png
```

## Installation ##
### Download files ###


##### Using Git #####
Clone into `https://github.com/ngi-automation/rad-seq.git` from the `Protocol Files` directory:

```bash
cd "C:\VWorks Workspace\Protocol Files"
git clone https://github.com/ngi-automation/rad-seq.git
```

Alternatively, download the compressed folder from:
[`https://github.com/ngi-automation/rad-seq/archive/master.zip`][zip]
and extract to `C:\VWorks Workspace\Protocol Files`. Rename the resulting `rad-seq-master` folder to `rad-seq`. The path to the folder containing the extracted files should then be `C:\VWorks Workspace\Protocol Files\rad-seq`.

### Configure ###
#### Labware and and liquid class definitions ####
Use the import feature in VWorks from `File › Import`in the toolbar and select the `all_labware_liquids.vzp` file included. See the [VWorks Knowledge Base][import] for more information.

#### Device files ####
Device files and profiles are system specific and will not be provided. The "standard" Bravo configuration is used in the RAD-seq protocols:

##### Standard configuration #####
Position | Type | Part#
-------: | ---- | -----
1&ndash;3, 8  | Deck Platepad | `G5498b#004`
4, 6     | Peltier Thermal Station (Inheco) | `G5498b#021`
5        | Orbital Shaking Station | `G5498b#033`
7        | Magnetic Bead Accessory | `G5498b#008`
9        | Thermal Station (ThermoCube) | `G5498b#036`/`7`/`8`

For reference see Agilent's [accessories catalog][catalog] for the Bravo.

:warning:  Each `.pro` file must have the correct device file set.

See the [VWorks Knowledge Base][device-file] for more information on how to select the device file.

## Protocol ##

Instructions are available as a [PDF file][sop].

## License ##
> Licensed under the Apache License, Version 2.0 (the "License");
> you may not use this file except in compliance with the License.
> You may obtain a copy of the License at
> 
> http://www.apache.org/licenses/LICENSE-2.0
>
> Unless required by applicable law or agreed to in writing, software
> distributed under the License is distributed on an "AS IS" BASIS,
> WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
> See the License for the specific language governing permissions and limitations under the License.

The full license can also be found in the file LICENSE and must included when redistributing the software.

If this method is used to generate results for publication we ask that you include a reference to this repository, something like:

```
Automation protocols made available by the National Genomics Infrastructure Stockholm at https://github.com/ngi-automation/rad-seq
```

*VWorks Automation Control*, *Bravo* and other things relating to the *Agilent NGS Workstation* are trademarks owned by Agilent Technologies, Inc. (Santa Clara, CA 95052-8058, US).

[email]: mailto:joel.gruselius@scilifelab.se "E-mail author"
[ngi]: https://portal.scilifelab.se/genomics/ "NGI Stockholm"
[scilife]: http://www.scilifelab.se/platforms/ngi/ "SciLifeLab"
[zip]: https://github.com/ngi-automation/rad-seq/archive/master.zip
[import]: http://www.velocity11.com/techdocs/AutomationSolutionsKB/vworks4_ug/11_Troubleshooting.15.03.html#2005458
[catalog]: http://www.chem.agilent.com/Library/catalogs/Public/5991-0369EN.pdf
[sop]: https://goo.gl/wA8sGi
[device-file]: http://www.velocity11.com/techdocs/AutomationSolutionsKB/vworks4_ug/02_CreateProtocolBasic.04.08.html#1981042

---

>[National Genomics Infrastructure][ngi] at [SciLifeLab][scilife]  
<joel.gruselius@scilifelab.se>  
Nov 2017
