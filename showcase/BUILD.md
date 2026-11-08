# Manual GitHub Showcase PDF build (macOS + Docker)

Use this inside a local checkout of https://github.com/fbrase799/fbrase799.

1. Extract this ZIP into the repository root. It creates `showcase/showcase.adoc`.
2. Run the commands below from the **repository root**.

```bash
mkdir -p showcase/images assets

curl -fL \
  'https://raw.githubusercontent.com/fbrase799/vehicle_configurator/main/docs/screenshots/vehicle_configurator_01_ferrari.png' \
  -o showcase/images/vehicle-configurator.png

curl -fL \
  'https://raw.githubusercontent.com/fbrase799/engineering_knowledge_assistant/main/docs/screenshots/engineering_knowledge_01_result.png' \
  -o showcase/images/knowledge-assistant.png

# Requires Calibri TTFs in showcase/fonts/ (Calibri.ttf, Calibrib.ttf, Calibrii.ttf, Calibriz.ttf).
docker run --rm \
  --user "$(id -u):$(id -g)" \
  -v "$PWD:/documents" \
  -w /documents \
  asciidoctor/docker-asciidoctor \
  asciidoctor-pdf \
  -a pdf-themesdir=showcase \
  -a pdf-theme=showcase \
  -a pdf-fontsdir=showcase/fonts \
  -o assets/Frank_Brase_GitHub_Showcase.pdf \
  showcase/showcase.adoc

open assets/Frank_Brase_GitHub_Showcase.pdf
```

3. Check the PDF: cover page; TOC and About this portfolio on one page; Knowledge Assistant then Vehicle Configurator; screenshots and links.
4. If satisfied, commit the source, screenshots, and generated PDF with `git add showcase assets/Frank_Brase_GitHub_Showcase.pdf` and `git commit`.

This is the **manual** build only. No GitHub Actions workflow is included yet.
