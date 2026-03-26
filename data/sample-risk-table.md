
| Security Risk Item # | Threats | Controls |
| --- | --- | --- |
| #1 | Replay attack due to weak nonce implementation | Nonces must be generated using a cryptographically secure random generator.  Nonce must be unique per transaction request. Enforce nonce TTL: 5-15 minutes maximum. |
| #2 | Nonce storage compromise | Disable public access for Redis cache. Use private endpoint / VNet integration for Redis. Restrict access via NSG rules. Enforce system to system authentication using Azure AD. |
| #3 | Insecure transmission of nonce | Nonce must be transmitted over HTTPS only (using TLS 1.2).  Nonce must be passed in request headers or request body. |
| #4 | Insecure or inappropriate auditing and logging | The system must log nonce generation and nonce validation failures, replay attempts, duplicate request attempts, etc.  Transfer audit logs to SIEM monitoring. |