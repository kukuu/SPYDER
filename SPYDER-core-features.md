# SPYDER 👁️⚡ Core Features:

- **Meter Functionality:**
  - Socket.io real-time data updates.
  - Meter grid display with charts
  - AI/ML historical  and inference data tracking.
  - Consumption rate indicators.
  - Affiliate link tracking
  - Calculate functionality for manual read RESULT
  - Results table display


- **AskJim Component:**
  - Inline collapsible configuration form with Settings icon
  - Three-column layout (Question Input, Sample Questions, NetZero Initiatives)
  - Material-UI components and styling
  - NetZero form with expand/collapse functionality
  - Sample questions display with optimized scrolling
  - Current supplier data display with expandable grid.
  - LLM integration with fallback responses
  - Analysis type selector (General, Real-time, Supplier Comparison)
  - Energy Certificate Trust and Green Business Certified images

- **UI Components:**
  - Navbar with Clerk authentication
  - Toast notifications
  - Responsive design
  - Ad containers with iframes
  - Brand story section
  - Sustainability Journey component
  - Product showcase

- **User Dashboard Configuration**
  - Supplier list management
  - Analysis Mode (x3)

- **NetZero Initiatives:**
  - Flight  Booking Price Alert
  - Real Estate Asset  Management.

 - **Configuration-Driven Architecture:**
  - Socket.io  asynchronous state changes stored in  environment variables (.env)
  - Database tables (suppliers, meters, etc.)
  - API endpoints for real-time updates
  - User preferences stored in state

- **Google Analytics Tracking**

SPYDER and Ask JIM both have Google Analytics ingested and enabled in Production. Tracking the following:

_Automatic Tracking:_

1. App load - Tracks when the app initializes
2. Page views - Tracks route changes using React Router
3. Socket connections - Tracks WebSocket connection status
4. Meter interactions - Treads meter selections and readings
5. AI queries - Tracks AskJIM usage and responses
6. Form submissions - Tracks Price Alert form submissions
7. Affiliate clicks - Tracks supplier switch clicks
8. Image/video loads - Tracks media loading events

**CSV Attachment to Meter Grid Reading submission**

Send Meter Readings is now configured in the Google Cloud Email Script to attach a dynamic generated CSV file from SPYDER Grid Meter readings. The file  is automatically sent to the AI engine at the backend  for processing and refining the Models to enhance data driven decisions and forecasting by the RAG pipelines and workflows.



**Useful Links:** 
1. https://www.energytariffscheck.com/
2. https://github.com/kukuu/SPYDER/blob/main/spyder-overview.md

