# Recruitment-Forecasting
# 🧠 İşe Alım Tahmin Sistemi (SVM Modelleriyle)

Bu proje, sahte verilerle oluşturulmuş bir işe alım veri seti üzerinde **SVM (Support Vector Machine)** algoritması kullanarak adayların işe alınıp alınmayacağını tahmin etmeyi amaçlamaktadır. Veri üretimi hem [Faker](https://faker.readthedocs.io/en/master/) kütüphanesiyle hem de NumPy ile yapılmıştır.

## 📂 Proje Yapısı

- `hw_faker.py`: Faker kütüphanesiyle veri üretimi, model eğitimi ve görselleştirme.
- `hw_random.py`: NumPy ile rastgele veri üretimi ve SVM model eğitimi.
- `parameter_tuning.py`: GridSearchCV ile en iyi C ve gamma parametrelerini bulma.
- `main.py`: FastAPI ile tahmin API'si.
- `models/`: Eğitilmiş modeller (`.pkl`) ve scaler'lar.
- `requirements.txt`: Gerekli kütüphaneler.
- `README.md`: Proje açıklaması.

## 🔧 Kullanılan Teknolojiler

- Python
- Scikit-learn
- Faker
- NumPy & Matplotlib
- FastAPI
- GridSearchCV
- Pickle

## 🚀 Kurulum ve Kullanım

### 1. Repo'yu klonlayın

```bash
git clone https://github.com/elifxkutlu/Recruitment-Forecasting.git
cd recruitment-forecasting 

### 2. Ortamı oluşturun ve bağımlılıkları yükleyin

python -m venv venv
source venv/bin/activate   # Windows için: venv\Scripts\activate
pip install -r requirements.txt

### 3. Modelleri oluşturun

python hw_faker.py
python hw_random.py

### 4. GridSearch ile en iyi parametreleri deneyin

python parameter_tuning.py

### 5. API'yi çalıştırın

uvicorn main:app --reload
Tarayıcıdan http://localhost:8000/docs adresine giderek Swagger arayüzüyle API'yi test edebilirsiniz.

📬 API Kullanımı
POST /predict

{
  "years_of_experience": 3,
  "technical_points": 72.5,
  "source": "faker",
  "kernel": "rbf"
}
Yanıt:

{
  "prediction": "Recruited"
}
