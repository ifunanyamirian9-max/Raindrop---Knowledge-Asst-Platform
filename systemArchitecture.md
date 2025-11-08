## ⚙️ System Architecture Overview

### Frontend
- **Framework:** React.js  
- **Purpose:** Provides an interactive interface for users to organize, retrieve, and visualize saved content.  
- **Key Modules:**  
  - Smart search and filtering  
  - Tag-based organization  
  - Dynamic previews and summaries  
  - Personalized “Memory Map” dashboard (AI-powered visualization of user’s stored content)

### Backend
- **Framework:** Node.js (Express)  
- **Purpose:** Handles all business logic, API requests, and data flow between the frontend, database, and AI layer.  
- **Core Features:**  
  - RESTful APIs for CRUD operations  
  - Authentication and authorization  
  - ElasticSearch integration for semantic retrieval  
  - Connection with external APIs (Raindrop.io API, OpenAI API)

### Database
- **Database Engine:** MongoDB  
- **Purpose:** Stores all saved links, metadata, summaries, and tags.  
- **Structure:**  
  - **Users Collection:** Profile, preferences, and linked integrations  
  - **Assets Collection:** Each saved link, its metadata, and AI-generated insights  
  - **Activity Collection:** Tracks retrieval history and session-level insights

### AI & Search Layer
- **AI Layer:** OpenAI or HuggingFace embeddings model  
- **Function:** Transforms stored content into semantic vectors for context-based recall.  
- **Search Engine:** ElasticSearch for hybrid retrieval (keyword + semantic).  
- **Result Ranking:** Based on relevance, recency, and personalized weights (user’s reading or saving patterns).

### Integration Overview
1. **Raindrop.io API** – Fetches and syncs saved bookmarks.  
2. **ElasticSearch** – Enables intelligent search and recommendation.  
3. **AI Model (Embeddings)** – Powers semantic retrieval and contextual suggestions.  
4. **Frontend–Backend API** – JSON-based data exchange over HTTPS.

### Deployment & Scalability
- **Containerization:** Docker for consistent environments.  
- **Hosting:** AWS EC2 or Render.  
- **Database Hosting:** MongoDB Atlas.  
- **CI/CD Pipeline:** GitHub Actions for automated testing and deployment.  
- **Scalability Considerations:**  
  - Horizontal scaling for backend and database clusters.  
  - Caching layer (Redis) for faster repeated queries.  
  - CDN for static asset delivery.

### Security & Authentication
- **Authentication:** OAuth 2.0 with JWT.  
- **Encryption:** HTTPS + environment-protected keys.  
- **Access Control:** Role-based permissions for future team features.  
- **Data Privacy:** No content-sharing without explicit user consent.

### Future Improvements
- Add real-time collaboration (multi-user knowledge boards).  
- Introduce browser extension for direct “save + summarize.”  
- Build a recommendation engine that clusters related assets across users.
