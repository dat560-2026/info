# DAT560 Class Project: Multimodal Retrieval-Augmented Generation (mRAG) on MMDocIR  
  
## 1) Project Title  
**Design and Evaluation of Multimodal Retrieval-Augmented Generation (mRAG) Pipelines**  
  
---  
  
## 2) Project Context and Motivation  
Modern information systems increasingly require reasoning over **multimodal documents** that combine text and images. Traditional retrieval pipelines are often text-centric and fail to fully exploit such heterogeneous signals.  
  
This project focuses on building a **Multimodal Retrieval-Augmented Generation (mRAG)** system using a subset of the MMDocIR evaluation dataset.  
  
You will:  
1. Implement a **retrieval pipeline** over multimodal documents    
2. Explore **query processing and retrieval methods**    
3. Design an **agentic or non-agentic RAG architecture**    
4. Conduct **systematic experimental evaluation** of design choices    
  
The emphasis is on **retrieval quality, system design trade-offs, and rigorous evaluation**, not just generation performance.  
  
---  
  
## 3) Data Source and Policy (Required)  
  
You will work with a **subset of the MMDocIR Evaluation Dataset**, containing:  
- Multimodal documents (pdf documents and extracted images)  
- Queries and associated relevant answers

Download the collection [**here**].(https://liveuis-my.sharepoint.com/:u:/g/personal/2929893_uis_no/IQCG7XfAqDZqT4Hd2JrKDIRJAa-n2cG50y7Be0uqz3vYy2Y?e=Omxibl)

More details about the full collection here: https://mmdocrag.github.io/MMDocIR/

### Data usage rules  
- Use the provided dataset split as-is  as respect the usage of each set (i.e. do not train or fine-tune on the test set)
- Do not modify ground-truth relevance labels  
- Ensure fair comparisons across all system variants  
  
---  
  
## 4) Core Deliverables  
  
Each group must submit:  
  
1. **Baseline RAG system** (required)    
2. **Enhanced mRAG system(s)** (required)    
3. **Agentic mRAG system(s)** (required)
4. A final report with experimental analysis    
5. Reproducible code and run instructions      
  
---  
  
## 5) Task Definition  
  
### Primary task  

Prepare data for retrieval:
1. Pre-process the documents and mine texts from the pdfs
2. Index the multimodal data (texts and images)  to be able to run efficient retrieval

Run the retrieval using given queries:  
1. Retrieve relevant content from multimodal documents  using created index(es)
2. Use retrieved evidence to **generate an answer**  
3. Evaluate the generated answers
  
### System scope  
Your system must include:  
- A **preprocessing component** (e.g. chunking, indexing)
- A **retrieval component** 
- A **generation component** (RAG-style answer synthesis)  
  
---  
  
## 6) Required System 1: Baseline RAG Pipeline  
  
Implement a **baseline RAG pipeline** as follows:  
  
1) Mine text from the document content (e.g. using any pdf processing library)
2) Encode document content (use text at minimum)  
3) Store embeddings in a vector database (e.g., FAISS, Weaviate)  
4) Transform the query into an embedding 
5) Run basic retrieval and return top-k documents
6) Use retrieved context to generate answers (simple prompting is sufficient)  
7) Evaluate the pipeline (retrieval and generation)
  
### Baseline requirements  
- Clear preprocessing pipeline
- Clear indexing strategy  
- Defined embedding model  
- Clear retrieval pipeline  
- Report evaluation metrics
  
---  
  
## 7) Required System 2: Advanced mRAG System  
   
### Goal  
Design an **enhanced multimodal RAG system** and compare it against the baseline.  

### Required advanced elements

#### 1. Query processing
  
Implement at least **one advanced query processing technique**:  
  
- Query rewriting / paraphrasing    
- Query expansion    
- Query decomposition (multi-step retrieval)   

#### 2. Chunking strategy

Implement at least one chunking strategy (e.g. hierarchical chunking, semantic chunking) and apply it on text documents

#### 3. Multimodal retrieval
  
You must compare text based retrieval with at least one multimodal retrieval approach (use e.g. cross-modal matching).
Multimodal retrieval should incorporate **visual signals beyond extracted text** (e.g., image embeddings or cross-modal models).

#### 4. Prompting strategies for answer generation

You must experiment with at least three prompting strategies (e.g. role prompting, chain-of-thoughts, ensemble prompting, few-shot prompting, etc.)

## 8) Required System 3: Agentic mRAG System 

### Goal  
Explore an **agent-based RAG pipeline** with **at least three agents** and compare it against the baseline.  Agents must involve **LLM-based decision-making or control flow**, not just modular functions.
  
