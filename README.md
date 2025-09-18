# Claude Code: Workshop Práctico

## Resumen

Workshop hands-on de 3 horas donde los participantes aprenderán Claude Code construyendo un proyecto web real y configurando flujos de trabajo automatizados.

## 📅 Agenda

### Workshop de 3 horas

1. **Bienvenida e Introducción** (10 min)
2. **Instalación y Configuración** (25 min)
   - Instalación de Claude Code
   - Setup inicial
3. **Integración con VS Code** (15 min)
4. **Primera Interacción con Claude** (10 min)
5. **Construcción de Sitio Web** (45 min)
   - Crear sitio web responsivo
   - Configuración para AWS Amplify
6. **Manejo de Git con Claude** (15 min)
7. **Creación de Subagentes** (30 min)
   - Subagente html-css-standards
   - Subagente repo-structure-manager
8. **Debugging y Mejoras** (20 min)
9. **Servidor MCP Weather** (15 min)
10. **Despliegue con Amplify** (15 min)
11. **Q&A y Cierre** (10 min)

## Requisitos Previos

- Laptop con Node.js 18+ instalado
- Cuenta de Claude
- Terminal y editor de código favorito
- Conocimientos básicos de línea de comandos
- Acceso a GitHub (cuenta personal)
- **uv** instalado (gestor de paquetes Python moderno)

## Estructura del Workshop

### **MÓDULO 1: Configuración y Primer Contacto (50 min)**

#### 🛠️ Lab 1: Instalación y Setup (25 min)
**Objetivo**: Tener Claude Code funcionando y hacer primera interacción

**Proceso paso a paso**:
```bash
# Verificar prerequisitos
node --version  # Debe ser 18+
npm --version
uv --version    # Verificar que uv está instalado

# Instalación global
npm install -g @anthropic-ai/claude-code

# Verificar instalación
claude --version

# Crear workspace del workshop
mkdir claude-workshop
cd claude-workshop
```

**Soluciones comunes**:
- **WSL**: Si usas Windows, instala en WSL, no en Windows directamente
- **Permisos**: Usa sudo en Linux/Mac si es necesario
- **Versión Node**: Actualiza con `nvm install 18 && nvm use 18`
- **uv no instalado**: Instala desde https://docs.astral.sh/uv/getting-started/installation/

#### ⚙️ Lab 2: IDE Integration (15 min)

**VS Code Integration**:
```bash
# Instalar extensión
code --install-extension anthropic.claude-code

# Configurar shortcuts
# Cmd+Esc (Mac) / Ctrl+Esc (Windows) para quick launch
```

**Demostración práctica**:
1. Seleccionar código en VS Code
2. Abrir Claude con shortcut
3. El contexto se comparte automáticamente
4. Hacer cambios en Claude
5. Ver diff integrado en VS Code

#### 🎯 Ejercicio: Primera Interacción (10 min)
```bash
# Iniciar Claude Code
claude

# Exploración inicial
> /help
> What can you tell me about this directory?
> Create a simple "Hello World" Python script that prints the current date
```

**Objetivo**: Ver inmediatamente las capacidades básicas de Claude Code.

---

### **MÓDULO 2: Construcción de Sitio Web con Amplify (60 min)**

#### 🌐 Lab 2: Sitio Web Sencillo para AWS Amplify (45 min)

**Objetivo del Lab**: 
- Construir una página web básica pero profesional
- Configuración simple para AWS Amplify
- Integración básica con GitHub
- Despliegue automático
- Todo usando comandos naturales con Claude Code

**Preparación del repositorio**:
```bash
# Clonar el repositorio del workshop
git clone https://github.com/gamgustavo/dalia-claude-code-workshop.git
cd dalia-claude-code-workshop

# Iniciar Claude Code
claude
```

**Construcción paso a paso**:

**Paso 1: Crear sitio web básico (15 min)**
```
> First, clean up any existing files in this directory, then create a simple, clean website with:
  - Remove any existing HTML, CSS, or config files
  - Single HTML page with basic structure
  - Simple CSS for clean styling
  - Responsive design that works on mobile
  - Basic hero section with title and description
  - Simple navigation menu
  - Footer section
  - Clean, professional look
```

