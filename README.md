# KLH-CSE-2026-27-2420030568-AegisLearnProject Overview
This project develops an AI-powered personalized learning framework that bridges the gap between static textbook corpora and adaptive student pedagogy. The system is designed to dynamically chunk academic textbooks, index them inside a simulated vector space database, retrieve relevant context using Retrieval-Augmented Generation (RAG), and synthesize study guides tailored to various cognitive levels.
When a student searches for an academic topic or takes a quiz, the query or target concept is processed and compared against the vector space using a Cosine Similarity Search Engine. The system extracts the top-K retrieved context paragraphs as grounding data. Using customizable prompt templates aligned with the six cognitive tiers of Bloom's Taxonomy (Remembering, Understanding, Applying, Analyzing, Evaluating, and Creating), the Large Language Model (Gemini 1.5 Flash) generates study guides and conceptual explanations. The student's responses are dynamically analyzed by a metrics engine to provide animated mastery gauges, diagnose subject gaps, and compile a syllabus remedial roadmap for targeted re-study.
The application features a modern, responsive single-page portal with three integrated views: the Student Portal (for customized content generation, dynamic testing, and progress tracking), the Educator Dashboard (for corpus ingestion, dataset split analytics, and indexing configuration), and the System Administrator console (for monitoring usage logs, API costs, and vector database status).
Team Members
2420030400	Masuma Fathema
2420030568	Avinash Yarukala
2420030521	Madhav Ghattamaneni
2420030467	K V S Jaswanth
Supervisor
Dr. K. Swanthana
Domain
Generative Artificial Intelligence, Retrieval-Augmented Generation (RAG), and Educational Technology (EdTech) / Natural Language Processing (NLP).
Objectives
•	Eliminate Generative Hallucinations: Ground AI responses inside verified textbook passages using RAG to suppress incorrect facts and hallucinations.
•	Personalize Cognitive Pedagogy: Adjust explanation complexity, analogies, and practice tasks dynamically based on the student's selected Bloom's tier.
•	Automate Bloom's Diagnostic Assessment: Evaluate student quiz performance across cognitive dimensions (Remembering to Creating) rather than relying on a single aggregate score.
•	Synthesize Targeted Remedial Roadmaps: Generate dynamic roadmap guides linking back to specific textbook sections for topics missed during testing.
•	Empower Custom Syllabus Ingestion: Allow teachers to load custom textbook or syllabus sheets, extract index metadata, and configure chunking parameters.
Dataset
The framework is tested on reference academic datasets parsed and prepared as structured vector search collections:
•	1. OpenStax Textbook Corpus: College-level Anatomy, Physiology, & Biology. (Official source: openstax.org)
•	2. NCERT Textbook Corpus: High School Science (Nutrition & Cellular Processes). (Official source: ncert.nic.in)
•	3. Khan Academy Algebra Corpus: Middle School Mathematics (Quadratic Equations). (Official source: khanacademy.org)
Data Input/Output mapping for the Generative AI RAG loop:
•	X / Input: Student topic query and Top-K retrieved textbook chunks (context grounding).
•	Y / Output: Bloom-aligned study guides, custom-tailored quiz questions, and cognitive mastery analytics.
System-generated metadata (such as Cosine Similarity scores, Bloom's cognitive level tags, mock chunk IDs, and remedial roadmaps) are computed by the application's runtime and simulator engines.
Technologies Used
AI and Machine Learning
•	Gemini 1.5 Flash (Generative LLM via Fetch API)
•	Retrieval-Augmented Generation (RAG)
•	Local Vector Space Embeddings Simulator (Cosine similarity matching)
•	Bloom's Taxonomy Prompt Engineering Framework
Web Application Stack
•	React.js (Single Page Application Library)
•	TypeScript (Static Casing and Type Safety)
•	Vite (Fast Bundler & Hot Reload Dev Server)
•	Tailwind CSS & Vanilla CSS (Responsive theme, Glassmorphism UI)
•	Lucide React (Vector Icon Library)
Development Tools
•	VS Code (Integrated Development Environment)
•	Git & GitHub (Version Control)
System Workflow
The diagram below outlines the flow of data through the vector search, Prompt synthesizer, LLM generation, and evaluation dashboards:
                     Student / Educator Login
                                │
                                ▼
                Select or Upload Textbook Corpus
                                │
                                ▼
                Input Search Query / Start Quiz
                                │
                                ▼
                Semantic Text Chunking & Indexing
                                │
                                ▼
                Vector Space Embeddings Simulator
                                │
                                ▼
             Cosine Similarity Search (Top-K Retrieval)
                                │
                                ▼
            Pedagogical Routing & Bloom's Filter Engine
                                │
                                ▼
             Prompt Synthesizer (Context + Bloom Prompt)
                                │
                                ▼
             Gemini API (Personalized Notes / Quiz Gen)
                                │
                                ▼
                      Interactive Interfaces
             ┌───────────────────┼───────────────────┐
             ▼                   ▼                   ▼
          Student             Educator             Admin
         Dashboard           Dashboard           Analytics
             │                   │                   │
             └───────────────────┼───────────────────┘
                                 ▼
                     Dynamic Student Evaluation
                                 │
                                 ▼
             Bloom's Mastery Gauges & Remedial Roadmap
                                 │
                                 ▼
                                END

System Modules
Student Portal (Student Module)
Students can use the portal to:
•	Authenticate and select an active profile.
•	Query academic topics and extract grounded textbook context.
•	Generate personalized study guides across the 6 Bloom's levels (Remembering, Understanding, Applying, Analyzing, Evaluating, Creating).
•	Start dynamic, interactive quizzes targeting the active corpus.
•	View real-time evaluation feedback on options selected and read instant explanation blocks.
•	Access the Performance Dashboard to monitor SVG accuracy gauges, progress bars for Bloom's dimensions, and review tailored syllabus remedial roadmaps.
Educator Portal (Educator Module)
Educators can use the dashboard to:
•	Upload custom syllabus text or textbook collections in CSV/JSON format.
•	Track textbook corpus metrics (paragraph counts, grade distributions, and reading ease metrics).
•	Inspect indexed chunks and test cosine similarity vector matching in the embedding simulator.
Administrator Module
Administrators can use the console to:
•	Monitor global usage analytics (active users, total queries, and dataset volumes).
•	Track Gemini API usage metrics (response times, prompt length, and token load).
•	Manage corpus databases and reset the local storage simulator index.
Pedagogical Routing & Bloom's Filter Engine
The Pedagogical Routing Engine maps retrieved raw textbook text onto specific instructional prompts to achieve structured learning outcomes.
Example routing configuration:
Topic Query = Cellular Respiration
Cognitive Demand = "Understanding" (Concept Analogy)
       ↓
Retrieves Top-K Paragraphs from NCERT Biology Dataset
       ↓
Loads Bloom's Prompt Template (Structures analogy, simplifies terminology)
       ↓
Gemini 1.5 Flash Generates Analogy-based Study Notes and Grounded Explanation
       ↓
Saves performance and history to local storage state

Model & System Evaluation
The framework and the generated content are continuously monitored using four metrics:
•	1. Faithfulness Score: Determining if the generated explanations are strictly supported by the retrieved textbook paragraphs to completely block hallucinations.
•	2. Answer Relevance: Measuring how well the generated study guide answers the student's initial query.
•	3. Retrieval Precision & Recall: Evaluating semantic cosine similarity thresholds to ensure the vector engine retrieves highly relevant contexts.
•	4. Student Mastery Score: Dynamic assessment of correctness across the six Bloom's tiers to identify exact cognitive levels that need support.
Project Structure
generative-ai-personalized-learning/
├── public/                     # Static client files
├── src/
│   ├── assets/                 # SVGs and UI graphics
│   ├── components/
│   │   ├── StudentLogin.tsx    # Portal authentication & profiles
│   │   ├── XaiSandbox.tsx      # Bloom's Study Notes Generator
│   │   ├── QuizView.tsx        # Interactive Quiz Stepper & scoring
│   │   ├── PerformanceView.tsx # Student Analytics & Mastery Gauges
│   │   ├── RagAnalyzer.tsx     # Vector Search Simulator & RAG uploader
│   │   ├── AnalyticsView.tsx   # Corpus analytics & metadata split
│   │   └── Navbar.tsx          # Navigation controls
│   ├── data/
│   │   ├── promptTemplates.ts  # Bloom's Taxonomy prompt index
│   │   ├── textbooks.ts        # Preloaded OpenStax, NCERT corpora
│   │   └── quizQuestions.ts    # Fallback local quiz database
│   ├── utils/
│   │   ├── api.ts              # Gemini API integration service
│   │   └── simulator.ts        # Embedding vector cosine similarity
│   ├── App.tsx                 # App layout router
│   ├── index.css               # Theme globals and glassmorphism styling
│   └── main.tsx                # App bootstrap mounting
├── package.json                # Dependencies and project scripts
├── vite.config.ts              # Bundler configuration settings
└── README.md                   # Running instructions

Setup and Execution
1. Clone the Repository
git clone https://github.com/2420030211-hub/KLH-CSE-2026-27-2420030211-PersonalizedLearning
cd KLH-CSE-2026-27-2420030211-PersonalizedLearning

2. Install Node.js Dependencies
npm install

3. Run the Development Server
npm run dev

4. Open the Web Portal
Open your browser to the local address shown in the terminal. Usually:
http://localhost:5173/

5. Configure Gemini API Key
Click the API Key setup button in the sidebar and enter your Gemini API Key. This will unlock live, RAG-grounded custom notes and quiz generation.
Current Phase Status
Current Phase: Phase 4 – Application Interface Development and RAG Model Integration
Completed
•	Project Selection and Title definition.
•	Initial problem statement, objectives, and abstract writeup.
•	Selection of textbook datasets (OpenStax Anatomy, NCERT Biology, Khan Academy Algebra).
•	Development of local vector space embeddings simulator and chunking algorithms.
•	Custom prompt engineering catalog aligned with the six levels of Bloom's Taxonomy.
•	Integration of Gemini API connector using TypeScript fetch.
•	Design of Student Login, navbar, and core page router.
In Progress
•	Dynamic RAG Analyzer search box sandbox.
•	Refining Bloom study notes prompt templates.
•	Building the interactive Quiz stepper component with real-time feedback.
•	Implementing SVG performance gauges, Bloom taxonomy metrics progress bars, and syllabus remedial roadmap.
Upcoming
•	Educator portal uploader and metadata validator.
•	Comprehensive validation testing (faithfulness, retrieval recall).
•	Final document assembly, code packaging, and production deployment.
Project Plan
Phase 1 – Literature Survey and Conceptual Design
•	Research 10 educational NLP papers on personalized learning, RAG, and Bloom's Taxonomy.
•	Identify current limitations in LLM education systems (hallucinations, rigidity).
•	Establish project framework architecture and select initial reference textbooks.
Phase 2 – Dataset Parsing and Chunking
•	Obtain textbooks and segment them into overlapping sliding paragraphs.
•	Extract subjects, grade levels, and readability scores for corpus metadata.
Phase 3 – Vector Space Simulator Development
•	Write chunk vector mapping generator.
•	Develop cosine similarity matching function in TypeScript.
Phase 4 – UI Construction and Layout
•	Build clean dark glassmorphism responsive layouts.
•	Construct Student Login, navigation bars, and collection selectors.
Phase 5 – RAG Prompt and API Integration
•	Ground prompts in retrieved context blocks.
•	Verify token parameters and model response JSON structures.
Phase 6 – Student Quiz and Evaluation Engine
•	Implement interactive quiz stepper with real-time feedback.
•	Develop performance tracker classifying answers by Bloom's level.
Phase 7 – Performance Dashboard and Ingestor
•	Create SVG accuracy gauges and Bloom mastery bars.
•	Create dynamic Remedial Roadmap list generator for incorrect answers.
•	Develop educator custom corpus uploader component.
Phase 8 – Testing, Documentation and Host Deployment
•	Evaluate response relevance, correctness, and retrieval precision.
•	Complete user testing feedback cycle.
•	Write final report and host project on public platform.
Project Outcome
The finalized project delivers a state-of-the-art Generative AI Personalized Learning Framework that converts static textbooks into interactive, personalized tutors. Key outcomes include:
•	1. RAG-Grounded Context: Grounds all responses in textbook paragraphs using semantic search to completely suppress AI hallucinations.
•	2. Cognitive Customization: Maps generated summaries, analogies, and quizzes across all six levels of Bloom's Taxonomy, accommodating the cognitive need of each student.
•	3. Multi-Dimensional Performance Analysis: Evaluates student quiz performance to profile precise strengths and weaknesses in different cognitive styles.
•	4. Targeted Remedial Assistance: Automatically maps wrong answers to textbook chapters and generates a step-by-step syllabus study roadmap.
•	5. Flexible Syllabus Expansion: Allows educators to vectorize any customized corpus sheet dynamically, facilitating scalable personal learning paths for any syllabus.
By packaging this framework into a fast, responsive interface, the system achieves a significant reduction in student learning gaps, improves engagement, and sets a transparent benchmark for AI-driven academic support.
