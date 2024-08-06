FROM ubuntu

# Set the working directory
WORKDIR /app

# Install Python and other dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-venv python3-pip

# Copy and install Python dependencies
COPY requirements.txt .
RUN python3 -m venv venv && \
    . venv/bin/activate && \
    pip install knowledge-storm && \
    pip install -r requirements.txt && \
    pip install trafilatura==1.11.0

# Copy the rest of the application code
COPY . /app

# Expose the port Streamlit uses
EXPOSE 8501

# CMD ["bash", "-c", ". venv/bin/activate && streamlit run storm.py"]
