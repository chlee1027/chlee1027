# chaehyun

산업 이미지 이상 탐지(Anomaly Detection)를 연구하고, 생성 모델(Generative Models)에 관심을 두고 공부하고 있습니다.

## Research Interests

아래 흐름의 논문은 원문으로 읽고 노트로 정리했습니다. 식을 직접 유도하고, 논문의 실험을 표와 그림마다 분석(파라미터 수 세기, 표 수치 다시 계산하기, 그림 눈금 읽기)했습니다. 각 칸의 「노트 보기」를 펼치면 노트 링크가 있습니다.

**Anomaly Detection**
- 정상 이미지만으로 학습해 결함을 찾는 방법. 특히 PatchCore 계열(사전학습 CNN 특징을 메모리 뱅크에 모아 두고, 새 이미지 조각과의 최근접 이웃 거리로 이상을 판단하는 방식)
- 메모리 뱅크가 GPU 메모리보다 커질 때, 뱅크를 파티션으로 나누어 정해진 메모리 안에서 빠르게 최근접 이웃을 검색하는 방법
- 정상 이미지에서 무엇을 남겨 두는가로 갈리는 흐름: 조각 특징 저장(SPADE → 코어셋 → PatchCore) · 특징 재구성(UniAD) · 확산 모델로 이미지 복원(AnoDDPM) · 합성한 가짜 결함으로 복원 망과 분할 망을 함께 학습(DRAEM)

<details>
<summary>노트 보기</summary>

