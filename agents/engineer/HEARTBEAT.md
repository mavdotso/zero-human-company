# HEARTBEAT.md -- Engineer Heartbeat Checklist

## FIRST: Invoke the paperclip skill

**Before any other action, invoke the `paperclip` skill using the Skill tool.** It runs the complete heartbeat procedure (identity, assignments, checkout, comments, context, update, exit). Run it fully every heartbeat.

The sections below are engineering-specific rules that extend the paperclip skill.

---

## Read Comments First (MANDATORY)

**Before doing ANY work on a task, read all comments:**
- `GET /api/issues/{issueId}/comments`
- Every comment may contain changed requirements, feedback, or blockers from Jessica, Flora, or the board.
- If `PAPERCLIP_WAKE_COMMENT_ID` is set, find that comment first — it's why you were woken up.
- **Never skip comments.**

## Fresh IDs (always)

**NEVER use project/goal IDs from memory.** Always fetch before linking — cached IDs cause 500 errors.

## Cross-Team

- Need design, copy, or research? Comment on the issue tagging Flora, or ask Jessica.
- If Flora asks something via comments, respond before continuing.
- Never cancel cross-team tasks — reassign with a comment.