**Paso 2: Configurar para AWS Amplify (15 min)**
```
> Setup this simple website for AWS Amplify deployment:
  1. Create basic amplify.yml file
  2. Add simple build configuration
  3. Configure for static hosting
  4. Add basic redirect rules
```

**Paso 3: Contenido específico del workshop (15 min)**
```
> Add content about our Claude Code workshop:
  1. Hero section: "Claude Code Workshop"
  2. Simple description of what Claude Code is
  3. Basic contact information
  4. Clean, readable layout
```

#### 📋 Git manejado por Claude (15 min)

**Configuración inicial**:
```
> Can you check if git is available and show me the current git status?

> Please configure git for this project:
  - Set up user name and email for commits
  - Initialize git repository if needed
  - Connect to remote repository
  - Set up default branch as main
```

**Workflow automatizado**:
```
> Please handle git operations for our website:
  1. Add all files to git
  2. Create a proper commit message for this new website
  3. Push to the main branch
  4. Set up proper git configuration if needed
```

---

### **MÓDULO 3: Subagentes y Automatización (50 min)**

#### 🧪 Lab 3: Subagentes - Creación y Uso (30 min)

**Método recomendado: Usar CLI de Claude Code**
```bash
# Iniciar Claude Code
claude

# Explorar comandos de subagentes
> /agents
> /help

# Crear subagentes interactivamente
> Create a new subagent called "html-css-standards":
  - Name: html-css-standards
  - Description: Reviews HTML/CSS code for standards compliance
  - Tools: Read, Edit, Write
  - Purpose: Check code quality, naming conventions, structure
  - Location: Project-specific (.claude/agents/)
  - Main rule: Ensure all file names are lowercase (index.html, style.css, not Index.HTML)

> Create a new subagent called "repo-structure-manager":
  - Name: repo-structure-manager
  - Description: Manages repository structure and git workflows
  - Tools: Read, Edit, Write, Bash(git:*)
  - Purpose: Standardize repository organization
  - Location: Project-specific (.claude/agents/)
  - Main rule: Always require a README.md file with project description in root directory
```

**Uso efectivo de subagentes**:
```
# Verificar subagentes creados
> /agents

# Usar subagentes específicos
> Use the html-css-standards subagent to review my HTML and CSS files
> Have the repo-structure-manager subagent organize our project structure

# Encadenamiento avanzado
> First use the html-css-standards subagent to review our files, then have the repo-structure-manager subagent create proper documentation and organize the project
```

#### 🔄 Lab 4: Debugging y Mejoras (20 min)

**Ejemplo de debugging**:
```html
<!-- Archivo con errores básicos -->
<!DOCTYPE html>
<html>
<head>
  <title>Workshop</title>
  <!-- Bug 1: No responsive viewport -->
  <style>
    body { margin: 0; }
    .header { width: 800px; } /* Bug: Fixed width */
    .text { color: #ccc; background: white; } /* Bug: Poor contrast */
  </style>
</head>
<body>
  <div class="header">
    <h1>Claude Code Workshop</h1>
    <p class="text">Learn to code with AI</p>
  </div>
</body>
</html>
```

**Proceso de debugging**:
```
> Debug this simple HTML file and fix these issues:
  1. Make it responsive for mobile
  2. Fix color contrast problems
  3. Add missing meta tags
  4. Improve basic accessibility
```

---

### **MÓDULO 4: Integraciones y Despliegue (30 min)**

#### 🤖 Lab 5: Crear Servidor MCP Weather (15 min)

**Objetivo: Crear exactamente el mismo servidor MCP weather siguiendo la guía oficial**

Vamos a seguir la guía oficial: https://modelcontextprotocol.io/docs/develop/build-server

**Paso 1: Crear el proyecto**

```bash
# Crear directorio del proyecto weather
uv init weather
cd weather

# Crear entorno virtual y activarlo
uv venv
.venv\Scripts\activate  # En Windows
# source .venv/bin/activate  # En Linux/Mac

# Instalar dependencias
uv add mcp[cli] httpx

# Crear archivo del servidor
new-item weather.py  # En Windows
# touch weather.py    # En Linux/Mac
```

**Paso 2: Crear el archivo weather.py**

