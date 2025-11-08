# System Architecture for Raindrop Reimagined  

Raindrop Reimagined is a cloud-based web application designed to help users store, organize, and rediscover digital content across devices.  
It uses a retrieval-first architecture that connects the frontend, backend, and database through a clean API layer.  

## 1. Architectural Overview  

The system follows a three-tier structure:  

1. **Frontend Layer** – The user interface where all interactions happen.  
2. **Backend Layer** – The logic engine that processes data and connects with external services.  
3. **Data Layer** – The storage and retrieval layer that manages user data and search indexing.  

## 2. Frontend  

**Technology:** React.js + Redux Toolkit  
The frontend is responsible for:  
- Rendering pages such as onboarding, dashboard, and search results.  
- Managing user interactions and routing.  
- Sending API requests to the backend and displaying responses in real time.  

The interface communicates with the backend through RESTful APIs.  
It also uses local caching to improve performance and user experience.  

**Core Components:**  
- Onboarding Module  
- Ask My Archives Search  
- Rediscover Dashboard  
- Smarter Connections Panel  

## 3. Backend  

**Technology:** Node.js with Express.js Framework  

The backend handles all core logic:  
- Authenticating users through Google OAuth.  
- Processing search queries.  
- Managing CRUD operations for saved items.  
- Coordinating with Elasticsearch for fast retrieval.  

It acts as the bridge between the UI and database, ensuring smooth communication through well-defined API endpoints.  

**Main Services:**  
- Authentication Service  
- Content Management Service  
- Search Service  
- Recommendation Engine  

## 4. Database and Storage  

**Technology:** MongoDB and AWS S3  

MongoDB stores structured and semi-structured data such as user profiles, bookmarks, metadata, and tags.  
Each saved item is indexed by category, keyword, and date for efficient retrieval.  

AWS S3 is used to store files, PDFs, and images uploaded by users.  
All stored assets are encrypted and linked to the MongoDB collection through unique IDs.  

## 5. Search and Retrieval Layer  

**Technology:** Elasticsearch  

This is the core of the product.  
Elasticsearch indexes all user data to support advanced searches.  
It allows natural language queries and semantic matching.  

When a user types, “Show me the articles I saved about marketing,” Elasticsearch filters all stored content and returns relevant results in milliseconds.  

## 6. Recommendation Layer  

This layer powers Rediscover Dashboard and Smarter Connections.  
It uses a lightweight algorithm that tracks user behavior and content categories to recommend related items.  

Future versions will include OpenAI embeddings for more accurate semantic similarity detection.  

## 7. Deployment and Infrastructure  

**Hosting:**  
- Frontend: Vercel  
- Backend: Render  

Both connect to GitHub for automated CI/CD.  
Every commit triggers build and deployment pipelines using GitHub Actions.  

**Additional Services:**  
- AWS S3 for asset storage  
- Cloudflare for security and caching  
- SSL for data encryption  

## 8. Data Flow Summary  

1. User saves or uploads a resource through the UI.  
2. The frontend sends this data to the backend API.  
3. The backend stores metadata in MongoDB and the file in S3.  
4. Elasticsearch indexes the new record for fast search.  
5. When the user searches, the backend queries Elasticsearch.  
6. Relevant items are returned and displayed instantly in the UI.  

## 9. Future Enhancements  

- Add semantic vector search powered by embeddings.  
- Implement offline recall mode.  
- Support browser and mobile extensions for saving.  
- Introduce analytics dashboard for usage insights.  

## 10. Summary  

Raindrop Reimagined uses a clean, modular system that prioritizes retrieval speed, reliability, and scalability.  
Each component works independently but communicates through a simple API layer.  
The goal is to help users store and rediscover information efficiently without overwhelming complexity.  
