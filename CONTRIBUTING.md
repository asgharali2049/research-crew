# Contributing to Research Crew

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing.

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Ask questions if anything is unclear
- Help others succeed

## How to Contribute

### Reporting Issues

1. Check if the issue already exists
2. Provide a clear description of the problem
3. Include steps to reproduce
4. Share relevant error messages or logs
5. Mention your Python version and OS

### Submitting Changes

1. **Fork the repository**
```bash
git clone https://github.com/YOUR_USERNAME/research-crew.git
cd research-crew
```

2. **Create a feature branch**
```bash
git checkout -b feature/your-feature-name
```

3. **Make your changes**
- Write clean, readable code
- Follow PEP 8 style guide
- Add comments for complex logic
- Test your changes

4. **Commit with clear messages**
```bash
git commit -m "feat: add new feature description"
git commit -m "fix: resolve issue with..."
git commit -m "docs: update documentation"
```

5. **Push and create a Pull Request**
```bash
git push origin feature/your-feature-name
```

## Development Setup

```bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/research-crew.git
cd research-crew

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -e .
pip install pytest black flake8

# Run tests
pytest

# Format code
black src/

# Lint
flake8 src/
```

## Areas for Contribution

- 🐛 **Bug fixes** - Help fix existing issues
- ✨ **New features** - Add new agents, tools, or capabilities
- 📚 **Documentation** - Improve README, docstrings, examples
- 🧪 **Tests** - Add or improve test coverage
- 💡 **Ideas** - Suggest improvements or new use cases

## Feature Ideas

- Additional specialized agents (researcher, analyst, etc.)
- Export formats (PDF, HTML, JSON)
- Web UI for job management
- Scheduled research runs
- Multi-language support
- Custom tool integrations
- Performance optimizations

## Testing

Before submitting:

```bash
# Run all tests
pytest

# Run specific test
pytest tests/test_crew.py

# With coverage
pytest --cov=src tests/
```

## Documentation

If adding a feature:
- Update README.md
- Add docstrings to functions
- Update config examples
- Add usage examples

## Pull Request Process

1. Update README if needed
2. Add tests for new functionality
3. Ensure all tests pass
4. Provide clear PR description
5. Link related issues
6. Be responsive to feedback

## Questions?

- Open a GitHub Discussion
- Ask in the Issues section
- Check existing documentation

## License

By contributing, you agree your changes will be licensed under the MIT License.

---

Thanks for contributing to Research Crew! 🚀