```python
import asyncio
import logging
from mcp.server.models import InitializationOptions
from mcp.server import NotificationOptions, Server
from mcp.types import Resource, Tool, TextContent, ImageContent, EmbeddedResource
import mcp.types as types
import httpx

# Set up logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger("weather-server")

# Create a server instance
server = Server("weather-server")

# National Weather Service API base URL
NWS_API_BASE = "https://api.weather.gov"

async def get_forecast(latitude: float, longitude: float) -> dict:
    """Get forecast for a given latitude and longitude."""
    async with httpx.AsyncClient() as client:
        # First, get the grid point
        points_url = f"{NWS_API_BASE}/points/{latitude},{longitude}"
        points_response = await client.get(points_url)
        points_response.raise_for_status()
        points_data = points_response.json()
        
        # Get the forecast URL
        forecast_url = points_data["properties"]["forecast"]
        forecast_response = await client.get(forecast_url)
        forecast_response.raise_for_status()
        
        return forecast_response.json()

async def get_alerts(state: str) -> dict:
    """Get weather alerts for a given state."""
    async with httpx.AsyncClient() as client:
        alerts_url = f"{NWS_API_BASE}/alerts"
        params = {"area": state}
        alerts_response = await client.get(alerts_url, params=params)
        alerts_response.raise_for_status()
        
        return alerts_response.json()

@server.list_tools()
async def handle_list_tools() -> list[types.Tool]:
    """
    List available tools.
    Each tool specifies its arguments using JSON Schema validation.
    """
    return [
        types.Tool(
            name="get_forecast",
            description="Get weather forecast for a location",
            inputSchema={
                "type": "object",
                "properties": {
                    "latitude": {
                        "type": "number",
                        "description": "Latitude of the location"
                    },
                    "longitude": {
                        "type": "number", 
                        "description": "Longitude of the location"
                    }
                },
                "required": ["latitude", "longitude"]
            }
        ),
        types.Tool(
            name="get_alerts",
            description="Get weather alerts for a state",
            inputSchema={
                "type": "object",
                "properties": {
                    "state": {
                        "type": "string",
                        "description": "Two-letter state code (e.g., CA, NY)"
                    }
                },
                "required": ["state"]
            }
        )
    ]

@server.call_tool()
async def handle_call_tool(name: str, arguments: dict) -> list[types.TextContent]:
    """
    Handle tool calls.
    Tools can modify server state and notify clients of changes.
    """
    if name == "get_forecast":
        latitude = arguments.get("latitude")
        longitude = arguments.get("longitude")
        
        try:
            forecast_data = await get_forecast(latitude, longitude)
            periods = forecast_data["properties"]["periods"]
            
            forecast_text = f"Weather forecast for {latitude}, {longitude}:\n\n"
            for period in periods[:5]:  # Show next 5 periods
                forecast_text += f"{period['name']}: {period['detailedForecast']}\n\n"
                
            return [types.TextContent(
                type="text",
                text=forecast_text
            )]
            
        except Exception as e:
            return [types.TextContent(
                type="text", 
                text=f"Error getting forecast: {str(e)}"
            )]
            
    elif name == "get_alerts":
        state = arguments.get("state")
        
        try:
            alerts_data = await get_alerts(state)
            features = alerts_data.get("features", [])
            
            if not features:
                return [types.TextContent(
                    type="text",
                    text=f"No active weather alerts for {state}"
                )]
            
            alerts_text = f"Active weather alerts for {state}:\n\n"
            for alert in features:
                properties = alert["properties"]
                alerts_text += f"• {properties['headline']}\n"
                alerts_text += f"  Area: {properties.get('areaDesc', 'N/A')}\n"
                alerts_text += f"  Severity: {properties.get('severity', 'N/A')}\n\n"
                
            return [types.TextContent(
                type="text",
                text=alerts_text
            )]
            
        except Exception as e:
            return [types.TextContent(
                type="text",
                text=f"Error getting alerts: {str(e)}"
            )]
            
    else:
        raise ValueError(f"Unknown tool: {name}")

async def main():
    # Run the server using stdin/stdout streams
    from mcp.server.stdio import stdio_server
    
    async with stdio_server() as (read_stream, write_stream):
        await server.run(
            read_stream,
            write_stream,
            InitializationOptions(
                server_name="weather-server",
                server_version="1.0.0",
                capabilities=server.get_capabilities(
                    notification_options=NotificationOptions(),
                    experimental_capabilities={},
                ),
            ),
        )

if __name__ == "__main__":
    asyncio.run(main())
```

