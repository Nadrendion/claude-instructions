# Claude instructions

Project- and technology-neutral working instructions for Claude. They grow from decisions made during real work.

## Use

Clone this repo to your home folder:

```bash
git clone https://github.com/Nadrendion/claude-instructions.git ~/claude-instructions
```

Then add this line to `~/.claude/CLAUDE.md` to load the instructions in every project on that computer:

```text
@~/claude-instructions/instructions.md
```

Run `git pull` in `~/claude-instructions` to get the latest version.

## Skills

`skills` holds procedures that Claude loads when a task needs them, such as planning or merging. Link the folder so Claude finds them, and `git pull` keeps them current.

On Windows, in PowerShell:

```powershell
New-Item -ItemType Junction -Path ~/.claude/skills -Target ~/claude-instructions/skills
```

On macOS or Linux:

```bash
ln -s ~/claude-instructions/skills ~/.claude/skills
```
