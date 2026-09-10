# AI Student Support Assistant – Agentic AI Project Report

> GitHub-friendly Markdown version of the project report.

## Project Overview

This project presents an end-to-end **Agentic AI application for university/college students**. The system uses **RAG (Retrieval-Augmented Generation), tools/function calling, memory, and a dual-engine approach (Gemini online + local fallback)** to provide student support.

## Report Content

## Page 1

AI Student Support Assistant – Agentic AI Project Report 
                                                                     PROJECT REPORT 
                                               PROJECT TITTLE:AI Student Support Assistant 
     1.Project Overview 
Project tittle: AI Student Support Assistant 
The AI Student Support Assistant is an end-to-end Agentic AI application tailored for university and 
college students. Its core purpose is to answer college-related questions using regulations, syllabus 
information, FAQs, and notices while also performing student-specific actions through tools. 
The project combines three central capabilities: Retrieval-Augmented Generation (RAG), agent 
tools/function calling, and memory for multi-turn conversations and student context. This allows the 
assistant to move beyond a simple question-answer chatbot and behave as a student support agent. 
Capability 
Purpose 
RAG 
Retrieves relevant university information and 
provides source citations. 
Tools 
Performs attendance, grades, ticket, exam, GPA, 
and faculty-related operations. 
Memory 
Maintains conversation context and active 
student information across turns. 
Dual Engine 
Supports Gemini online mode and a local 
autonomous fallback engine. 
 Problem Statement 
Students frequently need information about attendance rules, examinations, grading, syllabus 
requirements, campus services, notices, and academic support. Conventional information portals may 
require students to search across multiple pages or systems. 
The project addresses this problem by providing a unified conversational interface. The assistant can 
retrieve institutional information, access student records through tools, create and track support tickets, 
and remember relevant context during a conversation. 
Description 
The AI Student Support Assistant is an Agentic AI-based web application designed to help college and 
university students quickly access academic and campus-related information. The system uses 
Retrieval-Augmented Generation (RAG) to retrieve answers from regulations, syllabus, FAQs, and 
notices, while AI agent tools handle tasks such as checking attendance, viewing grades, calculating 
target GPA, checking exam schedules, finding faculty information, and raising support tickets. It also 
uses conversation and student-context memory to provide personalized multi-turn interactions.

## Page 2

AI Student Support Assistant – Agentic AI Project Report 
2.Objectives and proposed Solutions 
 Project Objectives 
• Build an end-to-end AI Student Support Assistant for university/college use. 
• Answer questions from academic regulations, syllabus, FAQs, and campus notices. 
• Implement RAG for relevant document retrieval and source citation. 
• Implement agent tools for attendance, grades, exam schedules, tickets, GPA calculations, and 
faculty lookup. 
• Maintain multi-turn conversation memory and active student context. 
• Provide a modern responsive web portal for demonstrations and practical use. 
• Support both Gemini online mode and a local fallback autonomous agent. 
• 
Provide automated and manual verification procedures for the core features. 
 
Proposed Solution 
The proposed solution is a web-based Agentic AI student portal. A student submits a natural-language 
question through the chat interface. The backend agent determines whether the request requires 
knowledge retrieval, a tool operation, or a direct response. 
1. Receive the student's natural-language request. 
2. Use conversation and student-profile memory to resolve context. 
3. Determine the required action using the ReAct orchestration layer. 
4. Retrieve relevant knowledge-base chunks when institutional information is needed. 
5. Execute an appropriate tool when student-specific or operational data is required. 
6. Observe the retrieved information or tool output. 
7. Generate a structured final response with citations and actionable guidance. 
 
 System Architecture 
The architecture is organized into a modern single-page portal UI, a FastAPI backend, an autonomous 
agent core, a RAG engine, a tool engine, a knowledge base, and a mock university database. 
Layer 
Main Components 
Frontend 
Chat arena, citations, student switcher, 
knowledge explorer, helpdesk desk. 
API Backend 
FastAPI server and HTTP/JSON APIs. 
Agent Core 
ReAct loop, LLM driver, local fallback 
reasoning engine. 
RAG Engine 
Chunking, metadata tagging, semantic indexing, 
top-k retrieval, citations. 
Tool Engine 
Attendance, grades/CGPA, tickets, exam 
schedule, target GPA, faculty search. 
Knowledge Base 
Regulations, CS syllabus, FAQs, 
circulars/notices. 
Mock University DB 
Student records, tickets, faculty directory, exam

## Page 3

