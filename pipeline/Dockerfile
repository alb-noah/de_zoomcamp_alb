FROM python:3.13.11
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/
WORKDIR /CODE
ENV PATH="/CODE/.venv/bin:$PATH"
COPY pyproject.toml .python-version uv.lock ./
RUN uv sync --locked
COPY pipeline.py .
ENTRYPOINT ["uv","run","python", "pipeline.py"]