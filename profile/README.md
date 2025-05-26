# 🚫 SpamGuard AI

**Advanced Spam Detection powered by Homomorphic Encryption.**

SpamGuard AI leverages state-of-the-art **homomorphic encryption** to analyze user inputs and detect spam — all while preserving data privacy.  
It combines machine learning with encrypted computation, ensuring that sensitive information remains secure throughout the detection process.

🔐 **Key Features**
- Privacy-preserving spam classification using encrypted vectors and weights
- Seamless integration of preprocessing, vectorization, encryption, and prediction
- Designed for secure environments where data confidentiality is critical

---
## 🔐 Security Architecture

SpamGuard AI is built with **privacy by design** in mind. It utilizes **Homomorphic Encryption** to ensure that sensitive user data is never exposed in plaintext—even during processing.

- The **Secret Key** is stored **only on the client-side**.  
  The server **never has access** to the secret key, ensuring complete data confidentiality.
- All feature vectors and model weights are encrypted on the client-side using the secret key before transmission.
- Encrypted data is serialized using **Base64 encoding** to allow safe transmission over standard HTTP channels.
- Upon receipt, the server decodes the Base64 string and performs computations **directly on the encrypted data (Ciphertext)**.
- The encrypted results are sent back to the client, where decryption and final interpretation are performed locally.

> ✅ This design ensures that at no point is the raw user input or prediction result exposed to the server.
---

<img width="1262" alt="image" src="https://github.com/user-attachments/assets/353baa63-b0ce-4e36-940d-bbe7a53338c1" />

<img width="1142" alt="image" src="https://github.com/user-attachments/assets/861986c2-ca49-4186-b860-84853473ff65" />
