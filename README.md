# mcp-deep-research

TBH I'm impressed by OpenAI deep research, but I challenge the sale value of OpenAI pro subscription $200 per month just for it. This is MCP version of deep research. I tried 
- [David's deep-research](https://github.com/dzhng/deep-research)
- [Perplexity deep research](https://www.perplexity.ai/)
- OpenAI deep research with Pro subscription

I thinks a chain of LLM deep diving conversations with web search and external tool calls should resolves many research problems.

[HearMeOut-13's deep-research](https://www.reddit.com/r/ClaudeAI/comments/1ijg50g/guide_setting_up_deep_research_capabilities_with/) just demod it possible to do with MCP. I really like the idea.

Why MCP instead of a in-house LLM agent? The big reason is extensibility. Most in-house agent hard-codes prompts even with template style. There is development requirement to use external tool. MCP just upload development of extension to LLM and MCP servers.

## required MCP servers
- Search. It could be [Brave Search](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) or [Firecrawl](https://github.com/mendableai/firecrawl-mcp-server).
- Fetch, https://github.com/modelcontextprotocol/servers/tree/main/src/fetch
- Sequential Thinking, https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking
- Time, https://github.com/modelcontextprotocol/servers/tree/main/src/time


## Usage
After you installed/config required MCP servers, you just need to download guide.md, then attach it to Claude converstion or add it Cursor chat context. Please use prompt like:

```Research opportunities and challenges of AI and MCP that's introduced by Anthropic in end of 2024 as a new agent framework AI in 2025 for 1200 seconds.```

I recommend to use claude-3.7-sonnet-thinking model.

## Advantage
- It could be automatically extended by utilizing all avaiable MCP servers for you.
- You are free to change [guide.md](https://raw.githubusercontent.com/bobbercheng/mcp-deep-research/main/guide.md) to add your custimization.

## Limit
- It depends on MCP server capabilities. E.g. if Brave Search cannot parse search content result as markdown correctly, you may not get correct resolve.
- I try to keep it as simple as possible to improve easy understanding, so no complex handling for edge cases.
- LLM model like claude-3.7-sonnet-thinking is good but still limited. E.g. it cannot follow 20 minutes duration strictly.

## Contribution
You are welcome to submit PR.

## Thanks
I really appreciated David's repository and HearMeOut-13's sharing.


## Reference
[David's deep-research](https://github.com/dzhng/deep-research)
[HearMeOut-13's deep-research](https://www.reddit.com/r/ClaudeAI/comments/1ijg50g/guide_setting_up_deep_research_capabilities_with/)

