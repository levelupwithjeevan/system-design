# Style Guide

This guide defines the handbook's shared vocabulary and writing rules. Chapters must use these definitions exactly and may clarify them only with examples, not by creating competing meanings.

## Canonical Definitions

**latency**: The elapsed time between a request being initiated and the corresponding result being observed by the requester, measured for a specific operation and usually described with percentiles rather than only an average.

**throughput**: The amount of useful work completed per unit of time, measured for a defined boundary such as requests per second, messages per second, jobs per minute, or bytes per second.

**availability**: The fraction of time a system is able to perform its required function for users within the promised service boundary.

**durability**: The degree to which acknowledged data is preserved and can be recovered despite failures, corruption, operator error, or loss of infrastructure.

**reliability**: The ability of a system to continue delivering correct behavior over time under expected operating conditions and credible failures.

**consistency**: The guarantee a system provides about what value a read or operation may observe relative to prior writes or operations.

**scalability**: The ability of a system to handle increased load by adding resources or changing topology without disproportionate loss of correctness, latency, operability, or cost efficiency.

**partition**: A loss, delay, or asymmetry of communication between parts of a distributed system such that some components cannot reliably exchange messages within the time assumptions required by the design.

**quorum**: The minimum number of participants whose responses are required for an operation or decision to be accepted under a replication or coordination protocol.

## Term Use Rules

- Use the canonical terms above consistently across all chapters.
- Do not use "fast" when the intended meaning is lower latency, higher throughput, or both; name the metric.
- Do not use "highly available" without stating the failure scope or service boundary.
- Do not use "reliable" as a synonym for durable storage; reliability covers correct behavior over time.
- Do not describe a system as "consistent" without naming the consistency model or the operation boundary.
- Use "partition" for communication failure, and use "data partition" or "shard" when discussing data placement.
- Use "quorum" only when the required participant count matters to correctness or availability.

## Naming And Formatting Rules

- Chapter folders use `chapter-NN-kebab-title/`.
- Chapter files are named `README.md`.
- Chapter headings follow the exact structure in `STANDARDS.md`.
- Use sentence case for section headings except the fixed template headings.
- Use "Chapter NN - Title" in prose links when plain ASCII is preferable, and keep the exact heading form inside chapter files.
- Use product or project names only when necessary, and cite primary sources for empirical claims about named systems.
- Mark uncited rules of thumb as heuristics.
- Show capacity math directly in the text; never present an unexplained number.
- Prefer prose for reasoning, tables for comparisons, and bullets only when they improve scanability.
- Use Mermaid for diagrams. Do not embed raster images, screenshots, hand-drawn diagrams, or photos.
- Use ASCII punctuation in new files unless the required chapter template calls for the em dash in headings.
- Avoid marketing language, jokes inside technical material, and unsupported absolutes such as "always" or "never" unless the chapter is stating a safety rule.
- Write in original language from first principles. Do not copy or mirror the structure of any specific external book, course, article, or repository.

## Citation Rules

- The "Further reading" section uses primary sources only: papers, official documentation, standards, RFCs, or first-party engineering posts.
- Cite primary sources for empirical claims about named systems, protocols, or products.
- Do not cite content-farm blogs, SEO summaries, copied slide decks, or interview-prep aggregators.
- If a useful statement cannot be verified, either label it as a heuristic, narrow it to a stated assumption, or remove it.

## Diagram Rules

- Each chapter must include at least three Mermaid diagrams: one simple mental-model diagram, one intermediate mechanism diagram, and one decision tree.
- Diagrams must be fenced as Mermaid code blocks.
- Prefer `flowchart`, `sequenceDiagram`, `stateDiagram`, or `erDiagram`.
- Keep node labels short enough to be readable.
- Validate Mermaid syntax before considering a chapter complete.

