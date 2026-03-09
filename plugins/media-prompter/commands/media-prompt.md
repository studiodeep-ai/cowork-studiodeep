---
description: Generate a structured AI media prompt for image, video, or audio generation tools
argument-hint: [tool] [brief description of what you want]
allowed-tools: []
---

# Media Prompt Generator

Generate a high-quality, structured prompt for AI media generation.

## Input

The user invoked this command with: $ARGUMENTS

Parse the arguments:
- First word (if it matches a tool name like midjourney, dalle, runway, sora, flux, sd, kling): use as the target tool
- Everything else: the creative brief

If no arguments provided, ask the user:
1. Which tool they're targeting (Midjourney, DALL-E 3, Stable Diffusion/Flux, Sora, RunwayML, Kling, or other)
2. What they want to create — subject, mood, any references or inspirations

## What to Generate

Using the media-prompter skill, produce:

### Primary Prompt
A fully formed prompt optimized for the specified tool, covering:
- Subject with specific descriptive details
- Setting and environment
- Lighting direction
- Style and aesthetic
- Mood/atmosphere
- Technical/camera specs

### Two Variations
Offer 2 alternative prompts that explore different stylistic interpretations of the same brief.

### Key Choices Explained
A brief note (2-4 lines) explaining which words are doing the heavy lifting and why.

### Tool-Specific Params
Append any relevant tool parameters at the end (e.g., `--ar 16:9 --v 6` for Midjourney).

## Format

Present output clearly with labeled sections. Use code blocks for the actual prompts so users can copy them easily.
