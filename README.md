# Awesome-Online-Document-Services

# Top Online Document Services Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted PDF Toolkits, Browser-Local Processing & Privacy-First Document Workflows*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Online Document Services**. These tools handle the everyday document work that used to require desktop software or cloud uploads — merging, splitting, compressing, converting, OCR-ing, signing, and annotating PDFs — with a spectrum running from subscription-based web suites to self-hosted platforms and browser-local editors that never upload your files.

**Examples** include Stirling-PDF, BentoPDF, PdfDing, and Docmost (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, client-side processing, and transparent document handling — especially relevant as **Stirling-PDF has become the #1 PDF application on GitHub** with 50+ tools in a single Docker container, and **BentoPDF** runs entirely in the browser with 130+ tools and no uploads [citation:1][citation:4].

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Adobe Acrobat PDF Pack** — **The reference commercial online PDF service.** Convert, combine, sign, and export PDFs from any browser with Creative Cloud integration. **Subscription-based** as part of Acrobat plans. **Trade-offs**: documents are uploaded to Adobe's servers for processing, and the free tier is limited [citation:5]. **Best for Adobe subscribers** wanting a familiar web interface without self-hosting.

- **Smallpdf Pro** — **The polished web-based PDF suite.** Merge, split, compress, convert, and e-sign with a clean interface. **Free tier is capped at 2 tasks per day**; Pro is around $9–10/month [citation:5]. **Trade-offs**: files are uploaded to Smallpdf's servers — unsuitable for confidential documents. **Best for quick one-off tasks** on non-sensitive files.

- **iLovePDF Premium** — **The popular freemium PDF toolkit.** Web-based tools for merge, split, compress, and convert. **Free tier is web-only with per-file size caps and daily task limits** [citation:5]. **Best for occasional use** where upload risk is acceptable.

## Open-Source GitHub Projects

- **Stirling-PDF** — **The leading self-hosted PDF platform and the #1 PDF application on GitHub.** Open-core licensed (MIT-adjacent with paid tiers), **50+ tools in one Docker container**: merge, split, rotate, OCR (100+ languages), convert to/from Office formats, sign, redact, compress, watermark, and more [citation:5][citation:6]. **Stateless by default** — no database, files processed on your own server and deleted immediately after; nothing is uploaded to a third party [citation:5]. **Deployment**: `docker run -p 8080:8080 docker.stirlingpdf.com/stirlingtools/stirling-pdf` [citation:6]. **Resource requirements**: ~1–2 GB RAM minimum for the Java/Spring Boot app; the "ultra-lite" image runs in 1 GB [citation:9]. **Desktop client** available for Windows, macOS, and Linux, packaging the web UI and local server into one native app [citation:6]. **The honest caveats**: **OCR quality (Tesseract) is below Adobe Acrobat** for complex scanned pages, **Java heap needs tuning** to avoid OOM on large files, and **text editing is still in alpha** [citation:9]. **Best for teams wanting a private, self-hosted Acrobat replacement** with the broadest tool coverage in one place.

- **BentoPDF** — **The privacy-first, browser-local PDF toolkit.** **AGPL-3.0 or commercial ($49 lifetime)**, with **130+ tools that run entirely in your browser via WebAssembly** — files never leave your device, no server uploads, no account required [citation:4]. **Covers the full workflow**: convert, edit, organize, secure, annotate, OCR, and sign [citation:4]. **Self-hostable via Docker** (`ghcr.io/alam00000/bentopdf-simple:latest`) or any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages) [citation:2][citation:4]. **No file size caps, no usage limits** [citation:4]. **Air-gapped support** via an automated script that prepares a self-contained bundle [citation:4]. **Tech stack**: TypeScript + Vite, with pdf-lib (MIT), pdfjs-dist (Apache 2.0), PyMuPDF (AGPL), Ghostscript (AGPL), and LibreOffice WASM for Office conversions [citation:4]. **The honest caveat**: **Office file conversions require SharedArrayBuffer**, which needs HTTPS when accessed over a LAN IP [citation:4]. **Best for organizations needing self-hosted PDF processing with zero server-side file exposure** — even a compromised server never sees your documents.

