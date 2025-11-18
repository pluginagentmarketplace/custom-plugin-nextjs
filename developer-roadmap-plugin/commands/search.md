# /search - Search Across Roadmaps

Search for specific topics, technologies, and skills across all 78 roadmaps.

## Usage

```
/search [keyword]
/search react
/search database design
/search machine learning
/search authentication
```

## Search Results Format

Results include:
- **Roadmaps**: Which roadmaps cover this topic
- **Agents**: Which agents specialize in this
- **Level**: Beginner, Intermediate, Advanced
- **Resources**: Related learning materials
- **Related Topics**: Connected concepts

## Popular Searches

### **Programming Languages**
```
/search python
/search javascript
/search java
/search go
/search rust
```

### **Web Technologies**
```
/search react
/search node.js
/search database
/search api design
/search rest
/search graphql
/search authentication
```

### **Cloud & DevOps**
```
/search kubernetes
/search docker
/search aws
/search ci/cd
/search terraform
/search monitoring
```

### **Data & AI**
```
/search machine learning
/search data pipeline
/search llm
/search prompt engineering
/search neural networks
/search big data
```

### **System Design**
```
/search caching
/search load balancing
/search microservices
/search sharding
/search database scaling
/search high availability
```

### **Security**
```
/search authentication
/search authorization
/search encryption
/search owasp
/search sql injection
/search jwt
```

## Advanced Search

### **Search by Category**
```
/search category:frontend
/search category:backend
/search category:infrastructure
/search category:data
/search category:security
```

### **Search by Level**
```
/search "react" level:beginner
/search "kubernetes" level:advanced
/search "python" level:intermediate
```

### **Search by Roadmap**
```
/search in:frontend
/search in:backend
/search in:aws
/search in:machine-learning
```

## Example Search Results

```
/search react

Results:
1. React Fundamentals
   - Roadmap: Frontend Developer, Full Stack
   - Agent: Web Development Agent
   - Level: Beginner → Intermediate
   - Topics:
     • Components and JSX
     • Hooks (useState, useEffect)
     • Props and State
     • Context API
     • Performance optimization

   Resources:
   - Official React Docs: https://react.dev
   - Course: React - The Complete Guide
   - Practice: Build Todo App

2. Advanced React Patterns
   - Roadmap: Frontend Developer (Advanced)
   - Agent: Web Development Agent
   - Level: Advanced
   - Topics:
     • Custom hooks
     • Server-Side Rendering (SSR)
     • Static Generation (SSG)
     • Code splitting
     • Error boundaries

3. React with TypeScript
   - Roadmap: Full Stack (TypeScript path)
   - Agent: Language & Fundamentals, Web Development
   - Level: Intermediate
   - Topics:
     • Type definitions for props
     • Hooks with types
     • Context typing
     • Generic components

4. React Testing
   - Roadmap: Frontend Developer (Testing path)
   - Agent: Specialized Roles (QA)
   - Level: Intermediate
   - Topics:
     • Jest configuration
     • React Testing Library
     • Unit testing components
     • Integration testing
```

## Tips for Effective Searching

1. **Use specific keywords**
   ```
   ✓ "jwt authentication"
   ✓ "postgresql indexing"
   ✗ "database stuff"
   ```

2. **Include context**
   ```
   ✓ "frontend performance optimization"
   ✓ "kubernetes networking"
   ✗ "performance"
   ```

3. **Combine searches**
   ```
   /search react
   + /search typescript
   + /search testing
   = Complete React stack
   ```

4. **Refine by level**
   ```
   /search kubernetes level:beginner
   /search "system design" level:advanced
   ```

## Search Categories

**Languages & Fundamentals**
- Programming languages
- Data structures
- Algorithms
- Design patterns

**Web Development**
- Frontend frameworks
- Backend frameworks
- Full-stack technologies
- Web APIs

**Mobile Development**
- iOS development
- Android development
- Cross-platform frameworks
- App deployment

**Data & AI**
- Machine learning
- Data engineering
- AI/LLMs
- MLOps

**Cloud & Infrastructure**
- Cloud platforms
- Containerization
- Orchestration
- Infrastructure as Code

**Databases**
- SQL databases
- NoSQL databases
- Caching
- Query optimization

**System Design**
- Architecture patterns
- Scalability
- Security
- Performance

**Specialized**
- Product management
- Technical leadership
- DevRel
- Technical writing
- Game development
- Cybersecurity

## Related Features

- **`/roadmap`** - Get full path for a roadmap
- **`/agents`** - Find which agent covers topic
- **`/assess`** - Test knowledge on found topics
- **`/learning-path`** - Build custom path from search results

## Examples

```
User: /search database design

Agent Response:
→ System Design topic covers database design patterns
→ Architecture Agent specializes in this
→ Related: SQL, NoSQL, Caching, Sharding
→ Found in: 12 roadmaps (Backend, Data Engineer, Architect)

Resources:
- System Design Interview questions
- PostgreSQL Optimization
- MongoDB Scaling Patterns

Next step: /agents architecture or /roadmap system-design
```

---

**Source**: https://roadmap.sh
