# Concordantia - citation-verified theology for Claude Desktop

Concordantia is an MCP connector for Claude Desktop that grounds answers
in a 64.2M-word library of classical Christian theology - and
mechanically verifies every quote before it reaches you.

## Install (macOS)

1. Download the Concordantia-for-Claude-darwin-arm64.mcpb for your Mac
   (Apple Silicon) or -x64 (Intel) below, and double-click it.
   Claude Desktop opens an install dialog - click Install.
2. Upload the skill: Settings > Capabilities > enable Code execution
   and file creation, then under Skills upload
   concordantia-study-skill.zip (also below) and toggle it ON.
3. Start a new chat and ask any doctrine question - e.g. "How does a
   Christian calling and work relate to their salvation?" The
   connector tools (study_topic, search, fetch, verify) run
   automatically and answers end with a Sources list.

## Windows

Download the win32-x64 MCPB / binary. (Unsigned builds trigger
SmartScreen - More info > Run anyway - until code-signed.)

## First use

The sidecar database (~975 MB) downloads automatically on your first
search into a managed folder - you never configure paths. After that,
everything is instant and fully local.

## Notes

- Every quote in an answer has been mechanically checked against the
  source text. The library currently leans Reformation/Protestant;
  ask and we can show how other traditions differ.
- Requires Claude Desktop with MCP extensions.
- macOS unsigned-build fallback: if the Concordantia tools do not appear
  after installing (Gatekeeper blocked the bundled binary), open
  Terminal once and run:
  xattr -dr com.apple.quarantine "$HOME/Library/Application Support/Claude/Claude Extensions/local.mcpb.flaremark.concordantia"
  then restart Claude Desktop. (Not needed on signed/notarized builds.)