**Paso 3: Configurar en Claude Desktop**

Agregar al archivo de configuración MCP:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "C:\\Users\\Gustavo Gamboa\\Documents\\claude-code-workshop\\claude-workshop-v2\\claude-workshop\\dalia-claude-code-workshop\\weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

**Paso 4: Probar el servidor**

```bash
# Activar el entorno virtual si no está activo
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Linux/Mac

# Probar el servidor directamente
uv run python weather.py

# Reiniciar Claude Desktop
# Ir a Settings > Developer > Local MCP servers
# Verificar que aparece "weather" en la lista
```

**Demostración práctica:**

Una vez configurado, puedes probar en Claude Desktop:

```
# Obtener pronóstico del tiempo
> What's the weather forecast for Sacramento? (Latitude: 38.5816, Longitude: -121.4944)

# Obtener alertas meteorológicas
> Are there any weather alerts for California? (State code: CA)

# Comparar diferentes ubicaciones
> Compare the weather forecast between Sacramento and New York (40.7128, -74.0060)
```

**Verificar funcionamiento:**

En Claude Desktop deberías ver:
- Servidor "weather" listado en Local MCP servers
- Estado "Connected" 
- Respuestas con información meteorológica real
- Ícono "W" para herramientas weather en las conversaciones

**Casos de uso para el workshop:**

```
# Demostrar herramientas con parámetros
> Get weather forecast for the workshop location

# Mostrar manejo de errores
> Try to get alerts for an invalid state code

# Combinar múltiples herramientas  
> Get both forecast and alerts for Texas (Latitude: 31.9686, Longitude: -99.9018, State: TX)
```

**Casos de Uso Útiles para Desarrolladores**

Una vez que tengas el servidor MCP weather funcionando, aquí algunos casos de uso prácticos que puedes implementar en tu trabajo diario como desarrollador:

**1. Integración en aplicaciones**:
```
# Verificar condiciones antes de despliegues
> Check weather conditions for our data center locations before deploying

# Planificación de releases
> What's the weather forecast for the next 3 days in our main office locations?
```

**2. Automatización de workflows**:
```
# Alertas para equipos remotos
> Get weather alerts for all states where our remote team members are located

# Decisiones de infraestructura
> Check if there are any severe weather alerts that might affect our AWS regions
```

**3. Desarrollo de features relacionadas con clima**:
```
# Testing con datos reales
> Get current weather data for testing our location-based features

# Validación de APIs
> Compare our weather data with NWS official forecasts for accuracy testing
```

**4. Integración con otras herramientas**:
- Combinar con calendarios para planificar eventos outdoor
- Integrar con sistemas de monitoreo para correlacionar clima con performance
- Usar en chatbots internos para respuestas contextuales

#### 🚀 Lab 6: Despliegue con Amplify (15 min)

**Crear configuración de deployment**:
```yaml
# amplify.yml - Configuración básica
version: 1
frontend:
  phases:
    build:
      commands:
        - echo "Building simple website..."
  artifacts:
    baseDirectory: /
    files:
      - '**/*'
```

**GitHub Action básica**:
```yaml
# .github/workflows/deploy.yml
name: Deploy to Amplify
on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Deploy to Amplify
        run: echo "Deploying simple website to AWS Amplify"
```

---

## Recursos Continuos

**Repositorio del Workshop**:
```
dalia-claude-code-workshop/
├── index.html              # Página principal simple
├── style.css               # Estilos básicos
├── amplify.yml             # Configuración Amplify
├── .claude/
│   ├── agents/             # Subagentes del proyecto
│   └── commands/           # Comandos personalizados
├── .github/workflows/      # CI/CD básico
├── README.md               # Instrucciones
├── weather/                # Proyecto MCP Weather
│   ├── weather.py          # Servidor MCP
│   └── .venv/              # Entorno virtual
└── docs/setup-guide.md     # Guía de setup
```

**Community y Soporte**:
- Discord: Claude Developers
- GitHub Discussions
- Weekly office hours
- Documentación oficial: https://docs.anthropic.com/en/docs/claude-code
- Documentación uv: https://docs.astral.sh/uv/

