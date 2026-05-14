---
name: content-continuation
description: Continue writing lesson plans via Dify API. Use when the user needs to extend or complete a lesson plan based on the provided title, catalogue, abstract and existing content.

---

#content-continuation

Use Dify chat api to continue writing lesson plans.

##Setup

Only show setup in linux/macos enviroment, change it if under Windows. Required before API calling. If not set, ask users to provide.

### DIFY_API_HOST

```bash
mkdir -p ~/.config/dify
echo "your_dify_api_host" > ~/.config/dify/api_host
```

### DIFY_API_KEY

```bash
mkdir -p ~/.config/dify/api_key
echo "your_dify_api_key" > ~/.config/dify/api_key/{skill_name}
```

Replace {skill name} with actual name

## API Usage

```bash
DIFY_API_HOST=$(cat ~/.config/dify/api_host)
DIFY_API_KEY=$(cat ~/.config/dify/api_key/content-continuation)

curl -X GET "$DIFY_API_HOST/v1/chat-messages" \
  -H "Authorization: Bearer $DIFY_API_KEY" \
  -H "Content-Type: application/json" \
  --data-raw '{
    "inputs": {
        "mainTitle": "Lesson plan title to be continued",
        "catalogue": "Lesson plan catalogue",
        "abstract": "Lesson plan abstract (optional)",
        "content": "Current finished content of the lesson plan (optional)"
    },
    "query": "Continue writing the lesson plan according to the given title, catalogue, abstract and existing content",
    "response_mode": "blocking",
    "conversation_id": "",
    "user": "openclaw-agent"
}'
```

### Get Valid Input

Pass inputs in the request based on user messages if necessary. The valid options can get from parameters API:

```bash
curl -X GET "$DIFY_API_HOST/v1/parameters"\
--header "Authorization: Bearer $DIFY_API_KEY"
```

From the response find `user_input_form` array. Only select input from the list.

### Conversation_id

Keep it blank for the first conversation. If users ask more interactions, find the `conversation_id` from the response for following API calls.

### Response

The example response for blocking mode.

```json
{
    "event": "message",
    "task_id": "c3800678-a077-43df-a102-53f23ed20b88", 
    "id": "9da23599-e713-473b-982c-4328d4f5c78a",
    "message_id": "9da23599-e713-473b-982c-4328d4f5c78a",
    "conversation_id": "45701982-8118-4bc5-8e9b-64562b4555f2",
    "mode": "advanced-chat",
    "answer": "...",
    "metadata": {
        "annotation_reply": null,
        "retriever_resources": [],
        "usage": {
            "prompt_tokens": 919,
            "prompt_unit_price": "2",
            "prompt_price_unit": "0.000001",
            "prompt_price": "0.001838",
            "completion_tokens": 375,
            "completion_unit_price": "8",
            "completion_price_unit": "0.000001",
            "completion_price": "0.003",
            "total_tokens": 1294,
            "total_price": "0.004838",
            "currency": "RMB",
            "latency": 10.999156465753913
        }
    },
    "created_at": 1770971349
}
```

### Tips

It may take several minutes to complete the request. Wait patiently until responses come back. Only try one time even there are any errors. If errors happen, tell users error details to let them decide.



