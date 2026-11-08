![image](https://github.com/khalidbelhadj/htbx/assets/38633386/1283f4a0-20dc-4a0b-bde9-7f63ab06a5f8)


# NoteVec — Semantic Note Sharing & Knowledge Discovery Platform

### Smarter Notes. Faster Search. Collaborative Learning.

**NoteVec** is a collaborative, web-based knowledge management platform designed to help university students organize, share, search, and explore academic resources efficiently.

By combining **semantic vector search, interactive knowledge graphs, document management, and collaborative discussions**, NoteVec transforms scattered academic materials into an accessible and searchable learning environment.

The platform is built with modern web technologies, including Next.js, Tailwind CSS, shadcn/ui, D3.js, MongoDB, and AWS S3.

---

## Project Overview

University students frequently rely on multiple learning resources to understand complex subjects, including lecture slides, textbooks, handwritten notes, previous assignments, research papers, and materials shared by classmates.

Although these resources are valuable, managing them becomes increasingly difficult as the amount of information grows.

Students often face challenges such as:

- Searching through hundreds of lecture notes and PDF documents.
- Finding specific topics across multiple sources.
- Managing duplicate or poorly organized study materials.
- Discovering relationships between different academic concepts.
- Sharing useful resources with classmates.
- Collaborating on academic content outside traditional learning management systems.

**NoteVec addresses these challenges by creating a centralized academic knowledge base where students can contribute resources and discover relevant information through intelligent search and interactive visualization.**

The platform is designed around a simple principle:

**The more useful knowledge students contribute, the easier it becomes for everyone to discover and understand information.**

---

## Key Features

### 1. Collaborative Note Sharing

NoteVec simplifies academic document sharing through an intuitive upload interface.

Key capabilities include:

- Drag-and-drop document uploads.
- Centralized academic resource collection.
- PDF-based learning material sharing.
- Access to notes contributed by other students.
- Organized document discovery.

This reduces the need to exchange files across multiple messaging platforms or manually search through large folders.

### 2. Semantic Vector Search

NoteVec incorporates vector-based search to help students find relevant academic materials.

Rather than relying exclusively on exact keyword matching, semantic search aims to retrieve documents based on contextual similarity.

For example, a student searching for:

> How does a compiler convert source code into machine instructions?

Could discover relevant materials covering lexical analysis, syntax analysis, intermediate code generation, and compiler architecture, even when the documents use different wording.

**Benefits include:**

- Context-aware document discovery.
- Reduced manual searching.
- Faster access to relevant notes.
- Improved retrieval across large academic collections.

### 3. Interactive Knowledge Graph

NoteVec provides a visual way to explore relationships within a knowledge base.

The visualization uses **D3.js** to represent information as an interactive graph.

This approach helps users:

- Explore connected academic resources.
- Discover related topics.
- Understand relationships between documents.
- Navigate information visually.
- Identify connections that may be difficult to recognize through traditional file lists.

### 4. Collaborative Discussions

Students can communicate and exchange feedback through discussions associated with shared notes.

Capabilities include:

- Commenting on academic resources.
- Providing feedback on uploaded materials.
- Discussing difficult concepts.
- Sharing clarifications with classmates.
- Encouraging peer-supported learning.

### 5. Accessible User Interface

The frontend emphasizes usability and simple navigation.

Interface technologies include:

- Next.js for application development.
- Tailwind CSS for styling.
- shadcn/ui for reusable interface components.
- D3.js for interactive knowledge visualization.

The goal is to make the platform accessible to students regardless of their technical experience.

---

## Technology Stack

| Layer | Technology | Purpose |
|---|---|---|
| Frontend | Next.js, React | Application interface |
| Styling | Tailwind CSS | Responsive interface styling |
| UI Components | shadcn/ui | Reusable UI components |
| Visualization | D3.js | Interactive knowledge graphs |
| Database | MongoDB | Document metadata storage |
| File Storage | AWS S3 | PDF document storage |
| Backend | Serverless Functions | Backend processing |
| Document Processing | Thumbnail Generation | Document previews |
| Search | Vector-Based Retrieval | Semantic note discovery |

---

## System Architecture

```text
                    UNIVERSITY STUDENTS
                            |
                            v
                 +----------------------+
                 |     NOTEVEC WEB APP  |
                 |   Next.js + React    |
                 | Tailwind + shadcn/ui |
                 +----------+-----------+
                            |
             +--------------+--------------+
             |              |              |
             v              v              v
     +---------------+ +------------+ +--------------+
     | DOCUMENT      | | SEMANTIC   | | KNOWLEDGE    |
     | MANAGEMENT    | | SEARCH     | | GRAPH        |
     |               | |            | |              |
     | Upload/Share  | | Vector     | | D3.js        |
     | PDFs          | | Retrieval  | | Visualization|
     +-------+-------+ +------------+ +--------------+
             |
             v
     +-----------------------+
     | SERVERLESS FUNCTIONS  |
     | Document Processing   |
     | Thumbnail Generation  |
     +-----------+-----------+
                 |
          +------+------+
          |             |
          v             v
   +-------------+ +-------------+
   |  MongoDB    | |   AWS S3    |
   | Metadata    | | PDF Storage |
   +-------------+ +-------------+
```

This architecture separates frontend presentation, document management, storage, search, and visualization responsibilities.

---

## How NoteVec Works

### Step 1 — Upload Study Materials

Students upload lecture notes, PDFs, or other supported academic resources through the document-sharing interface.

### Step 2 — Store Document Information

The application uses AWS S3 for PDF storage and MongoDB for document metadata.

Serverless functions support document-processing operations such as preview thumbnail generation.

### Step 3 — Search for Relevant Notes

Students submit search queries to find related academic resources.

Vector-based retrieval supports discovering materials through semantic similarity.

### Step 4 — Explore the Knowledge Graph

Users can navigate the interactive D3.js visualization to discover relationships between resources.

### Step 5 — Collaborate with Classmates

Students can provide feedback and discuss shared content through note-related conversations.

---

## Example Use Case

Consider a BS Computer Science student preparing for a Compiler Construction examination.

The student has access to multiple sources covering:

- Compiler phases.
- Lexical analysis.
- Syntax analysis.
- Abstract syntax trees.
- Symbol tables.
- Intermediate code generation.

Instead of manually searching multiple PDF files, the student uses NoteVec to discover relevant notes and explore related concepts through its search interface and visual knowledge graph.

This illustrates how NoteVec can support faster academic resource discovery and more organized exam preparation.

---

## Engineering Highlights

### Semantic Information Retrieval

NoteVec demonstrates the use of vector-based information retrieval in an academic document management environment.

Semantic representations enable searching for conceptually related resources beyond simple filename or keyword matching.

### Interactive Data Visualization

D3.js provides the foundation for graph-based visualization.

The implementation combines React's component architecture with D3.js visualization behavior, requiring careful handling of data structures and rendering responsibilities.

### Cloud-Based File Management

The system separates PDF binary storage from document metadata.

- AWS S3 stores the uploaded files.
- MongoDB manages document metadata.
- Serverless processing supports document-related operations.

This separation is intended to improve maintainability and support future scaling.

### Modular Frontend Design

Next.js, Tailwind CSS, and shadcn/ui provide a component-based foundation for interface development.

### Serverless Architecture

Serverless functions reduce the need for manually managed application servers for supported backend operations.

This allows document-processing tasks to be handled independently of the main user interface.

---

## Technical Challenges and Solutions

### 1. Cross-Browser PDF Handling

Different browsers can handle PDF viewing and downloads differently.

This introduces challenges involving response headers, file encoding, and browser-specific behavior.

**Engineering consideration:** Document serving must use appropriate content types, download headers, and compatible file-delivery mechanisms.

### 2. D3.js and React Integration

D3.js performs interactive DOM manipulation, while React manages component rendering through its own state and lifecycle.

Combining these technologies requires careful integration.

**Approach:** Maintain predictable graph data structures and clearly separate visualization updates from React-controlled interface behavior.

### 3. Document Storage and Retrieval

Academic platforms may contain large numbers of PDF documents.

**Approach:** Store document metadata separately from binary files to support organized storage and retrieval.

### 4. Semantic Search Precision

Searching entire documents may return broadly relevant material without identifying the most useful paragraph.

**Future improvement:** Introduce paragraph-level embeddings and finer-grained retrieval.

---

## Future Development Roadmap

### Paragraph-Level Semantic Search

Improve retrieval precision by embedding individual sections or paragraphs instead of relying solely on document-level representations.

### User Accounts and Classes

Introduce structured accounts and class-based organization for academic resources.

Potential capabilities include:

- Student profiles.
- Course-specific document collections.
- Class-level resource sharing.
- Access permissions.
- Personalized note libraries.

### Additional Opportunities

- AI-powered document summarization.
- Question answering across uploaded academic materials.
- Automatic topic extraction.
- Duplicate document detection.
- Improved knowledge graph navigation.
- Document tagging and categorization.
- Collaborative study groups.
- Bookmarking and saved searches.
- Improved accessibility.
- Search quality evaluation and performance monitoring.

These features represent potential enhancements, not verified existing functionality.

---

## Development and Attribution

### Portfolio / Repository Maintainer

**Mashiel Khan**  
BS Computer Science  
Software Development | Full-Stack Web Applications | AI-Powered Systems

GitHub: [github.com/Mashielkhan](https://github.com/Mashielkhan)

The original description refers to a student team but does not identify its members. Original authorship and specific subsequent contributions should be documented according to the repository's history.

---

## Project Vision

NoteVec explores how shared academic knowledge can become easier to discover through semantic search, collaborative interaction, and visualization.

Rather than treating every PDF as an isolated document, the platform aims to connect resources into a searchable academic knowledge base.

**NoteVec — Turning Shared Notes into Connected Knowledge.**
