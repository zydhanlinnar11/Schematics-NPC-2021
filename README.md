# Schematics NPC 2021

Almost all stuffs related to Schematics NPC 2021 and can be known by public.

## Problemsetting Stuff

### Problemset

Problemset for Schematics NPC 2021 is available on [TLX](https://tlx.toki.id)

| Round              | Problemset Link                                                            |
| ------------------ | -------------------------------------------------------------------------- |
| Preliminary Senior | [Link](https://tlx.toki.id/problems/schematics-2021-npc-senior-penyisihan) |
| Preliminary Junior | [Link](https://tlx.toki.id/problems/schematics-2021-npc-junior-penyisihan) |
| Final Senior       | [Link](https://tlx.toki.id/problems/schematics-2021-npc-senior-final)      |
| Final Junior       | [Link](https://tlx.toki.id/problems/schematics-2021-npc-junior-final)      |

### Editorial

#### PDF Version

| Round              | Problemset Link                                                 |
| ------------------ | --------------------------------------------------------------- |
| Preliminary Senior | [Link](../Schematics-NPC-2021/editorial/preliminary-senior.pdf) |
| Preliminary Junior | [Link](../Schematics-NPC-2021/editorial/preliminary-junior.pdf) |
| Final Senior       | [Link](../Schematics-NPC-2021/editorial/final-senior.pdf)       |
| Final Junior       | [Link](../Schematics-NPC-2021/editorial/final-junior.pdf)       |

#### Web Version

Web-based version can be accessed from [Problemset](#problemset)

### Solutions

TBD

### Testdata

TBD

### Scoreboard and Online Judge URL

| Name   | Online Judge URL                          |
| ------ | ----------------------------------------- |
| Senior | [Link](https://senior.schematics-npc.com) |
| Junior | [Link](https://junior.schematics-npc.com) |

### Guidebook

| Name   | Link                                                    |
| ------ | ------------------------------------------------------- |
| Senior | [Link](./guidebook/schematics-npc-senior-guidebook.pdf) |
| Junior | [Link](./guidebook/schematics-npc-junior-guidebook.pdf) |

## Technical Stuff

### Online Judge

Online judge is a platform to judge or grade contestant submission and rank them based on ICPC / IOI / other rules. In Schematics NPC 2021, we use ICPC-style scoring for senior category and IOI-style for junior category. These are online judge that we used:

| Category | Online Judge    |
| -------- | --------------- |
| Senior   | DOMJudge v7.3.3 |
| Junior   | DMOJ v2.1       |

DMOJ is amazing but there is no support for freezing scoreboard and clarifications system little bit confusing. Maybe [Judgels](https://github.com/ia-toki/judgels) can be a good alternative.

### Judgehost / Judge Server

Online judge can't judge by itself. They use a program called judgehost / judgeserver to compile and score contestant submissions. For each online judge, we use default judgehost provided by online judge.

We can't use only 1 judgehost because it would be so slow to judge submission from ≥ 400 contestant. These are all judgehost we used for each online judge:

| Online Judge    | Judgehost                                                                               |
| --------------- | --------------------------------------------------------------------------------------- |
| DOMJudge v7.3.3 | 9 (4 Standard_B2s Azure VM, 1 GCP Instance splitted to 5 daemons (6 GB memory, 2 vCPU)) |
| DMOJ v2.1       | 6 (4 Standard_B1s Azure VM, 2 GCP Instance 2 GB memory, 2 vCPU)                         |

You can look at Azure VM specifications [here](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-b-series-burstable)

### ICPC Resolver

For senior category, we use resolver to display scoreboard activities during freeze period to contestant (This will bring ICPC World Final / Regional contest experience).

Repository URL: [sch-npc-resolver](https://github.com/zydhanlinnar11/sch-npc-resolver)

### Main Online Judge Server Specification

Schematics NPC 2021 was sponsored by [Rumahweb](https://www.rumahweb.com/) and they send us VPS with 8 GB RAM (we don't know another specification).

### Public Scoreboard

We have [public scoreboard](https://www.schematics-npc.com) that developed using Vue.js for front-end and Laravel for back-end. We need back-end although every online judge has its own API because back-end can minimize fetching frequency (1 minute fetch frequency and cached locally) so it wouldn't add major load to online judge compared to direct fetching from front-end.

### Deployment

All online judge and judgehosts were dockerized so we just need to install docker and download image in remote machine. Public scoreboard deployed in [Vercel](https://vercel.com).
