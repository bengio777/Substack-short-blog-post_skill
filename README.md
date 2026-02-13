# Blog Post Skill

A Claude Code skill that provides an end-to-end blog post creation workflow — from research and outlining through drafting, editing, and publish-ready output.

## Overview

This skill guides Claude through a structured blog post workflow, producing consistent, high-quality content across every stage:

1. **Research** — Gather context, sources, and key points on the topic
2. **Outline** — Structure the post with sections, flow, and logical progression
3. **Draft** — Write the full post based on the approved outline
4. **Edit** — Refine for clarity, tone, structure, and readability
5. **Publish-Ready Output** — Final formatted post ready for publication

## Installation

Copy the skill file into your Claude Code skills directory:

```bash
cp blog-post.md ~/.claude/skills/
```

Or symlink for development:

```bash
ln -s "$(pwd)/blog-post.md" ~/.claude/skills/blog-post.md
```

## Usage

Once installed, Claude Code will automatically invoke the skill when you ask it to write a blog post. You can also trigger it directly:

```
Write a blog post about [your topic]
```

The skill walks through each stage interactively, asking for your input and approval before moving to the next phase.

## Project Structure

```
Blog_Post_Skill/
├── README.md           # This file
└── blog-post.md        # The skill definition
```

## Development

To modify the skill, edit `blog-post.md` and test by invoking the workflow in a Claude Code session. See the [Claude Code skill development docs](https://docs.anthropic.com) for authoring guidelines.

## License

MIT
