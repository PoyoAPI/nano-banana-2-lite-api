# Nano Banana 2 Lite cURL Examples

Use these requests to submit a Nano Banana 2 Lite task and poll for the result.

## Text To Image

```bash
export POYO_API_KEY="YOUR_POYO_API_KEY_HERE"
export POYO_BASE_URL="https://api.poyo.ai"

curl --fail-with-body --request POST \
  --url "$POYO_BASE_URL/api/generate/submit" \
  --header "Authorization: Bearer $POYO_API_KEY" \
  --header "Content-Type: application/json" \
  --data '{
    "model": "nano-banana-2-lite",
    "input": {
      "prompt": "A clean 1K ecommerce concept image of a compact translucent desk speaker on a white studio surface, soft shadows, realistic reflections, no logo, no text",
      "size": "1:1",
      "resolution": "1K",
      "output_format": "png",
      "n": 1
    }
  }'
```

Store the returned `data.task_id`, then poll:

```bash
curl --fail-with-body --request GET \
  --url "$POYO_BASE_URL/api/generate/status/task-unified-example" \
  --header "Authorization: Bearer $POYO_API_KEY"
```

## Image Edit

```bash
curl --fail-with-body --request POST \
  --url "$POYO_BASE_URL/api/generate/submit" \
  --header "Authorization: Bearer $POYO_API_KEY" \
  --header "Content-Type: application/json" \
  --data '{
    "model": "nano-banana-2-lite-edit",
    "callback_url": "https://example.com/api/poyo/webhook",
    "input": {
      "prompt": "Preserve the source product, replace the background with a clean studio setup, keep realistic shadows, no logo, no text",
      "size": "1:1",
      "resolution": "1K",
      "output_format": "png",
      "n": 1,
      "image_urls": [
        "https://example.com/source-product.png"
      ]
    }
  }'
```

## Expected Submit Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "not_started",
    "created_time": "2026-05-23T08:00:00"
  }
}
```

## Expected Status Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "finished",
    "progress": 100,
    "files": [
      {
        "file_url": "https://storage.poyo.ai/generated/output.png",
        "file_type": "image"
      }
    ],
    "error_message": null
  }
}
```
