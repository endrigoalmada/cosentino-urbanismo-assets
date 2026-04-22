---
projeto: parceria-cosentino
subprojeto: site-institucional
tipo: manifest-selecao-assets
destino: upload no Lovable (projeto atual)
data: 2026-04-22
total: 320 MB
tags: [cosentino, lovable, assets, manifest]
---

# Seleção curada de assets para o Lovable

Pacote de arquivos prontos para upload no projeto Lovable atual da Cosentino Urbanismo. Todos vieram do OneDrive mirror (`../onedrive-mirror/`) e foram selecionados e renomeados para uso semântico direto no site.

## Logos (`logos/`, 2,5 MB)

**Arquivos vetoriais (fonte, para produção futura)**
- `empreendimentos-cosentino.ai` — Adobe Illustrator com os 6 logos em vetor
- `empreendimentos-cosentino.pdf` — PDF com 6 páginas, 1 logo por página, vetorial, 328 KB

**PNGs prontos para uso direto no site (export em preto sobre transparente)**
- `01-jardim-europa.png` — monograma circular + wordmark. Entra no card do **Jardim Europa V** na seção Portfólio e no footer como identificador da série
- `02-splendore-resort-residence.png` — wordmark thin extralarga + subline "Resort Residence". Entra no card do **Splendore** e na landing de case do Prêmio Master
- `03-jardim-das-americas.png` — monograma floral + wordmark duas linhas. Entra no card do **Jardim das Américas X** e histórico dos 10 entregues
- `04-porto-seguro-condominio.png` — escudo heráldico. Entra só no portfólio "Entregues" como histórico
- `05-jardim-florenca.png` — display serif decorativa. Entra só no portfólio "Entregues"
- `06-cidade-jardim-condominio.png` — abstrato + wordmark moderno. Entra como marco histórico (primeiro condomínio fechado do MT, 1994)

**Logo da marca-mãe "Cosentino Urbanismo" — AINDA SERÁ CONSTRUÍDO**

Ver o arquivo `lovable-briefs/prompt-logo-cosentino-urbanismo.md` ao lado deste para o prompt pronto a colar no Claude Design e gerar variações. Enquanto não existir, usar no header apenas o wordmark tipográfico:

```
COSENTINO
urbanismo (em mono, tracking largo, dourado #C9A84C)
```

## Hero (`hero/`, 268 MB)

**Fotografia aérea para as seções hero**
- `europa-v-aerea-01.jpg` — 1ª opção para hero da landing /empreendimentos/europa-v
- `europa-v-aerea-02.jpg` — 2ª opção, fallback ou uso alternativo no header da seção Território

**Vídeos aéreos DJI (candidatos para hero fullbleed)**
- `europa-v-hero-candidato-A.mov` (128 MB) — revisar visualmente e escolher
- `europa-v-hero-candidato-B.mov` (123 MB) — revisar visualmente e escolher

Como usar: o hero da Home e da landing do Europa V reserva um `<video>` fullbleed com overlay ink 55%. Até o vídeo final do Kling 3.0 ("Primavera de ontem → Primavera do futuro") estar pronto, usar um destes dois MOVs do drone DJI como placeholder cinematográfico real. Precisa ser transcodificado para MP4 H.264 (720p ou 1080p) otimizado para web antes do upload no Lovable, senão trava a performance.

**Comando de transcode sugerido (fazer antes do upload):**

```bash
ffmpeg -i europa-v-hero-candidato-A.mov \
  -c:v libx264 -preset slow -crf 23 \
  -vf "scale=1920:-2" -an -movflags +faststart \
  europa-v-hero-web.mp4
```

## Galeria editorial (`galeria/`, 43 MB)

Cinco fotografias aéreas para o mosaico da seção 05 (Galeria editorial mosaico) no site. Grid masonry recomendado: 1 grande (07), 2 médias (03, 05), 2 pequenas (04, 06).

- `europa-v-aerea-03.jpg`
- `europa-v-aerea-04.jpg`
- `europa-v-aerea-05.jpg`
- `europa-v-aerea-06.jpg`
- `europa-v-aerea-07.jpg`

Todos podem ser convertidos para WebP para reduzir peso antes do upload:

```bash
for f in *.jpg; do cwebp -q 82 "$f" -o "${f%.jpg}.webp"; done
```

## Splendore (`splendore/`, 6,7 MB)

Três peças de comunicação do Splendore Resort Residence (empreendimento em obras, case do Prêmio Master 2026). Podem virar imagens de card no Portfólio ou fundo da futura `/empreendimentos/splendore`.

- `splendore-01.png`
- `splendore-02.png`
- `splendore-03.png`

## Portfolio (`portfolio/`, vazia)

Pasta reservada. Quando tiver:
- Imagens aéreas do Jardim das Américas X (427 lotes, 51,37 ha)
- Imagens do Cidade Jardim histórico
- Outros empreendimentos entregues

Adicionar aqui.

## Como usar no Lovable

1. Abre o projeto Lovable atual da Cosentino Urbanismo
2. Vai em **Assets** (ou **Files**) e faz upload em lote:
   - Primeiro os 6 PNGs de logos
   - Depois as 7 fotos aéreas (jpg ou webp transcodada)
   - Opcional: 1 dos vídeos MOV transcodado pra MP4
3. Cola o brief de refinamento (`lovable-briefs/02-home-refinamento-v2.md`) no chat do projeto Lovable pedindo pra aplicar as mudanças
4. Revisa cada seção e aprova

## Pendências

- [ ] Transcodificar os 2 MOVs em MP4 H.264 web-ready (ou pular direto pro Kling 3.0 quando estiver pronto)
- [ ] Gerar logo oficial **Cosentino Urbanismo** no Claude Design (ver `lovable-briefs/prompt-logo-cosentino-urbanismo.md`)
- [ ] Receber do Willian mais imagens dos empreendimentos (Jardim das Américas X especialmente)
- [ ] Buscar no vault ou no OneDrive uma foto do Edgard Cosentino (pai ou filho) pra seção Sobre/Fundadores