Example agent roles:  
- Query rewriting agent    
- Retrieval agent    
- Answer generation agent    
  
You must:  
- Implement an **agentic pipeline**  
- Compare it with **non-agentic baseline**  
  
You may use:  
- LangChain    
- LlamaIndex    
- or similar frameworks

As generation model, you can use the ```qwen3-vl:8b model``` available at [UiS Ollama cluster](https://ollama.ux.uis.no/).

## 9) Evaluation Metrics (Required)  
  
### Core metrics  

Report the following metrics on test for retrieved documents:
- Precision@k for k = 1, 3, 5   
- Recall@k for k = 1, 3, 5

Report the following metrics on test for generated answers:
- Exact match
- F1 / token overlap
- Semantic similarity metric (e.g. LLM-based evaluation measure measuring Answer Relevancy)

You might use any additional evaluation measures.

---  
  
## 10) Resource Constraints

Teams may use university GPUs, or their own compute resources.
GPU resources are **shared across groups**, so systems must be efficient.  
Fine-tuning is not required to finish the project (though teams might use that if they prefer to) and GPU requirements should be small.
### Required optimizations  
- Precompute embeddings    
- Index the embedding and use index while doing retrieval
- Minimize GPU usage and avoid redundant computations    
### Reporting requirements  
You must report:  
- Preprocessing time    
- Runtime per experiment    
- GPU usage (if applicable)    
  
---  
  
## 11) Experimental Design Requirements  
  
You must report at least:  

- Baseline performance
- Advanced mRAG System performance
- Ablation(s) showing what helped in the advanced mRAG System
- Agentic mRAG System performance
  
### Required comparisons  
1. Baseline vs advanced vs. agentic system    
2. With vs without query processing    
3. With and without chunking
4. Text-only vs multimodal retrieval    
5. Prompting strategy    
  
---  
  
### Reproducibility checklist  
- Fixed random seeds (if applicable)    
- Prompt templates versioned in code or config    
- Deterministic evaluation scripts    
- Documented pipeline steps    
  
---  
  
## 12) Analysis and Discussion (Required)  
  
You must provide **clear experimental insights**, including:  
  
- When multimodal retrieval helps (or fails)    
- Impact of preprocessing, retrieval and generation techniques    
- Trade-offs in agentic vs non-agentic systems    
- Efficiency vs effectiveness    
  
Support claims with:  
- Quantitative results    
- Concrete examples    

You are expected to explain **why** your prompt/model design improved results (or failed to), supported by error analysis.
  
---  
  
## 13) Project Timeline  
  
### Weeks 1-2
- Dataset exploration    
- Baseline implementation    
- Evaluation setup    
### Weeks 3–4  
-  Multimodal retrieval implementation    
- Advanced pipeline implementation
- Agentic pipeline development    
- Experimental comparisons      
### Final Week (Week 17)  
- Presentation and final evaluation    
  
---  
  
## 14) Submission Package  
  
1. **Code repository** with:  
	- data processing scripts
	- baseline code
	- code for the advanced modules
	- prompt templates/configs
	- evaluation scripts
  
2. **Final report (8–12 pages)** including:  
   - problem framing and related methods
   - baseline approach
   - advanced approaches
   - experimental setup and metrics
   - results table(s)
   - ablations
   - limitations and future work  
   -
3. **Reproducibility appendix**:
- environment details
- model versions/APIs used
- hardware usage
- run commands
  
4. **Presentation (10-15 minutes)**:  
   - key findings
   - what worked and what didn’t
   - lessons learned
  
---  
  
## 15) Grading Rubric  
  
- **20%** Baseline correctness and implementation    
- **25%** Advanced multimodal system design and implementation
- **20%** Agentic pipeline design and implementation
- **20%** Experimental quality (ablations, fairness, reproducibility)   
- **15%** Report clarity + presentation quality    
  
---  
  
## 16) Practical Notes  
  
- Keep API costs in mind: cache model outputs and reuse intermediate artifacts.
- Build robust parsing for LLM outputs (JSON schema recommended).
- Add guardrails for malformed responses and retry logic.
- Track every experiment in a log table (prompt version, model, seed, metrics).
  
---  
  
## 17) Minimum Success Criteria  
  
To pass, your project must include:  
  
1. A working **baseline RAG system**    
2. A working **advanced mRAG system**    
3. A working **agentic mRAG system**
4. A direct comparison showing whether and where the advanced method improves,
5. Reproducible code and clear documentation.
  
---  
  
This project reflects real-world challenges in **multimodal retrieval and RAG system design**, emphasizing both engineering and scientific evaluation.
