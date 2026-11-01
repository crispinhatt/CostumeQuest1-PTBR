# Costume Quest 1 + Grubbins on Ice — Tradução PT-BR

**Tradução não oficial para o Português Brasileiro** do jogo *Costume Quest* (2010) e sua expansão *Grubbins on Ice* (2011), desenvolvidos pela Double Fine Productions.

---

## 📦 Download

Acesse a aba [**Releases**](../../releases) e baixe o arquivo `CQ1_PTBR_Final.zip` da versão mais recente.

---

## 🎃 Sobre

| | |
|---|---|
| **Jogo** | Costume Quest + DLC Grubbins on Ice |
| **Desenvolvedor** | Double Fine Productions |
| **Plataforma** | PC (Steam) |
| **Versão traduzida** | Steam (Build 2024) |
| **Strings traduzidas** | 3.440 (CQ1) + 791 (DLC) = **4.231 strings — 100%** |
| **Encoding** | UTF-8 |
| **Autor** | [crispinhatt](https://github.com/crispinhatt) |

---

## 🛠️ Instalação

1. Localize a pasta do jogo via Steam:
   `Biblioteca → Costume Quest → ⚙️ → Gerenciar → Navegar pelos arquivos locais`

2. Navegue até a pasta `Win\Packs\`

3. Faça **backup** dos arquivos originais:
   ```
   RgB_Stuff.~h  →  RgB_Stuff.~h.bak
   RgB_Stuff.~p  →  RgB_Stuff.~p.bak
   DLC1_Stuff.~h →  DLC1_Stuff.~h.bak
   DLC1_Stuff.~p →  DLC1_Stuff.~p.bak
   ```

4. Copie os arquivos da pasta `Win/Packs/` do zip para a pasta do jogo

5. Inicie o jogo — os textos estarão em Português Brasileiro!

### Desinstalação

Restaure os arquivos `.bak` renomeando-os de volta, ou use  
**Steam → Propriedades → Arquivos locais → Verificar integridade dos arquivos do jogo**

---

## 📸 Screenshots

> *(adicione screenshots aqui)*

---

## 🔧 Detalhes Técnicos

O jogo utiliza o formato proprietário **Double Fine Pack Format (dfpf)**, desenvolvido para a engine Buddha da Double Fine.

| Pack | Versão dfpf | Conteúdo |
|------|------------|----------|
| `RgB_Stuff.~h/.~p` | v2 | StringTables principais do CQ1 |
| `DLC1_Stuff.~h/.~p` | v2 | StringTables da DLC Grubbins on Ice |

### Pipeline de tradução

1. **Extração** — parser Python do formato dfpf v2 (bitfields big-endian de 16 bytes com sobreposição entre records)
2. **Tradução** — API Claude Sonnet via Artifact React, lotes de 60 strings
3. **Repack** — encode inverso dos bitfields + substituição cirúrgica dos StringTables no `.~p`

### Formato StringTable (dfpf v2)

```
[uint32 LE: tamanho - 4][0x31][StringTable{LineCodeData={
ID=LineCodeData{Text="texto";VolumeDB=0;Character=X;SoundCue=;};
...};};}]\x00
```

Encoding: **UTF-8** (o jogo lê nativamente UTF-8, confirmado pelo StringTable em espanhol do original).

---

## 📋 Glossário Principal

| EN | PT-BR |
|----|-------|
| Trick or treat | Doce ou travessura |
| Candy | doce(s) / bala(s) |
| Costume | fantasia |
| Battle Stamps | Selos de Batalha |
| Candy Pail | balde de doces |
| Monster | monstro |
| Quest | missão |
| Experience Points | Pontos de Experiência |
| Creepy Treat Cards | Cartinhas Sinistrosas |

---

## 📁 Estrutura do Repositório

```
├── Win/
│   └── Packs/
│       ├── RgB_Stuff.~h        ← Header do pack principal CQ1
│       ├── RgB_Stuff.~p        ← Dados do pack principal CQ1
│       ├── DLC1_Stuff.~h       ← Header do pack DLC
│       └── DLC1_Stuff.~p       ← Dados do pack DLC
├── backup/
│   ├── CQ1_strings_ptbr.json   ← Strings traduzidas CQ1 (EN + PT-BR)
│   └── DLC1_strings_ptbr.json  ← Strings traduzidas DLC (EN + PT-BR)
├── tools/
│   └── dfpf_parser.py          ← Parser/extrator do formato dfpf
└── README.md
```

---

## ⚠️ Aviso Legal

Esta é uma tradução **não oficial** criada por fãs, sem qualquer vínculo com a Double Fine Productions ou THQ Nordic. Distribuída gratuitamente para fins educacionais e de preservação. *Costume Quest* é propriedade intelectual de seus respectivos detentores.

---

## 🤝 Outros Projetos

- [Kill Team PT-BR](https://github.com/crispinhatt/KillTeam-PTBR)
- [Space Hulk: Deathwing EE PT-BR](https://github.com/crispinhatt/40kDeathwingEEBR)
- [Dawn of War: Definitive Edition PT-BR](https://github.com/crispinhatt/DoWDE-Traducao-PTBR)
- [Legacy of Dorn PT-BR](https://github.com/crispinhatt/40kHeraldBR)
