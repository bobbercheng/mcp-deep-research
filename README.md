# mcp-deep-research

TBH I'm impressed by OpenAI deep research, but I challenge the sale value of OpenAI pro subscription $200 per month just for it. This is MCP version of deep research. I tried 
- [David's deep-research](https://github.com/dzhng/deep-research)
- [Perplexity deep research](https://www.perplexity.ai/)
- OpenAI deep research with Pro subscription

I thinks a chain of LLM deep diving conversations with web search and external tool calls should resolves many research problems.

[HearMeOut-13's deep-research](https://www.reddit.com/r/ClaudeAI/comments/1ijg50g/guide_setting_up_deep_research_capabilities_with/) just demo that it's possible to do with MCP. I really like the idea.

Why MCP instead of a in-house LLM agent? The big reason is extensibility. Most in-house agent hard-codes prompts even with template style. There is development requirement to use external tool. MCP just offload development of extension to LLM and MCP servers.

## required MCP servers
- Search. It could be [Brave Search](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search), [Firecrawl](https://github.com/mendableai/firecrawl-mcp-server) or webresearch with Google.
- Fetch, https://github.com/modelcontextprotocol/servers/tree/main/src/fetch
- Sequential Thinking, https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking
- Time, https://github.com/modelcontextprotocol/servers/tree/main/src/time


## Usage
You can install required MCPs by yourself or you just use my MCPs hosted in GCP and Oracle cloud. To use my MCP in cursor, you just need to copy content of [mcp.json](https://raw.githubusercontent.com/bobbercheng/mcp-deep-research/main/mcp.json) to your MCP config file ~/.cursor/mcp.json. After you installed/config required MCP servers, you just need to download guide.md, then attach it to Claude conversation or add it Cursor chat context. Please modify following prompt to start your research:

```Research opportunities and challenges of AI and MCP that's introduced by Anthropic in end of 2024 as a new agent framework AI in 2025 for 1200 seconds.```

I recommend to use claude-3.7-sonnet-thinking model.

## Advantage
- It could be automatically extended by utilizing all available MCP servers for you.
- You are free to change [guide.md](https://raw.githubusercontent.com/bobbercheng/mcp-deep-research/main/guide.md) to add your customization.

## Limit
- It depends on MCP server capabilities. E.g. if Brave Search cannot parse search content result as markdown correctly, you may not get correct resolve. The solution is to review your MCP server capability, maybe replace some to more powerful version or add complementary MCP servers.
- I try to keep it as simple as possible to improve easy understanding, so no complex handling for edge cases. Both OpenAI and Perplexity version of Deep research have complex built-in reasoning. If you need more reasoning, please feel free to add it to [guide.md](https://raw.githubusercontent.com/bobbercheng/mcp-deep-research/main/guide.md).
- LLM model like claude-3.7-sonnet-thinking is good but still limited. E.g. it cannot follow 20 minutes duration strictly. One solution here is add code to [guide.md](https://raw.githubusercontent.com/bobbercheng/mcp-deep-research/main/guide.md) to increase reasoning. 

## Contribution
You are welcome to submit PR.

## Thanks
I really appreciated David's repository and HearMeOut-13's sharing.


## Reference
[David's deep-research](https://github.com/dzhng/deep-research)
[HearMeOut-13's deep-research](https://www.reddit.com/r/ClaudeAI/comments/1ijg50g/guide_setting_up_deep_research_capabilities_with/)

