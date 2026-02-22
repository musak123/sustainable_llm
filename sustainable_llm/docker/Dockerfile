# Base image
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Copy any dependency specifications (requirements.txt or environment.yml)
# Users should fill these files with actual dependencies.
COPY ../requirements.txt ./
COPY ../environment.yml ./

# Install Python dependencies if provided
RUN if [ -f requirements.txt ]; then pip install --no-cache-dir -r requirements.txt; fi
RUN if [ -f environment.yml ]; then \
    pip install --no-cache-dir "conda" && \
    echo "# environment.yml exists but conda install not implemented in this Dockerfile"; fi

# Copy project files
COPY ../src ./src
COPY ../scripts ./scripts

# Default command if container is run without arguments
CMD ["bash"]
