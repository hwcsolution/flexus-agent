---
name: dify-article-structure-analysis
description: By using the DIY API for reading comprehension analysis, this skill helps designated grade students understand the overall structure of the article: firstly, analyzing the organization and logic of the article; secondly, generating a mind map that displays the main content and structural relationships, helping students intuitively grasp the framework of the article.

---

# dify-article-structure-analysis

Use Dify chat api to article structure analysis.

## Setup

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
passage the reference article content, if not available, please request input;

```bash
DIFY_API_HOST=$(cat ~/.config/dify/api_host)
DIFY_API_KEY=$(cat ~/.config/dify/api_key/{skill_name})

curl -X POST "$DIFY_API_HOST/v1/workflows/run" \
  -H "Authorization: Bearer $DIFY_API_KEY" \
  -H "Content-Type: application/json" \
  --data-raw '{
    "inputs": {
    "{variable_name}": 
    [
      {
      "transfer_method": "local_file",
      "upload_file_id": "{upload_file_id}",
      "type": "{document_type}",
	  "grade": "{grade}",
	  "passage": "{passage}"
      }
    ]
  },
    "response_mode": "blocking",
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
    "mode": "chat",
    "answer": "...",
    "metadata": {
        "retriever_resources": [
            {
                "position": 1,
                "dataset_id": "",
                "dataset_name": "...",
                "document_id": "",
                "document_name": "...",
                "segment_id": "",
                "score": 0.98,
                "content": "..."
            }
        ]
    },
    "created_at": 1705407629
}
```

### Tips

It may take several minutes to complete the request. Wait patiently until responses come back. Only try one time even there are any errors. If errors happen, tell users error details to let them decide.