## Adding Tests

# How to run tests

uv venv
source .venv/bin/activate
uv pip install .[dev] 

pytest --cov=.venv/lib/python3.13/site-packages/microtorch  tests/


All new compartments must include appropriate unit tests.

Tests should be added to:

    microtorch/tests/signal_models/

Please follow the structure and conventions of existing tests. Tests
should verify:

-   Correct parameter handling
-   Numerical stability
-   Expected output shape
-   Basic sanity checks of signal behaviour
