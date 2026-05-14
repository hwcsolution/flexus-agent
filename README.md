# Flexus Agent Skills Collection

[简体中文 README](README_CN.md)

## 📖 Introduction

This repository contains reusable workflow skills based on **Dify** orchestration and export. Each skill is an independent workflow file that can be directly imported into the Dify platform.

**Features**:
- 🚀 **Ready to use**: Download and import directly into Dify
- 📂 **Clear categorization**: Organized by application scenarios for easy searching
- 🔧 **Continuous updates**: Regular additions and optimizations
- 📝 **Comprehensive documentation**: Detailed descriptions for each skill

## Installation

> To Be Developed

## ✨ Features

| Feature | Description |
|:----|:----|
| 🎯 **Ready to Use** | Download and import directly into Dify, no additional configuration required |
| 📂 **Clear Categorization** | Organized into 7 major categories including AI Video, Education, Business Research, Content Creation |
| 🔄 **Continuous Updates** | Monthly regular additions and optimizations of workflows |
| 📝 **Comprehensive Documentation** | Each skill includes detailed input/output descriptions and usage examples |
| 🧪 **Production Verified** | All workflows have been tested and verified in production environments |
| 🌍 **Multi-scenario Coverage** | Covers 10+ application scenarios including education, business, creation, analysis |
| 🔐 **Secure & Compliant** | No user data collection, supports private deployment |
| ⚡ **High Performance** | Optimized workflow design with average response time < 3 seconds |

## 📊 Skill Overview

### Statistics by Category

| Category | Icon | Count | Main Scenarios |
|:----|:----|:----|:----|
| AI Video Generation | 🎬 | 1 | Text-to-Video |
| Content Creation | 📝 | 3 | Marketing Copy, Translation, Sensitive Word Review |
| Education | 👨‍🏫 | 11 | Teacher Assistant, Reading Recommendations, Question Generation, Error Analysis |
| Business Research | 💼 | 8 | Policy Inquiry, Opinion Monitoring, Industry Reports |
| Productivity | ⚡ | 5 | Meeting Minutes, Resume Screening, Intelligent Query |
| Image Analysis | 🖼️ | 2 | Image Analysis, Water Meter Recognition |

## 📊 Detailed Skill List

### 🎬 AI Video Generation

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-video-gen` | Input keywords, achieve "text-to-video" in minutes | Keywords, style, duration, resolution | Video file download link | v1.0.0 |

**Use Cases**: Short video production, marketing material generation, educational training videos, product demonstrations

### 📝 Content Creation

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-intelligent-marketing-assistant` | Intelligent marketing copy generation with multi-platform adaptation | Product info, target platform, audience profile, marketing goals | Marketing copy (multiple versions), title suggestions, hashtags | v1.0.0 |
| `dify-intelligent-translation-assistant` | AI intelligent translation supporting multi-language with style preservation | Source text, source language, target language, style requirements | Translation results, terminology consistency check | v1.0.0 |
| `dify-sensitive-word-review` | Accurately identify sensitive words in images | Image URL, sensitive word library configuration | Review results, sensitive word location marking, risk level | v1.0.0 |

**Use Cases**:
- Marketing Copy: E-commerce product pages, social media promotion, email marketing, ad campaigns
- Intelligent Translation: Cross-border communication, document localization, real-time translation
- Sensitive Word Review: Content safety review, compliance checking, image filtering


