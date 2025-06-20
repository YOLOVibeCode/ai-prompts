# ai-prompts

This repository is a holding area for sample prompts, some high level tips, [links](links.md), and maybe some [ideas for things to do](todo-list.md)


## Windsurf/Cascade Configuration

### Global Rules
The global rules apply to all projects and are stored in your Windsurf memory system.

**Files:**
- [Global Rules Template](windsurf/global_rules.md) - The master template for global rules
- [Cascade System Prompt](windsurf/cascade/cascade-system-prompt.txt) - Full system prompt reference
- [Cascade Global Rules](windsurf/cascade/global_rules.md) - Formatted version for Cascade

**To Update Global Rules:**
1. Edit the `windsurf/global_rules.md` file in this repository
2. Copy the entire contents of the file
3. In Windsurf, go to Settings → Memory → Global Rules
4. Paste the updated content and save
5. The new rules will apply to all future conversations

### Project-Specific Rules
For project-specific customizations, create a `rules.md` file in your project's `.windsurf` directory.

**Template:** [windsurf/rules.md](windsurf/rules.md)

**Usage:**
1. Create a `.windsurf` directory in your project root (if it doesn't exist)
2. Copy `windsurf/rules.md` to `.windsurf/rules.md` in your project
3. Customize the rules for your specific project needs
4. Windsurf will automatically detect and apply these rules when working in that project

### Cascade
 - [Windsurf: Cascade Global Rules](windsurf/cascade/global_rules.md)
   - Not sure if formatting needs to be fixed

### Stable Diffusion XL
 - [Overview](stable-diffusion/sdxl-overview.md)
 - [Negative Prompts](stable-diffusion/negative-prompts.md)
