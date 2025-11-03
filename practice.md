flowchart LR
  A[1. Client Request] --> B[2. API Gateway]
  B --> C[3. Validate Request]
  C -->|[valid]| D[3.a Call Service-A]
  C -->|[invalid.schema]| E[3.E1 Return 400 with errorCode=SCHEMA_INVALID]
  C -->|[invalid.auth]| F[3.E2 Call AuthService -> Return 401]
  D --> G[4. Aggregate & Respond]
  E --> G
  F --> G
  G --> H[5. Client Receives Response]
