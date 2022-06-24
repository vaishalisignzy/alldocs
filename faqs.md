---
description: >-
  We recommend people to go through these FAQs as the majority of our clients
  frequently ask these questions.
---

# FAQ's

**Q1. How secure is Deep face Auth?**\
\
Signzy does not store the face image of the user. Signzy converts the face image into a hash signature which is a 512\*32 bits string. Signzy uses this signature for user enrollment, authentication & search from a database. Every hash signature is unique to the user. Users can always get this signature data deleted by getting in touch with Signzy or with Signzy Partner Businesses.\
\
The encryption mechanism used for data ins transit & data at rest - TLS1.2 & AES256 respective. \
\
**Q2. Does signzy provide both cloud & on-premise support for Deep face Auth?**\
****\
****Yes, Signzy provides both cloud & on-premise support for Deep face auth.\
\
**Q3. Does Deep-face Auth recognize twins during 1:1 auth or 1:N search?**\
****\
****Face Auth works by extracting the facial characteristics of a person and match with another facial feature to identify a match. Identical twins have the same DNA and have the same facial attributes which make it impossible for any facial recognition to recognize the difference between twins.\
****\
**Q4. What is the infrastructure required and how would it scale as my users increase?**\
****\
****We recommend two instances of Tesla T4 15GB 4x Large at 1 QPS load for less than 10k users. If you have more than 10k users, upgrade to Server V 100 8 Core 32 GB.\
****\
**Q5. Does Signzy provide mobile SDK for integration?**\
****\
****Yes, Signzy provides SDK for both IOS & Android for Deep face Auth.\
****\
**Q6. What is the recommended threshold to set during a 1:N search?**\
****\
****We recommend keeping a search threshold of 0.35 as we have seen highly optimized \
results at this threshold.\
****\
**Q7. Does Signzy also provide support for spoofing done by fraudsters?**\
****\
****Yes, Signzy also provides Liveness on-demand with Deep-face Auth which can detect any spoofing attempt made by any fraudsters. **Reach out to the sales team for activation for the same.**\
****\
**Q8. What is the false positive rate of the solution?**\
****\
****We did an internal benchmarking on 15k faces and achieved 0 false-positive scenarios at 0.7 and a higher threshold\
****\
**Q9. Does it work across all age groups, races, color & gender?**\
****\
****Yes, We provide an age, color, and gender agnostic solution.\
****\
**Q10. Is your solution recognized by any agency for certification?** \
****\
****We are in the process of getting our patent-pending face auth tech certified by NIST. \
****\
**Q11. Do Signzy services also run on a CPU instead of a GPU?**\
****\
****Yes, our current Deep face Auth can also be deployed on a CPU machine. To receive specs recommendation, reach out to your sales personnel.\
****\
**Q12. Can Deep-face Auth be integrated with a Hybrid Application via Webview Implementation?**\
****\
****Yes, Our solution can also be integrated via web-view as we provide enrollment & authentication frontend in both IOS and Android. Refer to the section for "Browser support" for understanding which browser we support.\
****\
**Q13. What format and size of images/video it supports?**\
****\
****Video format - MP4\
Image format - JPEG/JPG, PNG, TIFF/TIF & PDF\
Maximum image size support - 7 MB\
****
