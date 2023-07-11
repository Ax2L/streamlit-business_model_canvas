# 📝 Streamlit - Business Model Canvas

[![GitHub][github_badge]][github_link] [![PyPI][pypi_badge]][pypi_link] 

## Installation

```sh
pip install business_model_canvas
```

## Getting started

```python
import streamlit as st

from streamlit_business_model_canvas import st_bmc

# Spawn a new MBC editor
# Re-generate your JSON data
data = {
    "visual": {
        "company_name": "Apple"
    },
    "key_partners": {
        "cards": [
            { "id":"1", "text": "Manufacturing Partners (mostly chinese)" },
            { "id":"2", "text": "Cellphone Carriers" }
        ]
    },
    "key_activities": {
        "cards": [
            { "id":"1", "text": "New Product Development" },
            { "id":"2", "text": "Marketing" }
        ]
    },
    "key_resources": {
        "cards": [
            { "id":"1", "text": "Intelectual Property (Operational Systems, digital plataform, etc)" },
            { "id":"2", "text": "Brand" }
        ]
    },
    "value_propositions": {
        "cards": [
            { "id":"1", "text": "Premium High-End Products and Experience" },
            { "id":"2", "text": "An ecosystem of interconnected services" },
            { "id":"3", "text": "Access to iPhone/iPad user base" }
        ]
    },
    "customer_relationship": {
        "cards": [
            { "id":"1", "text": "Love Brand" },
            { "id":"2", "text": "Apple Care" }
        ]
    },
    "channels": {
        "cards": [
            { "id":"1", "text": "Apple Stores" },
            { "id":"2", "text": "App Store / iTunes" }
        ]
    },
    "customer_segments": {
        "cards": [
            { "id":"1", "text": "Product Buyers" },
            { "id":"2", "text": "Service Subscribers" },
            { "id":"3", "text": "App Developers + Music & Video Producers" }
        ]
    },
    "cost_structure": {
        "cards": [
            { "id":"1", "text": "Operational Costs" },
            { "id":"2", "text": "Marketing and Branding" }
        ]
    },
    "revenue_streams": {
        "cards": [
            { "id":"1", "text": "Product Sales (High-Priced Tech)" },
            { "id":"2", "text": "Service Subscriptions (Recurring Revenue)" },
            { "id":"3", "text": "App and Media Revenues (30% cut)" }
        ]
    }
}

# binding into model
business_model_canvas(data)

# Display editor's content as you type
content
```

## Demo

[![Open in Streamlit][share_badge]][share_link] 

[![Preview][share_img]][share_link]

[share_badge]: https://static.streamlit.io/badges/streamlit_badge_black_white.svg
[share_link]: https://share.streamlit.io/okld/streamlit-gallery/main?p=ace-editor
[share_img]: https://raw.githubusercontent.com/okld/streamlit-ace/main/preview.png

[github_badge]: https://badgen.net/badge/icon/GitHub?icon=github&color=black&label
[github_link]: https://github.com/okld/streamlit-ace

[pypi_badge]: https://badgen.net/pypi/v/streamlit-ace?icon=pypi&color=black&label
[pypi_link]: https://pypi.org/project/streamlit-ace