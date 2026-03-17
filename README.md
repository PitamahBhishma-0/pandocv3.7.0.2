# 🐳 pandocv3.7.0.2

A lightweight Docker image based on **Debian Bookworm Slim**, bundled with Pandoc 3.7.0.2 and XeLaTeX for high-quality Markdown → PDF conversion with full LaTeX support. Built for developers, academics, researchers, and automation pipelines.

## 📦 What's Included

✅ Pandoc 3.7.0.2 (static binary)  
✅ Full XeLaTeX stack (texlive-xetex, texlive-latex-extra, etc.)  
✅ Clean, minimal Debian Slim base  
✅ Pre-installed fonts: noto, lmodern, emoji support  
✅ ~875MB (slimmed down for a LaTeX-capable image)

## 🚀 Usage Examples

✅ View Pandoc version  
`docker run --rm ~home/pandocv3.7.0.2:version1 --latest`

✅ Convert Markdown to PDF  
`docker run --rm -v $(pwd):/data ~home/pandocv3.7.0.2:latest /data/input.md -o /data/output.pdf`

✅ Convert Markdown to DOCX  
`docker run --rm -v $(pwd):/data ~home/pandocv3.7.0.2:latest /data/input.md -o /data/output.docx`

📁 Working Directory  
All operations run inside `/workspace` by default. Use `-v $(pwd):/workspace` or specify your own working directory when running the container.

🛠️ Entrypoint & CMD  
This image is configured with:  
`ENTRYPOINT ["pandoc"]`  
`CMD ["--help"]`

This means you can treat it like a CLI tool:  
`docker run --rm ~home/pandocv3.7.0.2:version1 input.md -o output.pdf`

📧 Maintainer  
Maintained by Gaurav Basyal  
Open to contributions, suggestions, and feedback.

✅ Use Cases  
CI/CD pipelines for academic publishing  
Resume generation with LaTeX templates  
Instant Markdown → PDF conversion  
GitHub Actions for documentation generation  
Local dev tools without installing Pandoc or LaTeX locally

💡 Pro Tips  
Use `--pdf-engine=xelatex` for full font and Unicode support  
Add custom LaTeX templates via `--template=/data/custom.tex`  
Include citations using `--citeproc` with `.bib` files and CSL styles

🐧 Based On  
debian:bookworm-slim  
Official Pandoc static binaries  
Full XeLaTeX toolchain for PDF generation
