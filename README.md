# Mailson Rodrigues

**Biomedical scientist turned clinical-genomics software developer** — 15+ years in clinical laboratory diagnostics, postgraduate training in Medical Genetics & Genomics, now building bioinformatics and health software.
📍 Goiânia, Brazil · 🔗 [LinkedIn](https://linkedin.com/in/mailson-rodrigues) · 🧬 [ORCID 0000-0002-9281-5818](https://orcid.org/0000-0002-9281-5818)

---

## What I do

| Track | Focus |
|---|---|
| 🧬 **Clinical bioinformatics** | NGS analysis (FASTQ → BAM → VCF), variant annotation and interpretation (ACMG/AMP), reproducible pipelines, QC and provenance |
| 🏥 **Health software engineering** | Secure, auditable web platforms for clinical data: authentication/RBAC, audit trails, privacy by design (LGPD), regulated-software practices (IEC 62304, ISO 14971) |

What makes the combination useful: I know how a clinical laboratory actually works — what a variant report must say, what a reviewer needs to trust it — and I build software that respects those requirements.

## Featured project — GenCodeBio

A web-based clinical genomics platform: **VCF → QC → Ensembl VEP → ClinVar / gnomAD / PubMed → in-silico predictors → ACMG/AMP classification with source-verified citations → PDF report.**
Research Use Only; no real patient data. Production code is private; architecture and design decisions are public → **[gencodebio-showcase](https://github.com/mailson-rodrigues/gencodebio-showcase)**.

- **Evidence integrity by design:** a classification without a valid, verifiable citation is discarded and never stored.
- **Built to be audited:** RBAC, TOTP MFA, revocable server-side sessions, audit trail, rate limiting, security headers; documented risk register (ISO 14971 style), requirements traceability matrix and a preliminary ANVISA SaMD technical dossier.
- **Engineered for scale:** streaming VCF parsing, batched asynchronous processing for exome-sized inputs, signed-URL uploads.
- **International from day one:** UI in English, Portuguese, Spanish and French; stable API error codes; CI that fails if a translation is missing.
- **Zero-cost local profile** *(built and tested; hosted-instance upgrade pending)*: ports and adapters for queue, storage, e-mail and LLM; one `docker compose up` runs the whole stack on a laptop.
- **Local reference data** *(built and tested)*: Ensembl VEP official cache as a local service (equivalence with the REST API checked on 330/330 variants), a versioned ClinVar snapshot matched by **allele** instead of rsID, and region-sliced gnomAD v4.1 for 33 panel genes — with a coverage rule so a position outside the sliced regions is an explicit failure, never a false "absent from gnomAD".
- **Provenance and reinterpretation:** every PDF report records software image, database versions and model/prompt hash; a read-only endpoint flags classifications that may be stale against the current snapshot.
- **Command-line client** (`gencodebio`): MFA sign-in, upload, pipeline stages, variants, PDF report, provenance — passwords never on the command line, session revoked on logout, public API only.
- **Quality gates:** 585 backend (also run against a real PostgreSQL in CI), 42 frontend and 26 CLI automated tests; dependency auditing, SBOM and container vulnerability scan in CI; OWASP ZAP baseline scan.
- **Roadmap:** reinterpretation screen in the UI, FASTQ→VCF workflows (Nextflow), trio/inheritance, somatic oncology, GA4GH / HL7 FHIR interoperability.

## Other projects

- **[clinical-genetics-emr](https://github.com/mailson-rodrigues/clinical-genetics-emr)** — Electronic medical record for genetic counseling with pedigree construction from structured anamnesis (FastAPI, SQLAlchemy/Alembic, 24 entities, 98 unit/integration + 15 Playwright e2e tests, audit logging, role-based access).
- **[bioinfo-clinical-training](https://github.com/mailson-rodrigues/bioinfo-clinical-training)** — Documented, hands-on clinical NGS learning path on public reference data (NA12878 / GIAB, GRCh38): QC with FastQC / fastp / MultiQC, alignment with BWA-MEM / SAMtools, with the reasoning and trade-offs behind each decision.

## Tech

**Languages:** Python · TypeScript · SQL · Linux (WSL2)
**Backend:** FastAPI · SQLAlchemy · Alembic · PostgreSQL · pytest
**Frontend:** React · Vite · Tailwind CSS · Vitest · Playwright
**Bioinformatics:** FastQC · fastp · MultiQC · BWA · SAMtools · BCFtools · GATK4 · IGV · Ensembl VEP · VCF/HGVS/ACMG-AMP
**Platform & delivery:** Docker · Docker Compose · GitHub Actions (SBOM, vulnerability scanning) · Google Cloud Run · Cloud Tasks · Secret Manager · Cloudflare
**Learning:** Python · machine learning · clinical data standards

## Background

- **15+ years** in clinical laboratory diagnostics
- **Postgraduate** — Medical Genetics & Genomics; Biosafety
- **MBA** — Data Analytics, BI and Big Data
- **Studying** — Technology program in Artificial Intelligence and Machine Learning

## Contact

Open to conversations about clinical bioinformatics, health software and genomics teams. Reach me on [LinkedIn](https://linkedin.com/in/mailson-rodrigues).

<sub>Showcase repositories are source-available under noncommercial terms — see each LICENSE.</sub>
