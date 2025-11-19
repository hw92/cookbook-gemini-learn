# Daily Learning Workflow

## Setup
1. Work in `dev` branch
2. Create `labs/` folder for your code
3. One tutorial per session (deep learning > breadth)

## For Each Tutorial

### 1. Preview (5-10 min)
```bash
# Open the notebook and scan
jupyter notebook quickstarts/[Tutorial].ipynb
```

### 2. Study (30-60 min)
- Read through completely first
- Note key concepts
- Understand the API patterns

### 3. Experiment (30-60 min)
- Run the code with your own data
- Modify parameters
- Try variations
- Break things intentionally

### 4. Document (15-30 min)
Create: `docs/learning-notes/YYYY-MM-DD-[tutorial-name]-HH-MM.md`

Template:
```markdown
# [Tutorial Name]

**Date**: YYYY-MM-DD
**Time**: HH:MM
**Notebook**: quickstarts/[name].ipynb

## Key Learnings
- Point 1
- Point 2

## Code Patterns
```python
# Important patterns discovered
```

## Gotchas
- Common errors
- Things to watch out for

## Ideas for AI Code Agent
- How this applies to building agents
- Specific use cases

## Questions
- Unresolved questions
- Deep dive topics
```

### 5. Commit Progress
```bash
git add docs/learning-notes labs/
git commit -m "Learning: [tutorial name] - [key insight]"
```

## Weekly Review
Every Sunday:
- Review all notes from the week
- Update main learning strategy
- Plan next week's tutorials
- Identify patterns across tutorials

## Building Your Agent

### Incremental Development
After Phase 2, start building:

**Week 3-4**: MVP Agent
- Pick one use case (e.g., code review)
- Implement basic function calling
- Test on real code

**Week 5-6**: Enhanced Agent
- Add more tools
- Improve prompts
- Add error handling

**Week 7-8**: Production Ready
- Add rate limiting
- Implement caching
- Create web interface

## Tips
1. **Don't rush** - Deep understanding > coverage
2. **Experiment freely** - Break things in dev branch
3. **Document immediately** - Don't trust future memory
4. **Build incrementally** - Apply learnings right away
5. **Ask questions** - Use the Google AI forum
