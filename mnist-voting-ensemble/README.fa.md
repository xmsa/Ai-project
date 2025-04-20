<!-- language: rtl -->

این یه نسخه اولیه و استاندارد هست که هم ساختار پروژه رو مشخص می‌کنه، هم مراحل اجرا، و هم تکنولوژی‌هایی که استفاده می‌کنی رو توضیح می‌ده.

# 🧠 MNIST Voting Ensemble Classifier

یک پروژه کامل برای تشخیص اعداد دست‌نویس (MNIST) با استفاده از یادگیری ماشین و یادگیری عمیق، همراه با مانیتورینگ، API، رابط کاربری، و Docker.

## 🔍 ویژگی‌ها

<div dir="rtl" align="right" lang="fa">

- آموزش چند مدل مختلف (Simple CNN, Deep CNN, CNN with BatchNorm, SVM)
- مانیتورینگ فرآیند آموزش با استفاده از **MLflow**
- انتخاب بهترین مدل‌ها و پیاده‌سازی **weighted voting ensemble**
- ساخت API با **FastAPI** برای پیش‌بینی عدد از تصویر ارسالی
- رابط کاربری ساده با **Bootstrap**
- سیستم لاگین کاربران و اعتبارسنجی توکن
- قابل اجرا به‌صورت local یا روی سرور با استفاده از **Docker**
</div>

## 🛠 تکنولوژی‌ها و ابزارها

- Python, PyTorch, Scikit-learn
- MLflow
- FastAPI
- Bootstrap
- SQLite + JWT Authentication
- Docker
- Google Colab (برای آموزش مدل‌ها)

## 📁 ساختار پروژه

```
mnist-voting-ensemble/
├── models/             # مدل‌های ذخیره‌شده
├── mlruns/             # لاگ‌های MLflow
├── notebooks/          # Notebook آموزش مدل‌ها در Colab
├── app/                # API و کدهای FastAPI
├── frontend/           # فایل‌های HTML و Bootstrap
├── Dockerfile
├── requirements.txt
└── README.md
```

## 🚀 مراحل اجرا

### 1. آموزش مدل‌ها

مدل‌ها را در Google Colab آموزش دهید. Notebook در مسیر `notebooks/train_models.ipynb` قرار دارد.

### 2. اجرای API

```bash
uvicorn app.main:app --reload
```

### 3. داکرایز کردن پروژه

```bash
docker build -t mnist-app .
docker run -p 8000:8000 mnist-app
```

### 4. استفاده از API

مستندات خودکار API در مسیر `/docs` در دسترس است:

```
http://localhost:8000/docs
```

## 📬 ارسال تصویر برای پیش‌بینی

<div dir="rtl" align="right" lang="fa">

- ابتدا کاربر login می‌کند و توکن دریافت می‌کند.
- تصویر به صورت `multipart/form-data` ارسال می‌شود.
- پاسخ شامل عدد پیش‌بینی‌شده است.

</div>

## 👤 ورود کاربران

<div dir="rtl" align="right" lang="fa">

- ثبت‌نام و ورود از طریق API یا UI
- احراز هویت با استفاده از JWT
- محدود کردن تعداد درخواست‌ها با اعتبار
</div>

## 📊 رأی‌گیری مدل‌ها

<div dir="rtl" align="right" lang="fa">

- هر مدل یک پیش‌بینی انجام می‌دهد.
- با توجه به دقت مدل، پیش‌بینی آن وزن‌دهی می‌شود.
- عدد نهایی با رأی‌گیری وزن‌دار انتخاب می‌شود.
</div>

---
