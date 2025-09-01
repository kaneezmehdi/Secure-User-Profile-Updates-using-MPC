# Secure-User-Profile-Updates-using-MPC
This repository contains my implementation of the first assignment for the course CS670: Cryptographic Techniques for Privacy Preservation. The project focuses on secure user-profile updates in recommendation systems using additive secret sharing and secure multiparty computation (MPC).
Background
Recommendation systems represent users and items with latent vectors. The prediction for a user–item pair is computed as the inner product of the corresponding vectors. After observing a query, user profiles are updated to reflect new interactions. In this assignment, these updates must be carried out securely, without revealing the underlying vectors, by leveraging additive secret sharing across two parties.
Objective
The main objective of this project is to design and implement a protocol that securely updates user profiles. Specifically:

* Compute the inner product of secret-shared vectors in MPC.
* Compute the update factor δ = 1 − ⟨ui, vj⟩ securely.
* Perform the secure update ui ← ui + vj · δ.
* Re-share the updated profile among the parties to preserve secrecy.

Implementation Details

* The vectors U and V are additively shared between two parties, S0 and S1.
* A function for secure dot product (MPC DOTPRODUCT) was implemented.
* The shares are represented using dedicated data structures with support for initialization and randomization.
* Both parties use the same codebase, differentiated by role identifiers at runtime.
* Docker is used to containerize the environment, ensuring portability and reproducibility.

Deliverables in this repository

* Source code implementing secure user-profile updates with additive MPC.
* Dockerfile and docker-compose.yaml for running the protocol across parties.
* Scripts for generating secret shares and reconstructing values for debugging.
* README report describing:

  * Secret-sharing implementation
  * Secure inner product and update mechanism
  * Communication rounds and efficiency considerations

How to Run

1. Clone the repository and build the Docker containers using docker-compose.
2. Run the containers with appropriate command-line arguments specifying the number of users, items, features, and queries.
3. The program will print secret shares for each party and reconstructed values for verification.

Learning Outcomes
This project provided practical experience in implementing secure multiparty computation protocols. It reinforced the concepts of secret sharing, secure inner product computation, and privacy-preserving updates, which form the foundation for privacy-enhancing technologies in machine learning and recommendation systems.

---

Would you like me to also prepare a **concise project description (2–3 lines)** that you can use in your resume/portfolio alongside this longer README?
