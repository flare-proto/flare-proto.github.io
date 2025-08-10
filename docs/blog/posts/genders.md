---
date: 2025-07-25
comments: true
tags:
    - Open For Contribution
---
# Genders
Graph of as many genders as I could find
<!-- more -->
!!! warning
    Not all connections are shown, to make this actualy readable
```mermaid
flowchart LR
    Gender

    Cis
    Gender-->Cis
 
    Gender-->Multigender:::multigender
    Multigender-->Bigender:::multigender
    Multigender-->Plurigender:::multigender

    Trans
    Gender-->Trans

    Nonbinary
    Trans-->Nonbinary

    Nonbinary-->Pangender:::multigender
    Multigender-->Pangender

    Agender
    Nonbinary-->Agender

    Genderqueer
    Nonbinary-->Genderqueer

    Neutrois
    Nonbinary-->Neutrois

    Gendervoid
    Nonbinary-->Gendervoid

    Androgyne
    Nonbinary-->Androgyne

    Absorgender
    Nonbinary-->Absorgender

    Echogender
    Nonbinary-->Echogender

    Demigender
    Nonbinary-->Demigender:::demi
    
    Demigender-->Demiandrogyne:::demi
    Demigender-->Demigirl:::demi
    Demigender-->Demiboy:::demi
    Demigender-->Demitransgender:::demi
    Demigender-->Deminonbinary:::demi
    Androgyne-->Demiandrogyne:::demi

    Idingender
    Nonbinary-->Idingender
    Genderfaun
    Idingender-->Genderfaun
    Genderfae
    Idingender-->Genderfae
    Genderfluid
    Idingender-->Genderfluid:::fluix
    Genderfluid-->Demifluid:::fluix
    Demigender-->Demifluid
    Genderfluid-->Mutogender:::fluix
    Genderspike
    Genderfluid-->Genderspike:::fluix
    Genderspike-->Bigenderspike:::multigender
    Genderspike-->Femspike:::fluix

    Genderspike-->Fem-spike:::fluix
    Masc-spike
    Genderspike-->Masc-spike:::fluix

    Perifluid
    Genderfluid-->Perifluid:::fluix
    Cassfluid
    Genderfluid-->Cassfluid:::fluix
    Xenofluid
    Genderfluid-->Xenofluid:::fluix
    
    Genderglitch
    Genderfluid-->Genderglitch:::fluix

    Uxingender
    Nonbinary-->Uxingender
    Uxingender-->Genderflux:::fluix
    Uxingender-->Anogender

    Genderfluid-->Fluidflux:::fluix
    Genderflux-->Fluidflux 
    Fluidflux-->Genderslide:::fluix

    Xenogender
    Nonbinary-->Xenogender

    Glitchgender
    Xenogender-->Glitchgender:::fluix
    Glitchgender-->Genderglitch
 
    Nonbinary-->Offgender

    Nonbinary-->Rosboy
    Nonbinary-->Azurgirl

    Nonbinary-->Fingender

    Nonbinary-->Cassgender

    
    classDef fluix stroke:#f80
    classDef multigender stroke:#f00
    classDef demi stroke:#ff0
```
## Resources
- [https://gender.fandom.com](https://gender.fandom.com)
- [https://lgbtqia.wiki/wiki](https://lgbtqia.wiki/wiki)