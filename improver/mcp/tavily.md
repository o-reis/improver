# Tavily Search Server

MCP server for web search capabilities.

## Installation

```bash
npm install -g @modelcontextprotocol/server-tavily
```

## Configuration

```yaml
tavily:
  enabled: true
  auth_token: ${TAVILY_API_KEY}
  
  settings:
    max_results: 10
    search_depth: "advanced"
    include_answer: true
    include_raw_content: false
```

## Environment Variable

```
TAVILY_API_KEY=your_api_key_here
```

## Usage

```
Tool: tavily_search
Input: { query: string, max_results?: number }
Output: { results: SearchResult[], answer?: string }
```

## Rate Limits

- Free tier: 1000 requests/month
- Paid tiers available at tavily.ai
