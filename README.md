# chaehyun

산업 이미지 이상 탐지(Anomaly Detection)를 연구하고, 생성 모델(Generative Models)에 관심을 두고 공부하고 있습니다.

## 연구 관심사

**이상 탐지**
- 정상 이미지만으로 학습해 결함을 찾는 방법. 특히 PatchCore 계열(사전학습 CNN 특징을 메모리 뱅크에 모아 두고, 새 이미지 조각과의 최근접 이웃 거리로 이상을 판단하는 방식)
- 메모리 뱅크가 GPU 메모리보다 커질 때, 뱅크를 파티션으로 나누어 정해진 메모리 안에서 빠르게 최근접 이웃을 검색하는 방법

**딥러닝**
- 깊은 신경망이 학습되게 만든 장치의 흐름: 역전파 → 사전학습(DBN, 오토인코더) → AlexNet → VGG → 배치 정규화 → ResNet → Wide ResNet
- 논문을 원문으로 읽고 식을 직접 유도한 뒤, 작은 실험으로 주장을 확인

**생성 모델**
- 데이터 분포를 다루는 방식에 따라 이어지는 흐름: [오토인코더](https://github.com/chlee1027/paper_study/blob/main/notes/Science06_AE_Reducing_the_Dimensionality_of_Data_with_Neural_Networks.md) → [VAE](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR14_VAE_Auto_Encoding_Variational_Bayes.md) → [GAN](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS14_GAN_Generative_Adversarial_Nets.md) → [확산 모델(DDPM)](https://github.com/chlee1027/paper_study/blob/main/notes/NeurIPS20_DDPM_Denoising_Diffusion_Probabilistic_Models.md)
  (각 이름을 누르면 직접 읽고 정리한 노트로 이동합니다)
- 생성 모델을 이상 탐지에 쓰는 방법(확산 모델로 정상 이미지를 재구성해 차이를 보는 방식 등)

## 프로젝트

| 프로젝트 | 내용 | 기술 |
|---|---|---|
| [Obsidian Task Organizer](https://github.com/chlee1027/Obsidian-Task-Organizer)<br>[사이트 열기](https://organizer-eta-beryl.vercel.app) | 생각나는 대로 적은 메모를 Gemini 로 정리해 Obsidian 데일리 노트로 저장하는 웹 앱. 사람별 계정, 설정과 API 키는 서버에 저장 | JavaScript, Vercel 서버 함수, Upstash Redis, Gemini API |
| [paper_study](https://github.com/chlee1027/paper_study) | 퍼셉트론부터 DDPM 까지 논문 노트 15편과 직접 재현한 실험 5개. 노트마다 한계를 적고, 그 한계를 푼 논문을 다음에 읽는 순서로 정리 | Python, PyTorch, NumPy, Jupyter |
| PatchCore 메모리 뱅크 검색 연구<br>(비공개) | 이상 탐지 모델 PatchCore 의 메모리 뱅크를 파티션으로 나누어, 정해진 GPU 메모리 안에서 최근접 이웃 검색 시간을 줄이는 방법 연구 | Python, PyTorch, FAISS, Google Colab |

## 기술

| 분야 | 기술 |
|---|---|
| 언어 | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| 딥러닝 · 연구 | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white) |
| 실험 환경 | ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white) ![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white) |
| 웹 · 배포 | ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) ![Upstash Redis](https://img.shields.io/badge/Upstash%20Redis-047857?style=flat-square&logo=upstash&logoColor=white) |
| 도구 | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) |

## 연락처

- Email: one08988@tukorea.ac.kr

---

### About (English)

I research industrial image anomaly detection and study generative models.

- **Anomaly detection:** PatchCore-style methods that store pretrained CNN features in a memory bank and score defects by nearest-neighbor distance. My current research partitions the memory bank so that nearest-neighbor search fits within a fixed GPU memory budget.
- **Deep learning:** I read papers in the original, derive the equations myself, and check the claims with small reproduction experiments, following the line from backpropagation and pretraining to ResNet and Wide ResNet.
- **Generative models:** autoencoders, VAEs, GANs, and diffusion models (DDPM), and how generative models can be used for anomaly detection.

Contact: one08988@tukorea.ac.kr
