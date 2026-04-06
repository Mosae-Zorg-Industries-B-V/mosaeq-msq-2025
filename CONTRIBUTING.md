# Deployment Rules

## One Change Per Commit
- Never combine unrelated changes in a single commit
- Each commit = ONE logical change (one fix, one feature, one style update)
- If a task requires changes to multiple files, that is fine — but all changes must serve the same single purpose

## Before Every Push
1. Run `npm run build` locally
2. Fix ALL errors and warnings before committing
3. Test in browser (localhost)
4. Verify in incognito window after deployment
5. Never trust "already clean" confirmations without visual verification

## Commit Messages
Format: `type: description`
Examples:
- `fix: remove unicode BOM from LabWorkspace.tsx`
- `feat: add pricing section to homepage`
- `style: restore navy sidebar colors`

## Forbidden
- No unicode characters (BOM, diamonds, special chars) at start of files
- No combining color changes with feature changes
- No pushing without local build passing
- No "batch" commits with 5 unrelated things

## Rollback
If a deployment breaks, revert the single commit:
```
git revert HEAD
git push
```
This works ONLY if commits are single-purpose.
