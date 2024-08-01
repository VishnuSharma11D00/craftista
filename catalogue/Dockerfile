FROM python:latest as builder

WORKDIR /build

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . . 

FROM python:3.12-slim as final

WORKDIR /py-app

COPY --from=builder /build /py-app

EXPOSE 5000

CMD ["gunicorn", "app:app", "--bind", "0.0.0.0:5000"]