- 조각 특징 저장: [SPADE](https://github.com/chlee1027/paper_study/blob/main/notes/arXiv20_SPADE_Sub_Image_Anomaly_Detection_with_Deep_Pyramid_Correspondences.md) · [코어셋](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR18_Coreset_Active_Learning_for_Convolutional_Neural_Networks_A_Core_Set_Approach.md) · [PatchCore](https://github.com/chlee1027/paper_study/blob/main/notes/CVPR22_PatchCore_Towards_Total_Recall_in_Industrial_Anomaly_Detection.md)
- 특징 재구성: [UniAD](https://github.com/chlee1027/paper_study/blob/main/notes/NeurIPS22_UniAD_A_Unified_Model_for_Multi_class_Anomaly_Detection.md)
- 이미지 복원: [AnoDDPM](https://github.com/chlee1027/paper_study/blob/main/notes/CVPRW22_AnoDDPM_Anomaly_Detection_with_Denoising_Diffusion_Probabilistic_Models_using_Simplex_Noise.md)
- 가짜 결함 합성: [DRAEM](https://github.com/chlee1027/paper_study/blob/main/notes/ICCV21_DRAEM_A_Discriminatively_Trained_Reconstruction_Embedding_for_Surface_Anomaly_Detection.md)

</details>

**Deep Learning**
- 깊은 신경망이 학습되게 만든 장치: 역전파 → 사전학습 → AlexNet → VGG → 배치 정규화 → ResNet → 사전 활성 ResNet → Wide ResNet
- 순차 데이터에서 Transformer 까지: RNN → LSTM → GRU → seq2seq → Attention → Transformer → ViT · BERT
- 이미지 안에서 위치를 찾는 분할 · 검출: U-Net → Faster R-CNN → Mask R-CNN → YOLO

<details>
<summary>노트 보기</summary>

- 학습 장치: [역전파](https://github.com/chlee1027/paper_study/blob/main/notes/Nature86_Backprop_Learning_representations_by_back_propagating_errors.md) · [사전학습](https://github.com/chlee1027/paper_study/blob/main/notes/AISTATS10_Pretrain_Why_Does_Unsupervised_Pre_training_Help_Deep_Learning.md) · [DBN](https://github.com/chlee1027/paper_study/blob/main/notes/NC06_DBN_A_Fast_Learning_Algorithm_for_Deep_Belief_Nets.md) · [AlexNet](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS12_AlexNet_ImageNet_Classification_with_Deep_Convolutional_Neural_Networks.md) · [VGG](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR15_VGG_Very_Deep_Convolutional_Networks_for_Large_Scale_Image_Recognition.md) · [배치 정규화](https://github.com/chlee1027/paper_study/blob/main/notes/ICML15_BN_Batch_Normalization_Accelerating_Deep_Network_Training_by_Reducing_Internal_Covariate_Shift.md) · [ResNet](https://github.com/chlee1027/paper_study/blob/main/notes/CVPR16_ResNet_Deep_Residual_Learning_for_Image_Recognition.md) · [사전 활성 ResNet](https://github.com/chlee1027/paper_study/blob/main/notes/ECCV16_PreAct_Identity_Mappings_in_Deep_Residual_Networks.md) · [Wide ResNet](https://github.com/chlee1027/paper_study/blob/main/notes/BMVC16_WRN_Wide_Residual_Networks.md)
- 순차 데이터: [RNN](https://github.com/chlee1027/paper_study/blob/main/notes/CogSci90_Elman_Finding_Structure_in_Time.md) · [LSTM](https://github.com/chlee1027/paper_study/blob/main/notes/NC97_LSTM_Long_Short_Term_Memory.md) · [GRU](https://github.com/chlee1027/paper_study/blob/main/notes/EMNLP14_GRU_Learning_Phrase_Representations_using_RNN_Encoder_Decoder_for_Statistical_Machine_Translation.md) · [seq2seq](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS14_Seq2Seq_Sequence_to_Sequence_Learning_with_Neural_Networks.md) · [Attention](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR15_Attention_Neural_Machine_Translation_by_Jointly_Learning_to_Align_and_Translate.md) · [Transformer](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS17_Transformer_Attention_Is_All_You_Need.md) · [ViT](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR21_ViT_An_Image_is_Worth_16x16_Words_Transformers_for_Image_Recognition_at_Scale.md) · [BERT](https://github.com/chlee1027/paper_study/blob/main/notes/NAACL19_BERT_Pre_training_of_Deep_Bidirectional_Transformers_for_Language_Understanding.md)
- 분할 · 검출: [U-Net](https://github.com/chlee1027/paper_study/blob/main/notes/MICCAI15_UNet_Convolutional_Networks_for_Biomedical_Image_Segmentation.md) · [Faster R-CNN](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS15_FasterRCNN_Towards_Real_Time_Object_Detection_with_Region_Proposal_Networks.md) · [Mask R-CNN](https://github.com/chlee1027/paper_study/blob/main/notes/ICCV17_MaskRCNN_Mask_R_CNN.md) · [YOLO](https://github.com/chlee1027/paper_study/blob/main/notes/CVPR16_YOLO_You_Only_Look_Once_Unified_Real_Time_Object_Detection.md)

</details>

**Generative Models**
- 데이터 분포를 다루는 방식에 따라 이어지는 흐름: 오토인코더 → VAE → GAN → Wasserstein GAN → 확산 모델(DDPM) → DDIM → Score SDE → Latent Diffusion
- 생성 모델을 이상 탐지에 쓰는 방법(확산 모델로 정상 이미지를 재구성해 차이를 보는 방식 등)

<details>
<summary>노트 보기</summary>

- [오토인코더](https://github.com/chlee1027/paper_study/blob/main/notes/Science06_AE_Reducing_the_Dimensionality_of_Data_with_Neural_Networks.md) · [VAE](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR14_VAE_Auto_Encoding_Variational_Bayes.md) · [GAN](https://github.com/chlee1027/paper_study/blob/main/notes/NIPS14_GAN_Generative_Adversarial_Nets.md) · [Wasserstein GAN](https://github.com/chlee1027/paper_study/blob/main/notes/ICML17_WGAN_Wasserstein_GAN.md) · [DDPM](https://github.com/chlee1027/paper_study/blob/main/notes/NeurIPS20_DDPM_Denoising_Diffusion_Probabilistic_Models.md) · [DDIM](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR21_DDIM_Denoising_Diffusion_Implicit_Models.md) · [Score SDE](https://github.com/chlee1027/paper_study/blob/main/notes/ICLR21_ScoreSDE_Score_Based_Generative_Modeling_through_Stochastic_Differential_Equations.md) · [Latent Diffusion](https://github.com/chlee1027/paper_study/blob/main/notes/CVPR22_LDM_High_Resolution_Image_Synthesis_with_Latent_Diffusion_Models.md)

</details>

## Projects

| Project | Description | Stack |
|---|---|---|
| [Obsidian Task Organizer](https://github.com/chlee1027/Obsidian-Task-Organizer)<br>[사이트 열기](https://organizer-eta-beryl.vercel.app) | 생각나는 대로 적은 메모를 Gemini 로 정리해 Obsidian 데일리 노트로 저장하는 웹 앱. 사람별 계정, 설정과 API 키는 서버에 저장 | JavaScript, Vercel 서버 함수, Upstash Redis, Gemini API |
| [paper_study](https://github.com/chlee1027/paper_study) | 퍼셉트론부터 ViT · BERT, Latent Diffusion, PatchCore, U-Net · YOLO, DRAEM 까지 논문 노트 38편과 직접 돌린 실험 4개. 노트마다 한계를 적고, 그 한계를 푼 논문을 다음에 읽는 순서로 정리 | Python, PyTorch, NumPy, Jupyter |
| [beyond-mvtec](https://github.com/chlee1027/beyond-mvtec)<br>(진행 중) | MVTec AD 에서 고른 이상 탐지 설정의 순위가 VisA, Real-IAD 에서도 유지되는지 재는 프로젝트. PatchCore 는 원 저자 코드를 쓰고, PaDiM 과 PRO 지표는 직접 구현했다. MVTec AD 에서 원 논문 결과를 재현한 뒤, 설정 10개를 세 데이터셋 x 시드 3개로 비교했다. 순위는 같은 방향이지만(Kendall 순위 상관 0.51~0.78), MVTec AD 1위 설정이 VisA 에서는 5위였다. 정상 학습 이미지를 50장 · 10장으로 줄여도 PatchCore 두 설정의 순서는 세 데이터셋 모두 그대로였고, 10장일 때 이미지 AUROC 하락은 MVTec AD 5.6점, VisA 6.9점, Real-IAD 8.7점이었다 | Python, PyTorch, FAISS, Google Colab |
| AI+X 공공 웹사이트 불법광고 탐지 도구<br>(팀 공모전, 비공개) | 공공기관 웹사이트에 숨겨 심은 불법 광고(화면 밖에 둔 링크, 보이지 않는 글자, 자모를 쪼갠 글 등)를 찾는 도구. 브라우저로 페이지를 띄워 요소를 모으고, 글 판정 모델과 숨김 기법 규칙으로 찾은 뒤, 애매한 것만 LLM 에 다시 묻는다. Windows 실행 파일로 묶어 제출 | Python, Playwright, scikit-learn, Claude API, PyInstaller |
| 졸업작품: Fitness AI 운동 추천 앱<br>(비공개) | 목표·경험·부상·보유 장비로 운동 후보를 거른 뒤, 운동 기록(완료 여부, 체감 강도, 통증)을 보상으로 삼는 밴딧(epsilon-greedy)으로 다음 운동을 고르는 앱. Gemini 로 AI 코치 대화와 운동 가이드 제공 | Python, FastAPI, PostgreSQL, React Native(Expo), Gemini API |
| PatchCore 메모리 뱅크 검색 연구<br>(비공개) | 이상 탐지 모델 PatchCore 의 메모리 뱅크를 파티션으로 나누어, 정해진 GPU 메모리 안에서 최근접 이웃 검색 시간을 줄이는 방법 연구 | Python, PyTorch, FAISS, Google Colab |

## Tech Stack

| Category | Stack |
|---|---|
| Languages | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) |
| ML / DL | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![FAISS](https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white) |
| Frontend & Mobile | ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![React Native](https://img.shields.io/badge/React%20Native-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![Expo](https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white) |
| Databases | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Upstash Redis](https://img.shields.io/badge/Upstash%20Redis-047857?style=flat-square&logo=upstash&logoColor=white) |
| Notebooks & GPU | ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white) ![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white) |
| Deployment | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) ![PyInstaller](https://img.shields.io/badge/PyInstaller-1F4E79?style=flat-square) |
| AI Coding Tools | ![Claude Code](https://img.shields.io/badge/Claude%20Code-D97757?style=flat-square&logo=claude&logoColor=white) ![Codex](https://img.shields.io/badge/Codex-000000?style=flat-square) ![Antigravity](https://img.shields.io/badge/Antigravity-4285F4?style=flat-square) |
| Dev Tools | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) |

---

Contact: one08988@tukorea.ac.kr