AI Student Support Assistant – Agentic AI Project Report 
schedules. 
The project materials specify a ReAct sequence of Reasoning/Thought → Action → Observation → 
Final Answer. The agent therefore decides what information source or operation is needed before 
synthesizing the response. 
How the Agentic AI Solution Works 
The AI Student Support Assistant works as an intelligent agent rather than just a normal chatbot. It 
follows a ReAct (Reasoning → Action → Observation → Answer) process and combines RAG, 
tools, and memory.  
Working flow: 
1. Student asks a question 
Example: “Can I attend the exam if my attendance is 68%?”  
2. Agent understands the request 
It identifies that this is an academic regulation question.  
3. RAG retrieves information 
The system searches the knowledge base and retrieves the relevant attendance regulation.  
4. Agent takes an action 
If the question requires student-specific data, the agent calls a tool such as 
check_attendance(student_id).  
5. Agent observes the result 
It receives the retrieved document or tool output.  
6. Memory provides context 
The system remembers the active student and previous conversation, so the student does not 
have to repeatedly provide their details.  
7. Agent generates the final answer 
It combines the retrieved information/tool result and provides a clear response with source 
citations and actionable guidance.  
Simple Architecture 
Student → Web Portal → AI Agent → RAG / Tools / Memory → Result → Student 
For example: 
Student: “Check my attendance.” 
↓ 
Agent: Identifies active student 
↓ 
Tool: check_attendance(STU101)

## Page 4

AI Student Support Assistant – Agentic AI Project Report 
↓ 
Result: DSA = 68%, OS = 82% 
↓ 
AI Assistant: “Your DSA attendance is 68%, which is below the 75% requirement.” 
This is what makes it Agentic AI: the system can decide what action is needed, use the appropriate 
tool or knowledge source, observe the result, and then produce the final response, rather than 
simply generating a text an 
Key Features 
 Knowledge Base and Data Design 
The knowledge base is divided into four major document categories: 
File 
Content 
academic_regulations.md 
Attendance rules, condonation, grading scale, 
SGPA/CGPA, re-evaluation and supplementary 
exam criteria. 
computer_science_syllabus.md 
Core CS subjects, modules, prerequisites, lecture 
hours, textbooks and lab requirements. 
campus_faqs.md 
Hostel, mess, scholarships, fees, library, Wi-Fi, 
buses and placement eligibility FAQs. 
circulars_notices.md 
Exam schedules, fee deadlines, technical-event 
notices and approved holidays. 
The mock database contains student records, a persistent support-ticket store, a faculty directory, and 
examination schedules. Five demonstration student personas are included in the proposed dataset. 
Student ID 
Persona 
Branch 
Semester 
CGPA 
Attendance 
Example 
STU101 
Alex Johnson 
CS 
4 
8.4 
82% OS; 68% 
DSA 
STU102 
Priya Sharma 
IT 
6 
9.2 
94% all 
subjects 
STU103 
Marcus Vance 
CS 
2 
7.1 
76% 
STU104 
Ananya Patel 
AI & Data 
Science 
4 
8.8 
89% 
STU105 
David Kim 
Mech 
3 
6.9 
62% 
 Retrieval-Augmented Generation (RAG) Engine 
The RAG engine enables the assistant to answer institutional questions using the project's knowledge 
base instead of relying only on general language-model knowledge. 
• Documents are split using Markdown headings and natural paragraphs with overlapping windows. 
• Each chunk receives metadata including source, category, and section title. 
• The hybrid semantic engine computes similarity and retrieves the top-k relevant chunks. 
• The default retrieval size is three relevant chunks.

## Page 5

AI Student Support Assistant – Agentic AI Project Report 
• Retrieved results include citation information and a confidence percentage. 
• New .txt or .md documents can be uploaded through the UI and immediately indexed into the 
active vector store. 
Examples of RAG questions specified in the verification plan include attendance consequences, 
Database Management Systems prerequisites, and hostel curfew information. 
Agent Tools and Function Calling 
The tool engine provides structured operations for student-specific and administrative tasks. 
Tool 
Function 
check_attendance(student_id) 
Returns overall and subject attendance, shortage 
warnings, and classes needed to reach 75%. 
check_grades(student_id) 
Returns SGPA, CGPA, course grades, and 
credits earned. 
raise_support_ticket(...) 
Creates a trackable ticket and records it in 
tickets.json. 
get_ticket_status(ticket_id) 
Retrieves ticket status, timeline and staff 
remarks. 
get_exam_schedule(branch, semester) 
Returns exam dates, time slots and room 
allocations. 
calculate_target_gpa(...) 
Calculates required future SGPA for a target 
CGPA. 
search_faculty(query) 
Finds faculty cabins, emails, departments and 
consultation hours. 
Function calling is important because some questions cannot be answered correctly by document 
retrieval alone. For example, a request to check a student's current attendance requires access to 
structured student data. 
 Memory System 
