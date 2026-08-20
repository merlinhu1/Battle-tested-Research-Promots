---
name: research-thinking
description: Use Claude Opus 4.6 with extended thinking (max effort) + web search for hard research problems (e.g. analyzing experiment results, designing methods, deciding what to do next, doing math/theory, literature review, etc).
---

# Research Thinking Skill

## Instructions

When this skill is invoked, call the Claude Opus 4.6 API with extended thinking using Python:

```bash
python3 -c "
import os, json, urllib.request, sys

problem = '''QUERY_HERE'''

data = json.dumps({
    'model': 'claude-opus-4-6-20250310',
    'max_tokens': 16000,
    'thinking': {'type': 'adaptive'},
    'output_config': {'effort': 'max'},
    'temperature': 1,
    'messages': [{'role': 'user', 'content': problem}]
}).encode()

req = urllib.request.Request(
    'https://api.anthropic.com/v1/messages',
    data=data,
    headers={
        'Content-Type': 'application/json',
        'x-api-key': os.environ['ANTHROPIC_API_KEY'],
        'anthropic-version': '2023-06-01'
    }
)

try:
    with urllib.request.urlopen(req, timeout=1200) as resp:
        result = json.loads(resp.read())
        for block in result.get('content', []):
            if block.get('type') == 'thinking':
                print('<thinking>')
                print(block.get('thinking', ''))
                print('</thinking>')
                print()
            elif block.get('type') == 'text':
                print(block.get('text', ''))
except urllib.error.HTTPError as e:
    print(f'Error {e.code}: {e.read().decode()}', file=sys.stderr)
    sys.exit(1)
"
```

Replace `QUERY_HERE` with the actual query. For long context queries, include all relevant data in the problem string.

## Requirements

- The `ANTHROPIC_API_KEY` environment variable must be set
- Python 3 must be available

## Notes

- Uses Claude Opus 4.6 (claude-opus-4-6-20250310) -- the most capable model
- Adaptive thinking with max effort -- Claude decides how deeply to think
- temperature must be 1 when using thinking (API requirement)
- Max output tokens: 16000 (excluding thinking tokens)
- Timeout: 1200s (deep thinking can take a while)

## Output

Present the full response including thinking process to the user.
