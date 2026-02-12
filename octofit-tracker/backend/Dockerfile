FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

# Copy project files
COPY . /app

# Create virtual environment inside the image and install requirements
RUN python3 -m venv /opt/venv \
    && /opt/venv/bin/pip install --upgrade pip \
    && /opt/venv/bin/pip install -r requirements.txt

ENV PATH="/opt/venv/bin:$PATH"

EXPOSE 8000

# Development entrypoint: run Django dev server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
