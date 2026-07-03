# Production Notes

Use this checklist before putting nano-banana-2-lite into a user-facing product.

## API Key Safety

- Store `POYO_API_KEY` in server-side environment variables.
- Never send the key to browser code or mobile clients.
- Do not print `Authorization` headers in logs.

## Task State

- Persist `data.task_id` immediately after submit.
- Treat `finished` and `failed` as terminal states.
- Store the selected model, user ID, request time, and final status together.

## Polling And Webhooks

- Poll with a moderate interval while testing.
- Add a timeout in your application.
- Use `callback_url` webhooks for production queues.
- Make duplicate callbacks safe.

## Files

- Download generated files before they expire.
- Copy production assets to your own storage.
- Avoid logging private media URLs when they contain customer content.
