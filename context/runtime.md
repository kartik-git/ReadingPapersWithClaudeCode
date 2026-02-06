# Runtime & Environment Contract

## Execution Environment

Assume:
- Google Colab CPU
- Python 3.10
- No GPU
- No external credentials
- No private network access

## Allowed Libraries

Prefer:
- Python standard library
- numpy
- random
- math
- matplotlib

Avoid:
- Large ML frameworks unless absolutely necessary
- Cutting-edge Python features

## Reproducibility Rules

- All randomness must be seeded
- All data must be generated inside the notebook
- Notebook must run top-to-bottom without edits

## Dependency Handling

If installing packages:
- Use pip
- Keep installs minimal
- First cell must confirm imports succeed