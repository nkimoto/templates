# Project Templates

A collection of language-specific project templates using cookiecutter for modern development workflows.

## Available Templates

### Python Template
Located in `python/` directory, featuring:
- **uv** for fast Python package management
- **ruff** for linting and formatting
- **mypy** for type checking
- **pytest** for testing
- **Cursor AI** integration

### TypeScript Template
Located in `typescript/` directory, featuring:
- **npm/yarn** for package management
- **ESLint** for linting
- **Prettier** for code formatting
- **Jest** for testing
- **TypeScript** configuration
- **Cursor AI** integration

*More templates coming soon...*

## Usage

### Prerequisites

1. Install cookiecutter:
```bash
pip install cookiecutter
```

2. Install language-specific tools:
   - **Python**: Install uv
     ```bash
     curl -LsSf https://astral.sh/uv/install.sh | sh
     ```
   - **TypeScript**: Install Node.js and npm/yarn
     ```bash
     # Node.js installation varies by platform
     # Visit https://nodejs.org/ for instructions
     ```

### Creating a New Project

#### Python Project

1. Generate a new Python project:
```bash
cookiecutter python/
```

2. Follow the interactive prompts:
   - `project_name`: Your project name (e.g., "My Awesome Project")
   - `project_description`: Brief description of your project
   - `python_version`: Python version (default: 3.13)
   - `license`: Choose from MIT, Apache-2.0, GPL-3.0, BSD-3-Clause, or None

3. Navigate to your new project:
```bash
cd your-project-name/
```

4. Initialize the development environment:
```bash
# Install dependencies
uv sync

# Install development dependencies
uv sync --dev

# Activate virtual environment
source .venv/bin/activate  # On Unix/macOS
# or
.venv\Scripts\activate     # On Windows
```

5. Start developing:
```bash
# Format code
ruff format

# Lint code
ruff check

# Run tests
pytest

# Add your main application code and run
python -m your_project_name.main
```

#### TypeScript Project

1. Generate a new TypeScript project:
```bash
cookiecutter typescript/
```

2. Follow the interactive prompts:
   - `project_name`: Your project name
   - `project_description`: Brief description of your project
   - `package_manager`: Choose between npm, yarn, or pnpm
   - `license`: Choose from MIT, Apache-2.0, GPL-3.0, BSD-3-Clause, or None

3. Navigate to your new project:
```bash
cd your-project-name/
```

4. Initialize the development environment:
```bash
# Install dependencies
npm install
# or
yarn install
# or
pnpm install
```

5. Start developing:
```bash
# Lint code
npm run lint

# Format code
npm run format

# Run tests
npm test

# Start development server
npm run dev
```

## Template Structure

### Python Template
```
python/
├── cookiecutter.json                    # Template configuration
└── {{cookiecutter.project_slug}}/      # Generated project structure
    ├── pyproject.toml                  # Project configuration (uv, ruff, mypy, pytest)
    ├── README.md                       # Project documentation
    ├── .gitignore                      # Git ignore rules
    ├── .cursorrules                    # Cursor AI configuration
    ├── {{cookiecutter.project_slug}}/  # Main package
    │   └── __init__.py
    └── tests/                          # Test directory
        └── __init__.py
```

### TypeScript Template
```
typescript/
├── cookiecutter.json                   # Template configuration
└── {{cookiecutter.project_slug}}/     # Generated project structure
    ├── package.json                    # Project configuration
    ├── tsconfig.json                   # TypeScript configuration
    ├── .eslintrc.js                   # ESLint configuration
    ├── .prettierrc                    # Prettier configuration
    ├── README.md                      # Project documentation
    ├── .gitignore                     # Git ignore rules
    ├── .cursorrules                   # Cursor AI configuration
    ├── src/                           # Source code
    │   ├── index.ts
    │   └── utils.ts
    └── tests/                         # Test directory
        ├── index.test.ts
        └── utils.test.ts
```

## Features

### Python Template Features
- **Modern Python Development**: Uses uv for fast dependency management
- **Code Quality**: Integrated ruff for linting and formatting
- **Type Safety**: mypy configuration for static type checking
- **Testing**: pytest setup with coverage reporting
- **AI Integration**: Cursor AI configuration for enhanced development
- **Project Structure**: Standard Python package layout
- **Documentation**: Comprehensive README with usage instructions

### TypeScript Template Features
- **Modern TypeScript Development**: Full TypeScript configuration
- **Code Quality**: ESLint and Prettier for linting and formatting
- **Testing**: Jest setup with coverage reporting
- **Package Management**: Support for npm, yarn, and pnpm
- **AI Integration**: Cursor AI configuration for enhanced development
- **Project Structure**: Standard TypeScript/Node.js layout
- **Documentation**: Comprehensive README with usage instructions

## Development Workflow

### For Python Projects

1. **Setup**:
   ```bash
   cookiecutter python/
   cd your-project-name/
   uv sync --dev
   ```

2. **Daily Development**:
   ```bash
   # Format and lint code
   ruff format && ruff check
   
   # Run tests
   pytest
   
   # Type checking
   mypy your_project_name/
   ```

3. **Before Committing**:
   ```bash
   # Ensure code quality
   ruff check --fix
   pytest --cov
   ```

### For TypeScript Projects

1. **Setup**:
   ```bash
   cookiecutter typescript/
   cd your-project-name/
   npm install
   ```

2. **Daily Development**:
   ```bash
   # Lint and format code
   npm run lint && npm run format
   
   # Run tests
   npm test
   
   # Type checking
   npm run type-check
   ```

3. **Before Committing**:
   ```bash
   # Ensure code quality
   npm run lint:fix
   npm test -- --coverage
   ```

## Adding New Language Templates

### Template Structure
Each language template should follow this structure:
```
language-name/
├── cookiecutter.json                   # Template configuration
└── {{cookiecutter.project_slug}}/     # Generated project structure
    ├── [language-specific config files]
    ├── README.md                       # Project documentation
    ├── .gitignore                      # Git ignore rules
    ├── .cursorrules                    # Cursor AI configuration
    ├── src/ or lib/                    # Source code directory
    └── tests/                          # Test directory
```

### Required Files
- `cookiecutter.json`: Template configuration with variables
- `README.md`: Project documentation template
- `.gitignore`: Language-specific git ignore rules
- `.cursorrules`: Cursor AI configuration
- Language-specific configuration files (e.g., `package.json`, `pyproject.toml`)

### Best Practices
1. **Modern Tools**: Use the latest and most popular tools for each language
2. **Code Quality**: Include linting, formatting, and testing tools
3. **AI Integration**: Add Cursor AI configuration for enhanced development
4. **Documentation**: Provide comprehensive README with usage instructions
5. **Standard Structure**: Follow language-specific conventions and best practices

## Customization

### Modifying Existing Templates

- Edit the `cookiecutter.json` file to add/remove variables
- Modify template files to change the generated structure
- Update documentation in README files

### Creating Custom Templates

1. Create a new directory for your template:
   ```bash
   mkdir your-language/
   ```

2. Add a `cookiecutter.json` file with your template configuration

3. Create the template structure with `{{cookiecutter.variable_name}}` placeholders

4. Test your template by generating a new project

## Contributing

1. Fork this repository
2. Create a feature branch
3. Make your changes
4. Test your template by generating a new project
5. Submit a pull request

## License

This project is licensed under the MIT License.