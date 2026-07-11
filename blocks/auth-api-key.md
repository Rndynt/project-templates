# Block: AuthN — API Key (backend-to-backend)  
  
- Zero-trust: tidak ada caller yang dipercaya bawaan, termasuk internal tool.  
- Setiap caller = "API client" yang diidentifikasi API key.  
- Key resolve ke principal: { clientId, sourceApp, scopes }.  
- Rantai: apiKey -> credentialId -> clientId -> sourceApp -> scopes -> tenant access.  
- Opsional: HMAC signing untuk request berintegritas tinggi.
