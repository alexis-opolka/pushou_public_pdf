# NuShell in not a nutshell

Quelques articles paru dans linux-pratique de Benoît Benedetti sur NuShell m'ont donné envie de voir ce que peux faire cet outil.
Pour ceux qui ne le savent pas NuShell est un shell écrit en Rust, récent et dans l'air du temps. 
NewShell ne se contente pas d'être un shell pour Linux, MacOs et Windows mais il est aussi orienté "data" :

- "open" ou "fetch" vous permettent d'ouvrir des fichiers en local ou depuis internet.
- les pipelines, les outputs sous forme de tables permettent de manipuler lignes et colonnes.
- les formats d'échanges comme json permettent à nushell de communiquer avec de nombreux outils.

Voyons un exemple:
L'université planifie mon travail au travers d'un calendrier au format ical et nushell est capable de lire et parser un calendrier au format ical.

```
/home/pouchou/ownCloud/dev/nushell〉$moncal|where SUMMARY =~ SAE|first 5                                                                                                                                                                                                
╭───┬──────────────────────────────────────────────┬──────────────────────────────────────────────┬───────────────────────────────┬────────────┬───────────────────────────────────────────────────────────────────────────────────────╮
│ # │                   DTSTART                    │                    DTEND                     │            SUMMARY            │  LOCATION  │                                      DESCRIPTION                                      │
├───┼──────────────────────────────────────────────┼──────────────────────────────────────────────┼───────────────────────────────┼────────────┼───────────────────────────────────────────────────────────────────────────────────────┤
│ 0 │ Fri, 18 Nov 2022 13:00:00 +0000 (in 2 weeks) │ Fri, 18 Nov 2022 14:15:00 +0000 (in 2 weeks) │ SAE3D04 Infra. Virtualisée-CM │ B202-CLOUD │   DEVCLOUD DEVCLOUD-APP POUCHOULON   JEAN MARC A valider(Exporté le:04/11/2022 02:28) │
│ 1 │ Fri, 18 Nov 2022 14:30:00 +0000 (in 2 weeks) │ Fri, 18 Nov 2022 15:45:00 +0000 (in 2 weeks) │ SAE3D04 Infra. Virtualisée-TD │ B202-CLOUD │   DEVCLOUD DEVCLOUD-APP A valider POUCHOULON   JEAN MARC(Exporté le:04/11/2022 02:28) │
│ 2 │ Fri, 18 Nov 2022 16:00:00 +0000 (in 2 weeks) │ Fri, 18 Nov 2022 17:15:00 +0000 (in 2 weeks) │ SAE3D04 Infra. Virtualisée-E  │ B202-CLOUD │   DEVCLOUD DEVCLOUD-APP POUCHOULON   JEAN MARC A valider(Exporté le:04/11/2022 02:28) │
│ 3 │ Mon, 05 Dec 2022 07:00:00 +0000 (in 4 weeks) │ Mon, 05 Dec 2022 08:15:00 +0000 (in 4 weeks) │ SAE3D04 Infra. Virtualisée-E  │ B202-CLOUD │   DEVCLOUD DEVCLOUD-APP POUCHOULON   JEAN MARC A valider(Exporté le:04/11/2022 02:28) │
│ 4 │ Mon, 05 Dec 2022 08:30:00 +0000 (in 4 weeks) │ Mon, 05 Dec 2022 09:45:00 +0000 (in 4 weeks) │ SAE3D04 Infra. Virtualisée-E  │ B202-CLOUD │   DEVCLOUD DEVCLOUD-APP POUCHOULON   JEAN MARC A valider(Exporté le:04/11/2022 02:28) │
╰───┴──────────────────────────────────────────────┴──────────────────────────────────────────────┴───────────────────────────────┴────────────┴───────────────────────────────────────────────────────────────────────────────────────╯
```



