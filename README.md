# Sensitive Content Detection in Videos

This project is a web-based system that detects sensitive content in videos and alerts users during playback. It combines machine learning with real-time video interaction, making it suitable for content moderation, parental control, or safe media consumption.

## 🔍 Project Idea

The system identifies sensitive video frames (e.g., explicit or inappropriate content) using a deep learning model. Rather than analyzing frames in real-time (which causes latency), it pre-processes videos and stores sensitive timestamps in a database. When a user plays a video, alerts are triggered just before sensitive segments appear.

## ⚙️ Tech Stack

- **Frontend**: HTML5, CSS, JavaScript (Custom Video Player & Alert Display)
- **Backend**: Python (Flask Framework)
- **Machine Learning**: PyTorch (CNN model for frame classification)
- **Video Processing**: OpenCV
- **Database**: MySQL (Video metadata + sensitive frame timestamps)

## 🧠 How It Works

1. **Video Management**: Detects all video files from a local folder and lists them in the UI.
2. **Frame Extraction**: Frames are extracted at 1-second intervals using OpenCV.
3. **Content Detection**: A CNN model (trained on tomatoes as sensitive and cats as non-sensitive) classifies each frame.
4. **Data Storage**: Sensitive frame timestamps are stored in MySQL, grouped to avoid redundant alerts.
5. **Playback Alerts**: During playback, alerts are fetched from the database and shown 2 seconds before sensitive scenes.

## ✅ Results

- **Model Accuracy**: ~96% accuracy with ~94.5% F1-score.
- **Frame Classification Time**: ~12ms per frame (fast enough for real-time use).
- **Alert Trigger Time**: <1 second during playback.
- **User Experience**: Clean UI, grouped alerts, and automatic video pausing for user control.
- **Scalability**: Supports dynamic video addition and large video libraries without performance issues.


## 📌 Datasets Used

- [Tomatoes Dataset (Sensitive)](https://www.kaggle.com/datasets/enalis/tomatoes-dataset)
- [Cats Dataset (Non-sensitive)](https://www.kaggle.com/datasets/crawford/cat-dataset)

## 🚀 Future Improvements

- Support for multiple sensitive content categories
- User authentication and personalized alert settings
- Option to skip or blur sensitive segments automatically