### 👨‍🏫 Education

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-intelligent-teacher-assistant` | Generate course outlines and knowledge graphs in minutes | Subject, grade, knowledge points, class schedule | Course outline, knowledge graph, learning objectives, recommended resources | v1.0.0 |
| `dify-reading-recommendations` | Personalized reading book recommendations | Grade, reading level, interest tags, reading goals, read books | Recommended book list (with reasons and reading order suggestions) | v1.0.0 |
| `dify-reading-guide` | Generate heuristic guiding questions | Article excerpt, grade, teaching objectives | Guiding questions, thought questions, discussion topics | v1.0.0 |
| `dify-identification-of-rhetorical-writing-techniques` | Identify rhetorical devices and writing techniques | Full article, analysis depth | Technique list, paragraph positioning, function analysis, examples | v1.0.0 |
| `dify-reading-comprehension-questions` | Targeted question generation | Article, grade, weak knowledge points, question count, question type preference | Question list (with answers, explanations, and question design rationale) | v1.0.0 |
| `dify-article-structure-analysis` | Article structure analysis | Full article | Mind map (text format), paragraph division, main idea, writing flow | v1.0.0 |
| `dify-word-verify` | Automatic typo annotation generation | Document file (.doc/.docx/.txt) | Typo list, correct spelling, correction suggestions, context location | v1.0.0 |
| `dify-question-recommend` | Similar question recommendations | Question text, subject, difficulty range, quantity | Similar question list, knowledge point analysis, difficulty rating | v1.0.0 |
| `dify-question-analysis` | Problem-solving method analysis | Question text, subject | Solution steps, method summary, common errors, tips | v1.0.0 |
| `dify-question-attri` | Error question attribution analysis | Error question text, student answer, student historical errors | Error cause classification, weak knowledge points, personalized improvement suggestions | v1.0.0 |
| `dify-quality-edu` | Education marketing quality inspection | Marketing content (text/image/video link) | Compliance score, risk point marking, improvement suggestions | v1.0.0 |

**Use Cases**:
- Teacher lesson preparation and course design
- Personalized student learning
- Parent tutoring for children
- Educational institution content quality control


### 💼 Business Research

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-subsidy-inquiry` | Enterprise subsidy policy inquiry | Company name, Unified Social Credit Code | Company EID, applicable subsidy list, application requirements, deadlines | v1.0.0 |
| `dify-national-policy-research-and-comparison` | Multi-country policy comparison analysis | Country list, policy area, time range | Policy difference report, trend chart, key clause comparison | v1.0.0 |
| `dify-public-opinion-monitoring` | Social media opinion monitoring | Brand keywords, monitoring platforms, time range | Opinion analysis report, sentiment trend chart, risk alerts, hot topics | v1.0.0 |
| `dify-technology-trend-insights` | Technology trend insights | Technology field, time range, geographic scope | Technology evolution roadmap, patent analysis report, industry impact assessment | v1.0.0 |
| `dify-academic-literature-research` | Academic literature research | Research topic, time range, literature type | Paper search results, research hotspot analysis, structured review report | v1.0.0 |
| `dify-cross-border-product-overseas-market-analysis-assistant` | Cross-border market analysis | Product information, target country, competitor information | Market analysis report, consumer insights, competitor analysis, entry strategy | v1.0.0 |
| `dify-in-depth-research-report-writing` | In-depth research report writing | Research topic, analysis dimensions, report length | Comprehensive insight report, data charts, conclusions and recommendations | v1.0.0 |
| `dify-industry-report` | Industry report generation | Industry name, geographic scope, time range | Structured industry report, market size, competitive landscape, trend forecast | v1.0.0 |

**Use Cases**:
- Corporate strategic decision-making
- Government policy research
- Investment analysis
- Market entry strategy
- Academic research


### ⚡ Productivity

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-meeting-minutes-summary` | Meeting minutes generation | Meeting recording/transcript, attendee information | Structured meeting minutes (agenda, resolutions, action items, responsible persons) | v1.0.0 |
| `dify-resume-screening-assistant` | Resume screening | Resume file (PDF/Word), job description, screening criteria | Match score, candidate ranking, screening suggestions, interview questions | v1.0.0 |
| `dify-content-difference-identification` | Content difference identification | Document A, Document B, comparison dimensions | Difference comparison report, modification list, version summary | v1.0.0 |
| `dify-intelligently-query-data` | MySQL intelligent query | Natural language question, database schema | SQL statement, query results, data visualization suggestions | v1.0.0 |
| `dify-water-identify` | Water meter identification | Water meter image | Reading, recognition confidence, anomaly detection | v1.0.0 |

**Use Cases**:
- Meeting Management: Quickly organize meeting records
- Recruitment: Resume screening, candidate evaluation
- Document Management: Version comparison, change tracking
- Data Analysis: Natural language database queries
- IoT: Smart water meter reading recognition

### 🖼️ Image Analysis

| Skill Name | Description | Input | Output | Version |
|:----|:----|:----|:----|:----|
| `dify-image-analysis` | Image analysis assistant | Image URL, analysis dimension requirements | Content description, object recognition, OCR results, scene classification, sentiment analysis | v1.0.0 |

**Use Cases**:
- Content review
- Image classification and labeling
- Optical Character Recognition (OCR)
- Visual search
- Assisting visually impaired users


> **Total 29 ready-to-use workflows**
