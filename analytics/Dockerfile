FROM python:3.8-slim

WORKDIR /app 

#Install dependencies
COPY requirements.txt .

#Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

#Copy rest of the app code
COPY . .

CMD ["python", "app.py"]