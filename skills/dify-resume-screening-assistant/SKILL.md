---
name: dify-resume-screening-assistant
description: Provides resume pre-screening capabilities for enterprises, enabling minute-level screening of a large number of resumes based on job requirements, and intelligently quantifying the matching degree to improve recruitment efficiency and reduce labor costs.
---

# dify-resume-screening-assistant

Use Dify chat api to Screen Resumes.

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
      "type": "{document_type}"
      }
    ]
    }
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

### Response

The example response for blocking mode.

```json
{
  "workflow_run_id": "djflajgkldjgd",
  "task_id": "9da23599-e713-473b-982c-4328d4f5c78a",
  "data": {
    "id": "fdlsjfjejkghjda",
    "workflow_id": "fldjaslkfjlsda",
    "status": "succeeded",
    "outputs": {
      "text": "Nice to meet you."
    },
    "error": null,
    "elapsed_time": 0.875,
    "total_tokens": 3562,
    "total_steps": 8,
    "created_at": 1705407629,
    "finished_at": 1727807631
  }
}
```

### Tips

It may take several minutes to complete the request. Wait patiently until responses come back. Only try one time even there are any errors. If errors happen, tell users error details to let them decide.