- **PdfDing** — **The self-hosted PDF manager, viewer, and annotation tool.** Django-based, with **seamless browser-based PDF viewing across devices**, **memory of reading position**, **multi-level tagging, starring, and archiving**, **annotation (comments, highlighting, drawings)**, **highlight and comment export**, **SSO via OIDC**, **share links with access control and QR codes**, **two-factor authentication (TOTP + WebAuthn)**, and **Markdown notes** [citation:15]. **Lightweight**: uses SQLite by default — no additional database containers needed, runs on cheap hardware [citation:15]. **Received a grant from the NGI Zero Commons Fund** (funded by the European Commission), with 1,300+ GitHub stars and 125,000+ Docker pulls [citation:15]. **The honest boundary**: **more document shelf/reader than full editor** — it manages your library and annotation layer rather than rewriting existing text. **Best for individuals and teams** wanting a personal PDF library with reading management, annotation, and sharing, accepting that it is not a full Acrobat replacement.

- **ComPDF Self-Hosted** — **The Docker-deployable PDF editor and converter center.** Open-source, part of the ComPDF/KDAN ecosystem, with a **ready-to-use web UI** for PDF editing (merge, split, rotate, insert/delete/extract pages, watermark, encrypt/decrypt) and **conversion across PDF, Office, HTML, TXT, CSV, RTF, JSON, and images** [citation:10]. **Includes a dashboard console** for API key management, usage statistics, license status, operation logs, and account management [citation:10]. **Quick start**: `docker compose up -d`, with a default admin account on first deployment [citation:10]. **The honest caveat**: **the free license includes watermarking and page limits** — enterprise license removes watermarks, page limits, and enables batch processing [citation:10]. **Best for enterprises** wanting a self-hosted document processing platform with API management and commercial support options.

### Additional Strong Open-Source Options

- **ranuts/document** — **Local-first browser editor for Word, Excel, PowerPoint, and PDF.** Open-source, with **core document processing running locally** — no account or Office installation required [citation:3]. **Edit `.docx`, `.xlsx`, `.pptx` and annotate PDFs**, export to PDF, and use optional AI assistance (experimental beta) with on-device or connected models [citation:3]. **PWA installable, self-hostable via Docker** (`ghcr.io/ranuts/document:latest`), and embeddable via iframe API [citation:3]. **Best for users** wanting an Office-compatible editor in the browser with local-first processing.

- **ONLYOFFICE Docs** — **The collaborative online office suite with PDF editing.** Open-source Community Edition (AGPL v3, up to 20 simultaneous connections), with document, spreadsheet, presentation, form, and **PDF editors** [citation:8]. **Real-time collaborative editing**, AI-powered assistants, reviewing, spell-checking, and 46-language interface [citation:8]. **Integrates with Nextcloud, ownCloud, Moodle, and other sync & share solutions** [citation:8]. **Best for teams** wanting a full office suite with PDF editing and real-time collaboration on their own infrastructure.

**Frameworks for building custom systems**: Combine **Stirling-PDF** for a self-hosted web UI covering 50+ operations with Docker deployment and a desktop client, **BentoPDF** for browser-local processing where files never touch a server, **PdfDing** for a personal PDF library with reading management and annotation, and **ComPDF Self-Hosted** for an enterprise document processing platform with API management — to build an online document services stack tailored to your need for breadth versus simplicity, web versus local processing, and privacy requirements.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Online document services differ significantly in processing model, privacy posture, and deployment requirements. **Stirling-PDF processes files server-side** (though deletes them immediately) — suitable for self-hosted infrastructure you control, not for shared hosting [citation:5]. **BentoPDF processes entirely in the browser** — files never leave your device, making it the safer choice for truly sensitive documents [citation:4]. **PdfDing is a management and annotation tool**, not a full PDF editor . **ComPDF's free license includes watermarks and page limits** — enterprise license required for unrestricted use [citation:10]. **Smallpdf and iLovePDF upload documents to their servers** — unsuitable for confidential material [citation:5]. **Stirling-PDF's OCR quality is below Adobe Acrobat**, and its text editing is still in alpha [citation:9].
- Self-hosted open-source solutions require proper resource allocation (Stirling-PDF needs 1–2 GB RAM for the Java app), Docker deployment configuration, and awareness that OCR of large archives is CPU-intensive.

---

**Made for teams and individuals handling documents without handing them to a stranger's server.**
Let's make online document services more open, privacy-preserving, and self-hostable.
