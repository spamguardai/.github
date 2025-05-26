# 📧 SpamGuard AI  
**Advanced Spam Detection with Homomorphic Encryption Technology**

SpamGuard AI provides secure and privacy-preserving spam classification using fully homomorphic encryption (FHE). It ensures that sensitive email contents and model parameters remain encrypted throughout the entire prediction process.

---

## 🔐 Key Features

- Privacy-preserving spam classification using encrypted vectors and weights  
- Seamless integration of preprocessing, vectorization, encryption, and prediction  
- Designed for secure environments where data confidentiality is critical  
- Client-side secret key management with no server-side exposure  
- Supports encrypted inference with logistic regression over FHE

---

## 🔄 Flow: How SpamGuard AI Works

1. **Client-side preprocessing**  
   The user’s input email text is preprocessed and converted into a numerical feature vector.

2. **Client-side encryption**  
   The input vector and model parameters (weights and intercept) are encrypted using the [piheaan](https://github.com/snucsl/piheaan) library.  
   ➤ The **secret key is kept solely on the client side**, and the server has no access to it.

3. **Encrypted data transmission**  
   The encrypted input vector and model parameters are Base64-encoded and transmitted to the server.

4. **Server-side encrypted prediction**  
   The server performs logistic regression prediction directly on the encrypted data using FHE.  
   ➤ The server never accesses any plaintext data during this computation.

5. **Encrypted result transmission**  
   The encrypted prediction result (a score) is returned to the client in Base64-encoded form.

6. **Client-side decryption & classification**  
   The client decodes and decrypts the score using the secret key and classifies the result as **spam** or **not spam**.

---

## 📁 Technologies Used

- [piheaan](https://github.com/snucsl/piheaan): FHE library for homomorphic operations
- Logistic Regression: Linear model for binary classification
- React + TypeScript: Client-side application
- Python (FastAPI): Server-side server for prediction / Client-side server for encryption & decryption

---

## ⚠️ Security Note

All computations on the server are done on encrypted data. The secret key **never leaves the client**, making this system suitable for environments where data privacy and zero-trust architectures are required.

---

## 📬 Example Use Case

```txt
1. User enters email content
2. Client encrypts features + model
3. Server computes prediction on encrypted data
4. Client decrypts the result
5. Displays: SPAM / NOT SPAM


<img width="1262" alt="image" src="https://github.com/user-attachments/assets/353baa63-b0ce-4e36-940d-bbe7a53338c1" />

<img width="1142" alt="image" src="https://github.com/user-attachments/assets/861986c2-ca49-4186-b860-84853473ff65" />
