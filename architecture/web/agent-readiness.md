# Making apps agent-friendly

This is primarily done by using existing best practices, standards, and semantic structuring, though there are some emerging new standards that are low-lift and we should start doing as standard practice.

## Make content machine-understandable
Just do what everyone's been saying to do since the 90s.

- Semantic HTML with headings, navigation, lists, etc
- All pages should have descriptive page titles and metadata
- Use permalinks, and redirects as appropriate
- Labels on forms
- Alt text on images. Also supports accessibility and screen readers. Include punctuation to support readers.
- ARIA attributes to support labels and descriptions

## Include an llms.txt
Not yet a standard but supported by OpenAI, Anthropic, and Perplexity, and causes no harm for others. Not yet Gemini. See our [llms.txt template](/templates/web/llms.txt) for an example.

## More involved

### Add machine-accessible *.md versions of html pages, just for AIs
Only really feasible when a site is generated from a DB or static files.

### Add an API
Allow agents to get data programmatically

### MCP and A2A
And if they suit the use case and you've got $$$