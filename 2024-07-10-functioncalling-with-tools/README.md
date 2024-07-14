# functioncalling with Tools

This is an example of how function calling works. And we specifically look at using multiple tools from Ollama. 

The websearch code assumes that you have a local install of Searxng installed and running on port 8080. You can find instructions on how to install it here: https://github.com/searxng/searxng

settings.yml needs to be completed with:
```ui:
  static_use_hash: true

redis:
  url: redis://redis:6379/0

search:
  formats:
    - html
    - json

cors_domains:
  - "*"

logging:
  version: 1
  disable_existing_loggers: false
  formatters:
    simple:
      format: '%(asctime)s - %(name)s - %(levelname)s - %(message)s'
  handlers:
    console:
      class: logging.StreamHandler
      formatter: simple
  root:
    level: DEBUG
    handlers: [console]
```


To install dependencies:

```bash
bun install
```

To run:

```bash
bun run index.ts
```

