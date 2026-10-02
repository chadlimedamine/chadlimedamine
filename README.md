<div align="center">

# Hi, I'm Mohamed 👋

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&pause=1400&color=2F81F7&center=true&vCenter=true&width=720&lines=Backend+engineer+%C2%B7+Node.js+%C2%B7+NestJS+%C2%B7+TypeScript;I+turn+messy+real-world+input+into+systems+you+can+trust;PhD+in+AI+%C2%B7+I+taught+machines+to+read+Arabic+handwriting" alt="Backend engineer · Node.js · NestJS · TypeScript" />

[![LinkedIn](https://img.shields.io/badge/LinkedIn-chadlimedamine-0A66C2?style=flat-square)](https://linkedin.com/in/chadlimedamine)
[![Email](https://img.shields.io/badge/Email-mohamed.chadli.dev%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:mohamed.chadli.dev@gmail.com)

</div>

I build backends where *"it mostly works"* isn't good enough: healthcare billing, legally binding e-signatures, payments with KYC checks. If a system moves money or legal documents, I want an audit trail, a metric on every critical path, and a test that pins down how it behaves today.

I also like **messy input**: Arabic handwriting, farmers' Facebook posts, green screens with bad lighting. My favourite work is turning that kind of input into a system people can rely on.

```ts
const mohamed = {
  role:       "Backend Engineer · Node.js / NestJS / TypeScript",
  motto:      "Measure first. Fix second. Measure again.",
  phd:        "AI / computer vision: Arabic handwriting recognition (2025)",
  taught:     "Python, C and web dev to university students, for 4 years",
  speaks:     ["العربية", "English", "Français", "Deutsch (A1, jeden Tag ein bisschen besser)"],
  offline:    "🚴 cycling: regional award winner, amateur category",
  askMeAbout: ["EDIFACT, healthcare's favourite 1980s file format", "the heap spike that ate 12 GB", "teaching a CNN to read Arabic handwriting"],
} as const;
```

---

## 🚀 Featured projects

### 🌾 [AgroVendors API](https://github.com/chadlimedamine/agrovendors)

Farmers in Algeria sell their harvest through Facebook group posts. The posts are unstructured Arabic text, impossible to search, with the seller's phone number buried somewhere inside. **AgroVendors turns them into a real marketplace backend** with seller accounts, offers, images and permissions.

```text
request ─▶ JwtGuard ─▶ PermissionsGuard ─▶ ProfilingInterceptor ─▶ ValidationPipe
        ─▶ Controller ─▶ Service ─▶ Prisma ─▶ PostgreSQL
        ╰─▶ global exception filters ─▶ safe, uniform JSON errors
```

- **Refresh-token rotation with revocation.** Access and refresh tokens are signed with separate secrets. Refresh tokens are stored only as bcrypt hashes, each refresh invalidates the previous token, and logout revokes it for good.
- **Permission-based RBAC.** A custom `@Permissions()` decorator and guard read permissions straight from the JWT claims, so a check costs no database query. Every permission grant records who gave it and when.
- **Uploads checked by content, not by file extension.** Magic-byte validation, file-count and file-size limits, UUID file names, and images streamed back as `StreamableFile`.
- **Failures are visible.** Two global exception filters return safe, uniform errors. A profiling interceptor logs the duration of every request across three Winston log streams.
- **Privacy-safe seed data.** The repo ships 295 synthetic Arabic posts in the same format as scraped Facebook posts, so the import pipeline runs end to end without exposing a single real person. Every name, phone number and link is made up.
- **Posts become seller accounts.** A streaming CSV import matches sellers by phone number and creates a password-less account for each new one. Signing up with one of those numbers returns `422` instead of creating a duplicate seller.

`18 endpoints` · `7 modules` · `6 models` · `16 migrations` · `13 merged PRs` · `Swagger / OpenAPI`

**Stack:** NestJS · TypeScript · Prisma · PostgreSQL · Passport / JWT · bcrypt · Winston · Docker Compose

---

### 🛒 [ecommerce-promo](https://github.com/chadlimedamine/ecommerce-promo)

A cart and checkout API where promo codes stack, minimum-spend rules hold, and the price on an order never changes after checkout.

```text
cart        headphones 6000 + mouse 2000           = 8000
WELCOME      −500    no minimum                    ✓ applied
SPEND50     −1000    minimum spend 5000            ✓ applied
BIGSPENDER  −3000    minimum spend 10000           ✗ skipped
                                           total   = 6500
```

- **Money is an integer.** All prices are stored as integers, so floating-point rounding can never creep into a total.
- **Deterministic discounts.** The result does not depend on the order in which codes were added. Minimum spend is checked against the subtotal before discounts.
- **An audit trail for every discount.** Two junction tables separate the promotions a customer *requested* from the ones the order *honoured*.
- **Totals are frozen at checkout.** Checkout copies the cart into a separate Order. Composite keys block duplicate promotions, and a unique constraint allows only one order per cart.
- **No mass assignment.** A global `ValidationPipe` with `whitelist` and `forbidNonWhitelisted` rejects any field the API does not expect.

`9 models` · `9 endpoints` · `4 migrations` · `7 merged PRs` · `5 days from scaffold to working checkout`

**Stack:** NestJS · TypeScript · Prisma · PostgreSQL · class-validator

---

### 🎬 [Background-Changer](https://github.com/chadlimedamine/Background-Changer)

Green-screen replacement for images and video, using classical computer vision and **no ML models**. Yes, it puts Jean-Claude Van Damme on a New York street.

- **Robust keying.** It thresholds the Hue channel in HSV instead of RGB, so shadows and highlights on the green screen don't break the mask.
- **Real video.** It processes video frame by frame, with a still image or another video as the new background, keeps the audio in sync, and renders a 2×2 before/after grid.
- **Written to teach.** Four progressive notebooks take you from a basic NumPy mask to video-on-video compositing.

**Stack:** Python · OpenCV · NumPy · MoviePy · Jupyter

---

## 🏗️ In production

Client names and internals stay private. This is the kind of work I do:

- **Built observability from zero:** Prometheus metrics and Grafana dashboards for API latency, database queries, scheduled jobs and heap usage.
- **Used that data to halve median API latency** across a production platform and cut worst-case latency by **74%**.
- **Tracked down recurring Node.js heap spikes** in production containers with heap diagnostics.
- **Shipped EDI billing (EDIFACT):** invoice generation, corrections, re-submission, receipt reconciliation and a complete audit trail.
- **Shipped legally binding e-signatures over national eID,** with resumable signing sessions and webhook capture of the signed document.
- **Integrated payments and KYC,** built PostgreSQL full-text search without an Elasticsearch dependency, and moved slow work onto Redis-backed Bull queues.

## 🧭 How I work

- **Measure before optimizing.** I start with metrics, query plans and heap profiles, fix what the data shows, then measure again in production.
- **Keep the request path short.** Slow work goes onto a queue. A user should never wait for a background job.
- **Make failures loud.** Global exception capture, metrics on every critical path, and an audit trail for anything that moves money or legal documents.
- **Refactor behind tests.** Before I change old code, I pin down its current behaviour with characterization tests.

## 🛠️ Toolbox

<p align="center">
  <img src="https://skillicons.dev/icons?i=ts,nodejs,nestjs,postgres,redis,mongodb,prisma,docker,gitlab,jest,prometheus,grafana,py,tensorflow,opencv,dotnet&perline=8" alt="TypeScript, Node.js, NestJS, PostgreSQL, Redis, MongoDB, Prisma, Docker, GitLab, Jest, Prometheus, Grafana, Python, TensorFlow, OpenCV, .NET" />
</p>

| | |
|---|---|
| **Backend** | Node.js, NestJS, TypeScript, REST APIs, NestJS microservices, JWT / Passport, RBAC, webhooks |
| **Data** | PostgreSQL (query plans, indexing, full-text search), TypeORM, Prisma, MongoDB, Redis caching |
| **Async** | Bull queues on Redis, cron scheduling |
| **Observability** | Prometheus, Grafana, Winston, Node.js heap diagnostics, query profiling |
| **Delivery** | Docker, GitLab CI/CD, AWS S3, Jest (end-to-end and characterization tests) |
| **Integrations** | EDI (EDIFACT), national eID e-signatures, payments and KYC, OpenAI, speech-to-text |
| **Also** | Python, TensorFlow / Keras, OpenCV, C# / .NET (EF Core, Blazor), SQL |

## 🎓 The PhD: teaching machines to read Arabic handwriting

Arabic is cursive, its letters change shape depending on their neighbours, and real handwriting doesn't come with clean word boundaries. For my PhD in AI (computer vision, 2025), I built **CRNN models (CNN + Bi-LSTM, TensorFlow/Keras)** that read handwritten words without segmenting them first. I also built a **Moving Least Squares augmentation** that warps real handwriting into realistic new training samples.

The research took me to the Universidad de Castilla-La Mancha in Spain as an Erasmus+ research fellow, and to Hamad Bin Khalifa University in Qatar as a remote research assistant.

- [*Data Augmentation for Offline Arabic Handwritten Text Recognition Using Moving Least Squares*](https://doi.org/10.18280/ria.380101), Revue d'Intelligence Artificielle (IIETA), 2024
- *Offline Arabic Handwritten Text Recognition for Unsegmented Words Using Convolutional Recurrent Neural Network*, Springer Nature, 2022

---

<div align="center">

**Building something where the backend has to be right? I'd love to hear about it.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Let's_connect-0A66C2?style=for-the-badge)](https://linkedin.com/in/chadlimedamine)
[![Email](https://img.shields.io/badge/Email-Say_hello-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:mohamed.chadli.dev@gmail.com)

</div>
