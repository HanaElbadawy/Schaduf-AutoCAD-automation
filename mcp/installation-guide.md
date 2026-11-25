# AutoCAD MCP - Team Setup Guide

## What is AutoCAD MCP?

AutoCAD MCP allows Claude Desktop to communicate with AutoCAD and execute drawing operations.

## Requirements

Each team member needs:

- Windows PC
- AutoCAD installed
- Claude Desktop installed
- Git installed
- uv installed

## MCP Configuration

The configuration is available in:

`mcp/claude_desktop_config.example.json`

Copy the AutoCAD server configuration into your Claude Desktop configuration file:

`%APPDATA%\Claude\claude_desktop_config.json`

Do not delete other MCP server configurations.

## Start the MCP Server

1. Open AutoCAD.
2. Keep AutoCAD running.
3. Restart Claude Desktop.
4. Check that the AutoCAD MCP server is connected.

## Important Notes

- Every team member must configure the MCP on their own PC.
- The MCP server package is installed through uvx.
- This repository contains configuration examples, not the original MCP server source code.
- Do not share personal credentials or API keys.