The assistant includes two complementary forms of memory. Conversation-window memory retains 
recent turns, while student-profile memory stores the active student context needed for subsequent 
queries. 
• Conversation history can resolve follow-up references such as a subject mentioned in the previous 
turn. 
• Active student ID, department, semester and registered-course context can be retained. 
• Students do not need to repeatedly provide the same context in every query during a session. 
Example flow: a student asks about OS attendance, then asks how many classes are needed to reach 
75%. The agent can use the previous turn to understand that the follow-up concerns OS.

## Page 6

AI Student Support Assistant – Agentic AI Project Report 
LLM and ReAct Orchestration 
The project supports Google Gemini through the google-genai library when an API key is configured. 
It also includes a deterministic local fallback agent using semantic search and ReAct-style reasoning, 
allowing the application to be tested without an API key. 
ReAct Stage 
Description 
Thought 
Analyze the student's request and decide whether 
retrieval, a tool, or a direct response is needed. 
Action 
Execute the selected tool or RAG query. 
Observation 
Use the tool result or retrieved knowledge as 
context. 
Final Answer 
Generate a friendly, structured answer with 
source citations and actionable advice. 
This dual-engine design is intended to improve demonstration readiness because the project can 
operate in both online AI mode and local fallback mode. 
 Web Portal / User Interface 
The proposed frontend is a responsive single-page student portal with modern visual styling. The UI is 
organized around four major experiences. 
UI Area 
Features 
Chat Interface 
Message history, Markdown formatting, tables, 
code snippets, citations and quick prompts. 
Student Persona Bar 
One-click switching between pre-loaded student 
profiles. 
Knowledge Base Explorer 
Browse knowledge categories, test vector search 
and upload documents. 
Helpdesk Tickets 
View tickets, filter by status and observe newly 
created tickets. 
Presentation Mode 
Shows project progression, architecture, and 
RAG + Tools + Memory concepts. 
The interface also includes a live system-status indicator, active student badge, settings for Gemini 
configuration/model selection, source citation cards, and an expandable agent reasoning/tool-call 
indicator. 
4.Implementations and results 
 Project Structure 
The proposed project is self-contained under the ai_student_assistant directory. 
ai_student_assistant/ 
├── run.py 
├── requirements.txt 
├── .env.example 
├── README.md 
├── CAPSTONE_REPORT.md

## Page 7

AI Student Support Assistant – Agentic AI Project Report 
├── data/ 
│   ├── knowledge_base/ 
│   │   ├── academic_regulations.md 
│   │   ├── computer_science_syllabus.md 
│   │   ├── campus_faqs.md 
│   │   └── circulars_notices.md 
│   ├── students.json 
│   ├── tickets.json 
│   ├── faculty_directory.json 
│   └── exam_schedule.json 
├── backend/ 
│   ├── config.py 
│   ├── rag/ 
│   │   ├── document_processor.py 
│   │   ├── embeddings.py 
│   │   └── retriever.py 
│   ├── tools/ 
│   │   ├── student_tools.py 
│   │   ├── ticket_tools.py 
│   │   ├── academic_calculator.py 
│   │   └── registry.py 
│   ├── agent/ 
│   │   ├── memory.py 
│   │   ├── llm.py 
│   │   └── core.py 
│   ├── models/schemas.py 
│   └── main.py 
├── frontend/ 
│   ├── index.html 
│   ├── css/styles.css 
│   └── js/ 
│       ├── app.js 
│       └── components.js 
└── tests/ 
    ├── test_rag.py 
    ├── test_tools.py 
    └── test_agent.py 
 
Implementation Workflow 
 
• Prepare the project directory and install the dependencies listed in requirements.txt. 
• Configure environment settings through .env.example and optionally provide a Gemini API key. 
• Create and populate the knowledge-base documents and mock university data. 
• Implement document chunking, metadata tagging, indexing and retrieval. 
• Implement student, ticket, academic-calculator and faculty tools. 
• Implement conversation and student-profile memory. 
• Integrate the Gemini driver and local fallback reasoning engine. 
• Connect the FastAPI endpoints to the frontend.

## Page 8

AI Student Support Assistant – Agentic AI Project Report 
• Run automated tests for RAG, tools and agent memory. 
• Launch the application using python run.py and perform manual verification through the portal. 
 Technologies and Tools 
Technology / Tool 
Role in Project 
Python 
Primary backend and AI application 
development language. 
FastAPI 
Backend web framework and HTTP/JSON API 
layer. 
Google Gemini 
Online LLM engine when an API key is 
configured. 
google-genai 
Python integration for Gemini. 
RAG 
Grounded knowledge retrieval from university 
documents. 
TF-IDF / BM25-style local retrieval 
Local semantic retrieval/fallback capability 
described in the project plan. 
Pydantic 
Structured request/response and tool schemas. 
HTML / CSS / JavaScript 
Responsive student portal frontend. 
JSON / Markdown 
Mock database and knowledge-base storage 
formats. 
Pytest-style tests 
Automated verification of RAG, tools and agent 
behavior. 
 Verification and Testing 
