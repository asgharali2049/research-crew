# Research Crew 🤖

A powerful multi-agent AI system built with [CrewAI](https://crewai.com) that conducts thorough research on any topic and generates comprehensive reports.

## Overview

Research Crew orchestrates multiple AI agents to:
- **Research** - Uncover cutting-edge developments and insights on your topic
- **Analyze** - Process and organize complex information
- **Report** - Generate detailed, well-structured reports in Markdown format

Perfect for market research, competitive analysis, technology trends, and general information gathering.

## Features

- 🔍 **Intelligent Research** - AI-powered agents that dig deep into topics
- 📊 **Structured Reports** - Auto-generated Markdown reports with organized sections
- 🔄 **Sequential Processing** - Agents work together in a logical workflow
- 🎯 **Customizable** - Easily modify agents, tasks, and tools
- 🚀 **Production Ready** - Built on proven CrewAI framework
- 📝 **Training & Testing** - Train agents or replay specific tasks

## Quick Start

### Prerequisites

- Python 3.10+ (< 3.14)
- OpenAI API key (or compatible LLM)

### Installation

1. **Clone and Navigate**
```bash
git clone https://github.com/YOUR_USERNAME/research-crew.git
cd research-crew
```

2. **Install UV** (if not already installed)
```bash
pip install uv
```

3. **Install Dependencies**
```bash
uv sync
```

4. **Configure Environment**
Copy `.env.example` to `.env` and add your OpenAI API key:
```bash
cp .env.example .env
```

Then edit `.env`:
```env
OPENAI_API_KEY=your_api_key_here
```

### Run Your First Research

```bash
crewai run
```

This will research "AI LLMs" and generate `report.md` in the current directory.

### Customize for Your Topic

Edit `src/research_crew/main.py` and change the `topic` input:

```python
def run():
    inputs = {
        'topic': 'Your Topic Here',  # Change this!
        'current_year': str(datetime.now().year)
    }
    ResearchCrew().crew().kickoff(inputs=inputs)
```

Then run:
```bash
crewai run
```

## Project Structure

```
research-crew/
├── src/research_crew/
│   ├── crew.py              # Crew orchestration
│   ├── main.py              # Entry point
│   └── config/
│       ├── agents.yaml      # Agent definitions
│       └── tasks.yaml       # Task definitions
├── .env.example             # Example environment variables
├── requirements.txt         # Python dependencies
├── pyproject.toml          # Project configuration
└── README.md               # This file
```

## Agents

### 1. Researcher
- **Role**: Senior Data Researcher
- **Goal**: Uncover cutting-edge developments
- **Specialty**: Finding relevant, up-to-date information

### 2. Reporting Analyst
- **Role**: Technical Reporting Analyst
- **Goal**: Create detailed reports from research findings
- **Specialty**: Transforming research into structured, readable reports

## Customization

### Modify Agents

Edit `src/research_crew/config/agents.yaml`:

```yaml
researcher:
  role: >
    {topic} Research Specialist
  goal: >
    Provide comprehensive insights on {topic}
  backstory: >
    You're an expert researcher...
```

### Modify Tasks

Edit `src/research_crew/config/tasks.yaml`:

```yaml
research_task:
  description: >
    Research about {topic}...
  expected_output: >
    A detailed analysis...
```

### Add Custom Tools

Edit `src/research_crew/crew.py` and add tools to agents:

```python
@agent
def researcher(self) -> Agent:
    return Agent(
        config=self.agents_config['researcher'],
        tools=[search_tool, web_tool],  # Add your tools
        verbose=True
    )
```

## Advanced Usage

### Train the Crew

Improve agent performance through iterative training:

```bash
crewai train -n 5 -f training_data.json
```

### Replay Specific Tasks

Replay execution from a specific task ID:

```bash
crewai replay -t <task_id>
```

### Interactive Mode

Run an interactive session with your crew:

```bash
crewai chat
```

### Run Tests

Test crew functionality:

```bash
crewai test
```

## Environment Variables

Required:
- `OPENAI_API_KEY` - Your OpenAI API key

Optional:
- `MODEL` - LLM model to use (default: gpt-4o)
- `LOG_LEVEL` - Logging level (debug, info, warning, error)

See `.env.example` for a template.

## Output

By default, the crew generates:
- `report.md` - Complete research report in Markdown format

You can modify the output file in `src/research_crew/crew.py`:

```python
@task
def reporting_task(self) -> Task:
    return Task(
        config=self.tasks_config['reporting_task'],
        output_file='custom_report.md'  # Change output file
    )
```

## API Costs

Research Crew uses your OpenAI API. Cost depends on:
- Topic complexity
- Report length
- Number of iterations (if training)

Monitor your usage at [https://platform.openai.com/account/usage](https://platform.openai.com/account/usage)

## Examples

### Example 1: Technology Trends

```python
inputs = {
    'topic': 'AI and Machine Learning Trends 2026',
    'current_year': '2026'
}
```

### Example 2: Market Research

```python
inputs = {
    'topic': 'Cloud Computing Market Analysis',
    'current_year': '2026'
}
```

### Example 3: Competitive Analysis

```python
inputs = {
    'topic': 'Competitive Landscape of Web Frameworks',
    'current_year': '2026'
}
```

## Troubleshooting

### API Key Error
Ensure `OPENAI_API_KEY` is set in `.env`:
```bash
echo $env:OPENAI_API_KEY  # Windows PowerShell
```

### Timeout Issues
Increase timeout for large topics by modifying `crew.py`

### Rate Limiting
If you hit OpenAI rate limits, increase the delay between requests or use a different model.

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT License - See LICENSE file for details

## Resources

- [CrewAI Documentation](https://docs.crewai.com)
- [OpenAI API Reference](https://platform.openai.com/docs)
- [CrewAI GitHub](https://github.com/joaomdmoura/crewai)

## Support

For issues and questions:
1. Check [existing issues](https://github.com/YOUR_USERNAME/research-crew/issues)
2. Create a [new issue](https://github.com/YOUR_USERNAME/research-crew/issues/new)
3. Review [CrewAI documentation](https://docs.crewai.com)

---

Built with ❤️ using [CrewAI](https://crewai.com)
