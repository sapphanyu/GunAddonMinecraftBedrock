# Pure JSON Architecture

We decided to build the tactical gun system using pure Minecraft Bedrock JSON components and custom projectile entities rather than the Bedrock Script API (`@minecraft/server`). This eliminates experimental script requirements, maximizes cross-platform compatibility across Bedrock platforms (mobile, console, Windows), simplifies installation, and prevents script version deprecation issues, accepting the trade-off of high-speed entity collision physics instead of instant raycast hitscan.
