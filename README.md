# Asong Suh Jr

CS @ Texas A&M | Prev. @ Google, Sand Technologies 

I work on agentic AI and spatial intelligence: systems that build models of the physical world from limited observations, and the environments and verifiers used to train and test them.

Looking for Summer 2027 internships in SWE, Applied AI, AI/ML, or research engineering.

[LinkedIn](https://linkedin.com/in/asongsuhjr/) · [Resume]([https://tinyurl.com/AsongSuhJrResume/](https://drive.google.com/file/d/1OwA_MD_i5aA4ZWf6BAb8sa-ZQBFraLYQ/view?usp=sharing)) · [Portfolio](https://asongjr.com)

## Experience

**Sand Technologies, Research Engineer Intern** (Healthcare Science, Kigali and Cape Town)
- Migrated a 3-stage computer vision pipeline (YOLOv5 detection, 72M-param multi-scale attention transformer, verdict CNN) from TensorFlow 1.x to PyTorch, matching published benchmarks at 0.998 AUC; debugged a Grad-CAM gradient bug corrupting 40% of interpretability outputs
- Diagnosed distribution shift dropping AUC to 0.40 on unseen capture hardware across 6 datasets and 4 annotation formats; designed replay-based fine-tuning that recovered AUC to 0.93 without catastrophic forgetting
- Built and trained a second YOLOv8 detection pipeline on cloud GPUs, reaching ~100% sensitivity and 0.97 specificity in held-out evaluation
- Shipped 12 offline-first Python/FastAPI microservices for field deployment: event-sourced encrypted datastore (AES-SIV), on-device Whisper speech-to-text, idempotent delivery, Ed25519-signed model distribution, SHA-256 weight verification

**Google, SWE Intern** (Apigee Observability)
- Built 12 ML anomaly detection systems on API data
- Designed low-latency inference pipelines
- Improved failure-mode coverage by 80%

## Research & applied research

**[se3env](https://github.com/asoncode/se3env)** · RL environment for SE(3) geometric reasoning
- Procedurally generates six task families (visibility, depth order, loop-closure residuals, and more) from camera poses and landmarks, with a verifier whose ground truth is closed-form
- Ships six deliberately leaky verifiers to measure reward hacking; false-accept rates range from 24.8% to 100% against a strict verifier at 0%
- Precision filter drops instances whose answer flips under 3-decimal rounding; seven distribution-shift configs; 260 tests; GRPO training script via TRL
- GPT-4o calibration: 53.4% overall on 1,440 instances, near chance on the loop-closure families

**[Invisible Machine](https://github.com/asoncode/InvisibleMachine)** · Learning hidden mechanisms by probing them
- Agents push on an opaque simulated mechanical system (MuJoCo), keep a weighted set of hypotheses about its hidden spring network, and predict the effect of future actions
- Benchmark of 37 topologies and 560 stiffness assignments with topology-level splits; compares Bayesian grammar search, a learned RNN proposal model, a direct response predictor, and linear system identification
- Frozen study of 144 episodes with zero failures. The learned proposals did not show a reliable advantage (bootstrap CI includes zero), and linear identification had the lowest error using 32x fewer forward steps
- Includes an 11-page technical paper and a React lab for manual and agent-driven probing

**[OrfaLens](https://github.com/asoncode/OrfaLens)** · Monocular 3D mapping (Orfa.ai)
- Builds persistent, object-aware 3D maps from a single RGB video stream
- ORB visual odometry, MiDaS depth with temporal scale stabilization, keyframe-anchored point-cloud fusion
- YOLOv8/RT-DETR detection with motion-plus-appearance 3D tracking
- Relocalization against stored keyframes, loop closure with pose-graph optimization, `.ply` export

**[SafetAI](https://www.linkedin.com/in/asongsuhjr/details/projects/)** · Active shooter detection for weapon-free campuses and properties (2022 to present)
- Real-time audio CNN (TensorFlow) that classifies gunshots and estimates their distance, trained on 13,973 audio files: over 93% gunshot accuracy, about 89% on distance
- YOLOv5 + ByteTrack detector for open-carried firearms and the person holding them, trained on 16,322 images: over 93% accuracy
- ESRGAN super-resolution on surveillance footage to improve detection input quality and forensic review
- 97.7% reduction in police response time to an active shooting with SafetAI in the loop
- Congressional App Challenge winner (TX-8), U.S. House Commendation, 2x SCI://TECH Robotics & Intelligent Machines 1st place, HCU Cyber Impact Award, Dilorio Foundation Senior Engineering 1st place, 2x Repsol Student Innovation Award

## Projects

**[FPL AI Command Center](https://github.com/asoncode/FPL-Assistant)** · Fantasy Premier League decision engine
- Pulls live public FPL data and projects expected points per player over a 1 to 8 gameweek horizon from xG/xA, minutes, fixture difficulty, set-piece duty, and head-to-head history
- Solves transfers as a mixed-integer program (SciPy MILP) under every FPL rule: budget at the user's real selling prices, 3-per-club cap, free transfers, and -4 hits
- Exact starting-XI selection by enumerating all legal formations, plus captain, bench order, and Safe/Balanced/Aggressive risk profiles
- Conservative chip advisor that compares against an unlimited-transfer rebuild before recommending Wildcard or Free Hit; React + TypeScript frontend, FastAPI backend, Docker

**[Health Bulletin System](https://github.com/asoncode/Neonatal_Dashboard)** · Automated quarterly health bulletins
- Ingests DHIS2-style facility data (clinical neonatal, workforce, governance, operations) into PostgreSQL, validates it, and computes indicators from a single metrics layer
- Generates a Streamlit dashboard, a PDF bulletin, and an Excel workbook from the same numbers, targeting a Ministry of Health process that took about 40 hours a month by hand
- LLM narrative layer receives only computed metric packages, never raw data; facility scoring, watchlists, anomaly detection, and a nowcasting prototype

**[LipTr](https://github.com/asoncode/Lip-Reader)** · Audio-free lip reading
- Detects faces, crops and aligns the mouth, and runs a pretrained conformer VSR model (auto_avsr) to transcribe video with no audio
- An LLM pass reconstructs plausible sentences from the raw transcript

**[Question Creator](https://github.com/asoncode/QuestionCreator)** · Adaptive CS practice generator
- Turns pasted notes, docs, or code into coding, debugging, trace-output, and test-design questions with hints and answer keys
- Local Python runner checks expected vs. actual output; zero package dependencies

**Also built:** a quant trading system with autonomous execution and risk agents and volatility-based portfolio allocation.

## Tech

Python, C++, TypeScript, SQL  
PyTorch, NumPy, SciPy, OpenCV, MuJoCo, TRL  
FastAPI, PostgreSQL, React, Docker  
Computer vision, SLAM, RL environments, optimization, ML systems

## Recognitions

- NSBE 25 Under 25
- Congressional Commendation from US House
- Congressional App Challenge Winner
- Y Combinator AI Startup School & Summer Conference Invitee
- TAMU Research Week Top 3 in CS