Automated Testing 
Test 
Verification 
RAG Search Test 
Checks attendance consequence, DBMS 
prerequisites and hostel-curfew retrieval; verifies 
relevance and source attribution. 
Tools Execution Test 
Checks attendance, ticket creation/status retrieval 
and target-GPA calculation. 
Agent Integration Test 
Checks multi-turn interaction, tool-call sequence 
and memory retention. 
 Manual Verification 
• Launch the application with python run.py. 
• Verify that the FastAPI server starts at http://127.0.0.1:8000. 
• Open the web portal in a browser. 
• Switch the student persona to Alex Johnson (STU101). 
• Ask whether a student with 68% attendance can take the examination and verify the regulation 
citation. 
• Ask for semester attendance and verify the attendance tool invocation and subject-wise output. 
• Raise a DSA attendance recount ticket and verify that a ticket ID is created. 
• Open the Knowledge Base Explorer and test vector search.

## Page 9

AI Student Support Assistant – Agentic AI Project Report 
• Upload a sample notice and verify dynamic indexing. 
Expected / Achieved Results 
Based on the provided project implementation plan, the intended results are a functioning student 
support portal that can combine document retrieval, structured tool execution, and memory in a single 
conversation. The source materials define the verification procedures but do not provide actual 
execution logs or screenshots; therefore, this report treats the following as project outcomes to be 
verified during execution. 
• Relevant university information can be retrieved from the knowledge base with source attribution. 
• Attendance and grade queries can use student-specific records. 
• Support tickets can be created and tracked. 
• Exam schedules and faculty information can be retrieved through tools. 
• Target-GPA calculations can be performed through the academic calculator. 
• Multi-turn questions can reuse conversation and student context. 
• The system can be demonstrated through the student persona switcher. 
• Dynamic text/Markdown document indexing can be tested from the UI. 
 
Screenshot

## Page 10

AI Student Support Assistant – Agentic AI Project Report 
 
 
 
Conclusion and Future Scope: 
Conclusion 
The AI Student Support Assistant demonstrates how Agentic AI can be applied to a practical 
university support scenario. Instead of functioning only as a conversational chatbot, the system 
combines RAG for grounded institutional knowledge, tools for structured operations, and memory for 
contextual interaction. 
The proposed FastAPI backend, modern web portal, knowledge base, mock university database, tool 
engine, and dual-mode AI architecture provide a complete foundation for an academic capstone 
project. The verification plan further provides a clear way to evaluate retrieval, tool execution, and 
multi-turn agent behavior. 
Challenges Faced 
The project design identifies several practical implementation challenges that must be handled during 
development: 
• Maintaining accurate retrieval and source attribution from heterogeneous institutional documents. 
• Selecting the correct tool for student-specific requests. 
• Preserving context across multi-turn conversations. 
• Providing useful operation without depending entirely on an external API key. 
• Keeping structured student and ticket data synchronized with the user interface. 
• Testing both retrieval accuracy and agent/tool behavior. 
• Designing a clear interface that makes AI actions understandable during evaluation. 
The dual-engine approach and explicit automated/manual verification plan are intended to reduce the 
impact of API availability and improve testability. 
 Future Enhancements

## Page 11

AI Student Support Assistant – Agentic AI Project Report 
• Connect the mock student database to a real university/student information system. 
• Add authentication and role-based access for students, faculty and administrators. 
• Add persistent production-grade databases instead of JSON-only storage. 
• Expand the knowledge base to additional departments and institutions. 
• Add multilingual student support, including regional languages. 
• Add notifications for attendance shortage, exam dates, fee deadlines and ticket updates. 
• Add analytics dashboards for administrators and student-support teams. 
• Improve retrieval with production vector databases and stronger embedding models. 
• Add evaluation metrics for groundedness, retrieval precision and tool-call accuracy. 
• 
Deploy the application to a secure cloud environment with monitoring and access controls. 
 References 
• Project Implementation Plan – AI Student Support Assistant (Full-Fledged Project), provided 
project source material. 
• Project Template for IBM Internship – Agentic AI, provided report template. 
• FastAPI documentation and project framework references, as applicable during implementation. 
• Google Gemini / google-genai documentation, as applicable when online LLM mode is configured.

## Page 12

AI Student Support Assistant – Agentic AI Project Report

---

## GitHub Usage

This Markdown file can be uploaded directly to a GitHub repository and can also be used as context in GitHub AI tools that do not accept PDF attachments.
