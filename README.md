# My Shawarma Stand

A sample ordering page built with JavaScript and two Make scenarios. Customers can choose chicken, beef or mixed shawarmas, specify quantities and hotdogs per item, and select pickup or delivery. The page displays a delivery fee of NGN 500.

## Try the page

Open index.html locally. To connect your own automation, replace YOUR_AI_PREVIEW_WEBHOOK_URL and YOUR_SAVE_ORDER_WEBHOOK_URL in a local copy. The repository contains the webpage. The Make scenarios run separately.

- **Typed preview:** Sends a form-encoded message to the AI webhook. The page expects a JSON object with an items array containing product, quantity and hotdogs_per_shawarma, plus optional customer_name, fulfilment and delivery_address. The customer reviews the filled menu before submitting.
- **Save order:** Sends the reviewed order as JSON with one request_id for the whole order. The save scenario validates items, calculates prices and checks the stored key before saving. Retrying from the page reuses the same request ID.

The preview requires a webhook response with the extracted items. A plain Accepted response cannot fill the menu. Live webhook addresses and customer records are excluded.
