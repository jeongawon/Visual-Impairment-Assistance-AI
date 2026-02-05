# Visual-Impairment-Assistance-AI
👁️ 시각장애인 보행 자율성 향상을 위한 AI 보조 시스템 (AI Walking Assistant)
이 프로젝트는 시각장애인의 안전하고 독립적인 보행을 돕기 위해 개발된 실시간 위험 감지 및 음성 안내 시스템입니다.
카메라 영상을 통해 전방의 객체를 탐지하고, 거리를 측정하며, 상황을 분석하여 사용자에게 음성(TTS)으로 안내합니다.
📌 주요 기능 (Key Features)
1. 실시간 객체 탐지 (Object Detection):
    ◦ YOLOv5를 사용하여 사람, 차량(자동차, 버스, 트럭), 자전거, 신호등 등을 실시간으로 인식합니다.
2. 거리 추정 (Depth Estimation):
    ◦ MiDaS 모델을 통해 단일 카메라(Webcam)만으로 객체와의 상대적 거리를 측정하여 "매우 가까움/주의/안전" 단계를 판별합니다.
3. 동적 이동 방향 분석 (Movement Analysis):
    ◦ 이전 프레임과의 좌표 변화(Δx)를 분석하여 차량이나 사람이 다가오는지, 멀어지는지, 좌우로 이동하는지를 판단합니다.
4. 신호등 색상 인식 (Traffic Light Recognition):
    ◦ YOLO가 탐지한 신호등 영역의 RGB 평균값을 분석하는 알고리즘(Rule-based)을 적용하여 빨간불/초록불을 정확히 구분합니다.
5. 음성 안내 및 제어 (TTS & STT):
    ◦ gTTS를 통해 "전방에 차량이 접근 중입니다"와 같은 경고 메시지를 출력합니다.
    ◦ 사용자의 음성 명령("종료해", "상황 알려줘")으로 시스템을 제어할 수 있습니다.
🛠️ 기술 스택 (Tech Stack)
• Language: Python 3.8+
• Computer Vision: OpenCV, PyTorch
• AI Models:
    ◦ YOLOv5 (Object Detection)
    ◦ MiDaS (Monocular Depth Estimation)
• Audio Interface:
    ◦ gTTS (Text-to-Speech)
    ◦ SpeechRecognition (Speech-to-Text)
    ◦ Pyaudio, Playsound
