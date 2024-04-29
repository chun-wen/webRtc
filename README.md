# Firebase + WebRTC Codelab
### Full code solution can be found under the branch: _solution_
This is the GitHub repo for the FirebaseRTC codelab. This will teach you how 
to use Firebase Cloud Firestore for signalling in a WebRTC video chat application.

The solution to this codelab can be seen in the _solution_ branch.

See http://webrtc.org for details.


# WebRTC Stun and Nat Flow  
```mermaid
sequenceDiagram
    participant User as "WebRTC User"
    participant STUN as "STUN Server"
    participant NAT as "NAT Device"

    User->>+NAT: Attempt to connect to STUN
    NAT->>+STUN: Forwarding request
    STUN-->>-NAT: Respond with User's public IP and port
    NAT-->>-User: Relay STUN's response

    Note right of User: Determines public IP and whether behind NAT
    Note right of STUN: Helps in the discovery process

    User->>+NAT: Use public IP for session initiation
    NAT->>+STUN: Confirm connectivity
    STUN-->>-NAT: Confirming connectivity
    NAT-->>-User: Session established

```
