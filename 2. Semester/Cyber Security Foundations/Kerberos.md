## Step by step auth
1. Principal (client) wants to authenticate
2. The principal sends a request to the KDC (Key Distribution Center) asking for a **ticket**. This request is encrypted using the hash of the principals password.
3. The KDC looks up the principals account and authenticates them using  their hashed password.
4. The KDC then sends the ticket back to the principal.
5. The principal sends the ticket to Server A to which she wants to authenticate.
6. Server A verifies the ticket and authenticates the principal.

