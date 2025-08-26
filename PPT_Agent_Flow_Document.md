# PPT Agent Flow Document - Suno Project

## Table of Contents
- [Overview](#overview)
- [Current State](#current-state)
- [Architecture Overview](#architecture-overview)
- [Agent Flow Sequence](#agent-flow-sequence)
- [Core Components](#core-components)
- [Tool Integration](#tool-integration)
- [Canvas Creation Process](#canvas-creation-process)
- [File Management](#file-management)
- [Workflow Execution](#workflow-execution)
- [Frontend Integration](#frontend-integration)
- [Implementation Requirements](#implementation-requirements)

---

## Overview

The PPT Agent concept in the Suno project is a **planned specialized AI agent** designed to create presentations and slide decks based on user prompts. Currently, it exists as a UI placeholder in the dashboard, but the actual implementation would leverage the Kortix platform's generalist AI capabilities to generate HTML-based presentations that can be rendered in a canvas environment.

**Key Features (Planned):**
- HTML-based presentation generation
- Canvas rendering for visual display
- File management and organization
- Workflow automation
- Real-time preview capabilities

---

## Current State

### ⚠️ Important: Slides Agent is Not Yet Implemented

The "Slides Agent" currently exists only as a **UI placeholder** in the frontend dashboard. Here's what actually exists:

#### 1. Frontend UI Placeholder
**Location:** `frontend/src/components/dashboard/custom-agents-section.tsx`

```typescript
// This is just a UI configuration - no backend implementation
{
  id: 'slides-agent',
  name: 'Slides Agent',
  description: 'Build beautiful presentations and slide decks',
  emoji: '📽️',
  color: '#3b82f6',
  comingSoon: false  // Misleading - it's not actually implemented
}
```

#### 2. What Actually Exists in the Codebase
- **General file creation tools** (`backend/agent/tools/sb_files_tool.py`)
- **Browser automation tools** (`backend/agent/tools/sb_browser_tool.py`)
- **Task management tools** (`backend/agent/tools/task_list_tool.py`)
- **HTML rendering capabilities** (`frontend/src/components/thread/preview-renderers/html-renderer.tsx`)
- **General agent framework** that could be configured for presentations

#### 3. What's Missing
- No `slides-agent` configuration in the database
- No specialized presentation creation logic
- No presentation templates or design systems
- No agent-specific system prompts for presentation creation

---

## Architecture Overview

The PPT Agent would operate within the Kortix platform architecture (when implemented):

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │   Backend API   │    │   Agent Runtime │
│   Dashboard     │◄──►│   (FastAPI)     │◄──►│   (Docker)      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Canvas        │    │   Database      │    │   File System   │
│   Renderer      │    │   (Supabase)    │    │   (Sandbox)     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

---

## Agent Flow Sequence

### 1. User Prompt Processing (Current State)
**Location:** `frontend/src/components/dashboard/custom-agents-section.tsx`

```typescript
// Currently just a UI configuration
{
  id: 'slides-agent',
  name: 'Slides Agent',
  description: 'Build beautiful presentations and slide decks',
  emoji: '📽️',
  color: '#3b82f6',
  comingSoon: false
}
```

**Current Flow:**
1. User selects "Slides Agent" from dashboard
2. Agent ID (`slides-agent`) is passed to backend
3. **Currently fails** - no agent configuration exists

### 2. Agent Initialization (Would Need Implementation)
**Location:** `backend/agent/api.py`

The current agent initialization code exists but would need:

```python
@router.post("/agent/initiate")
async def initiate_agent_with_files(
    prompt: str = Form(...),
    agent_id: Optional[str] = Form(None),
    # ... other parameters
):
    # Would need slides-agent configuration in database
    agent_config = await load_agent_config(agent_id)  # Currently returns None for slides-agent
    
    # Create project and sandbox
    project = await create_project(account_id, placeholder_name)
    sandbox = await create_sandbox_if_needed(files)
    
    # Start agent execution
    run_agent_background.send(
        agent_run_id=agent_run_id,
        thread_id=thread_id,
        agent_config=agent_config
    )
```

### 3. Tool Execution (Existing Tools)
**Location:** `backend/agent/tools/`

The existing tools that could be used for presentation creation:

#### File Management Tool
**File:** `backend/agent/tools/sb_files_tool.py`

```python
@openapi_schema({
    "name": "create_file",
    "description": "Create a new file with content"
})
async def create_file(self, file_path: str, file_contents: str) -> ToolResult:
    # Can create HTML, CSS, JS files for presentations
    # Currently general-purpose, not presentation-specific
```

#### Browser Tool
**File:** `backend/agent/tools/sb_browser_tool.py`

```python
@openapi_schema({
    "name": "navigate_to",
    "description": "Navigate to a URL"
})
async def navigate_to(self, url: str) -> ToolResult:
    # Can be used for research and content gathering
    # Currently general-purpose
```

#### Task Management Tool
**File:** `backend/agent/tools/task_list_tool.py`

```python
@openapi_schema({
    "name": "create_tasks",
    "description": "Create structured task list"
})
async def create_tasks(self, sections: List[Dict]) -> ToolResult:
    # Can organize presentation creation into tasks
    # Currently general-purpose
```

### 4. Presentation Generation Process (Would Need Implementation)

The following steps would need to be implemented as part of the agent's system prompt and logic:

#### Step 1: Research and Content Gathering
```python
# Would be implemented in agent's system prompt
# Agent would use existing browser and search tools
await browser_tool.navigate_to("https://example.com/research")
await browser_tool.extract_text(selector=".content")
await web_search_tool.search(query="presentation topic")
```

#### Step 2: Content Structure Creation
```python
# Would be implemented in agent's system prompt
tasks = [
    {
        "title": "Presentation Setup",
        "tasks": [
            "Create HTML structure",
            "Design CSS styling", 
            "Add JavaScript functionality"
        ]
    },
    {
        "title": "Content Creation",
        "tasks": [
            "Research topic",
            "Create slide content",
            "Add visual elements"
        ]
    }
]
```

#### Step 3: HTML Presentation Creation (Would Need Templates)
```python
# Would need to be implemented with presentation templates
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Generated Presentation</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="presentation-container">
        <div class="slide active" id="slide-1">
            <h1>Slide Title</h1>
            <p>Slide content...</p>
        </div>
        <!-- Additional slides -->
    </div>
    <script src="script.js"></script>
</body>
</html>
"""

await files_tool.create_file("presentation.html", html_content)
```

#### Step 4: CSS Styling (Would Need Design System)
```python
# Would need to be implemented with presentation design system
css_content = """
.presentation-container {
    width: 100%;
    height: 100vh;
    position: relative;
    overflow: hidden;
}

.slide {
    position: absolute;
    width: 100%;
    height: 100%;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.slide.active {
    opacity: 1;
}
"""

await files_tool.create_file("style.css", css_content)
```

#### Step 5: JavaScript Functionality (Would Need Implementation)
```python
# Would need to be implemented with presentation navigation
js_content = """
// Presentation navigation
let currentSlide = 0;
const slides = document.querySelectorAll('.slide');

function showSlide(index) {
    slides.forEach(slide => slide.classList.remove('active'));
    slides[index].classList.add('active');
}

// Keyboard navigation
document.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight' && currentSlide < slides.length - 1) {
        currentSlide++;
        showSlide(currentSlide);
    } else if (e.key === 'ArrowLeft' && currentSlide > 0) {
        currentSlide--;
        showSlide(currentSlide);
    }
});
"""

await files_tool.create_file("script.js", js_content)
```

---

## Canvas Creation Process

### 1. HTML Renderer Component (Exists)
**Location:** `frontend/src/components/thread/preview-renderers/html-renderer.tsx`

```typescript
export function HtmlRenderer({
    content,
    previewUrl,
    className,
    project
}: HtmlRendererProps) {
    const [viewMode, setViewMode] = useState<'preview' | 'code'>('preview');
    
    return (
        <div className="w-full h-full flex flex-col">
            <div className="flex-1 min-h-0 relative">
                {viewMode === 'preview' ? (
                    <iframe
                        src={htmlPreviewUrl}
                        title="HTML Preview"
                        className="w-full h-full border-0"
                        sandbox="allow-same-origin allow-scripts"
                        style={{ background: 'white' }}
                    />
                ) : (
                    <ScrollArea className="w-full h-full">
                        <pre className="p-4 overflow-auto">
                            <code className="text-sm">{content}</code>
                        </pre>
                    </ScrollArea>
                )}
            </div>
        </div>
    );
}
```

### 2. File Renderer Integration (Exists)
**Location:** `frontend/src/components/file-renderers/index.tsx`

```typescript
export function FileRenderer({
    content,
    binaryUrl,
    fileName,
    className,
    project,
    markdownRef,
    onDownload,
    isDownloading,
}: FileRendererProps) {
    const fileType = getFileType(fileName);
    const isHtmlFile = fileName?.toLowerCase().endsWith('.html');
    
    return (
        <div className="w-full h-full">
            {isHtmlFile ? (
                <HtmlRenderer
                    content={content || ''}
                    previewUrl={htmlPreviewUrl || ''}
                    className="w-full h-full"
                />
            ) : (
                // Other file type renderers
            )}
        </div>
    );
}
```

### 3. Canvas Rendering Process (Exists)

1. **File Detection:** System detects HTML files in the project
2. **URL Generation:** Creates preview URLs for HTML files
3. **Iframe Rendering:** HTML presentations are rendered in iframe canvas
4. **Interactive Features:** JavaScript functionality works within sandbox
5. **Responsive Design:** Canvas adapts to different screen sizes

---

## File Management

### 1. File Upload and Processing (Exists)
**Location:** `backend/knowledge_base/file_processor.py`

```python
class FileProcessor:
    SUPPORTED_DOCUMENT_EXTENSIONS = {
        '.pdf', '.docx', '.html', '.css', '.js'
    }
    
    async def process_file_upload(
        self, 
        agent_id: str, 
        account_id: str, 
        file_content: bytes, 
        filename: str, 
        mime_type: str
    ) -> Dict[str, Any]:
        # Process uploaded files for presentation creation
        # Extract content from various file formats
        # Store in database for agent access
```

### 2. File Type Support (Exists)
**Location:** `frontend/src/hooks/use-cached-file.ts`

```typescript
const isOfficeFile = filePath?.toLowerCase().match(/\.(xlsx|xls|docx|doc|pptx|ppt)$/);

// MIME type mapping
const mimeTypes = {
    'pptx': 'application/vnd.openxmlformats-officedocument.presentationml.presentation',
    'ppt': 'application/vnd.ms-powerpoint',
    'html': 'text/html',
    'css': 'text/css',
    'js': 'application/javascript'
};
```

---

## Workflow Execution

### 1. Workflow Creation (Exists)
**Location:** `backend/agent/tools/agent_builder_tools/workflow_tool.py`

```python
@openapi_schema({
    "name": "create_workflow",
    "description": "Create a new workflow/playbook"
})
async def create_workflow(
    self,
    name: str,
    template: str,
    variables: Optional[List[Dict[str, Any]]] = None,
    description: Optional[str] = None,
    is_default: bool = False,
) -> ToolResult:
    # Creates reusable workflows for presentation creation
    # Templates can include variables like {{topic}}, {{style}}, etc.
```

### 2. Workflow Execution (Exists)
**Location:** `backend/triggers/execution_service.py`

```python
class WorkflowExecutor:
    async def execute_workflow(
        self,
        agent_id: str,
        workflow_id: str,
        workflow_input: Dict[str, Any],
        trigger_result: TriggerResult,
        trigger_event: TriggerEvent
    ) -> Dict[str, Any]:
        # Executes presentation creation workflows
        # Handles variable substitution
        # Manages execution state
```

### 3. Frontend Workflow Builder (Exists)
**Location:** `frontend/src/app/(dashboard)/agents/config/[agentId]/workflow/[workflowId]/page.tsx`

```typescript
export default function WorkflowPage() {
    const [steps, setSteps] = useState<ConditionalStep[]>([]);
    
    const handleSave = async () => {
        const payloadSteps = convertToNestedJSON(steps);
        
        if (isEditing) {
            await updateWorkflowMutation.mutateAsync({
                workflowId,
                name: workflowName,
                steps: payloadSteps
            });
        } else {
            await createWorkflowMutation.mutateAsync({
                agentId,
                name: workflowName,
                steps: payloadSteps
            });
        }
    };
}
```

---

## Frontend Integration

### 1. Dashboard Integration (Exists)
**Location:** `frontend/src/components/dashboard/custom-agents-section.tsx`

```typescript
const CUSTOM_AGENTS: CustomAgent[] = [
    {
        id: 'slides-agent',
        name: 'Slides Agent',
        description: 'Build beautiful presentations and slide decks',
        emoji: '📽️',
        color: '#3b82f6',
        comingSoon: false
    }
];
```

### 2. Thread Management (Exists)
**Location:** `frontend/src/components/thread/`

- **Message Display:** Shows agent responses and file attachments
- **File Preview:** Renders HTML presentations in canvas
- **Tool Execution:** Displays tool calls and results
- **Progress Tracking:** Shows task completion status

### 3. File Viewer Modal (Exists)
**Location:** `frontend/src/components/thread/file-viewer-modal.tsx`

```typescript
const isOfficeFile = ['xlsx', 'xls', 'docx', 'doc', 'pptx', 'ppt'].includes(extension || '');

// Handles presentation file viewing
// Supports both preview and download modes
```

---

## Implementation Requirements

To actually implement the PPT Agent, the following would need to be built:

### 1. Database Configuration
- Create `slides-agent` configuration in the agents table
- Configure system prompt for presentation creation
- Set up agent-specific tools and workflows

### 2. Agent System Prompt
- Specialized instructions for presentation creation
- Templates for different presentation types
- Design guidelines and best practices

### 3. Presentation Templates
- HTML templates for different slide layouts
- CSS frameworks for various presentation styles
- JavaScript libraries for navigation and interactions

### 4. Content Generation Logic
- Research and content gathering strategies
- Slide structure and organization
- Visual element integration

### 5. Design System
- Typography and color schemes
- Layout templates
- Animation and transition effects

---

## Complete Flow Summary

**Current State:**
1. **User Input:** User selects Slides Agent from dashboard
2. **Agent Initialization:** Currently fails - no agent configuration exists
3. **Tool Execution:** Would use existing general-purpose tools
4. **File Generation:** Would create HTML, CSS, and JS files using existing tools
5. **Canvas Rendering:** Frontend can render HTML presentations in iframe canvas
6. **Interactive Features:** JavaScript functionality works within sandbox
7. **File Management:** Generated files are stored and accessible for download
8. **Workflow Automation:** Reusable workflows can be created for similar presentations

**What's Missing:**
- Agent configuration and system prompt
- Presentation-specific templates and design system
- Specialized content generation logic
- Agent-specific workflows and tools

---

## Quick Reference Links

- [Agent API Endpoints](./backend/agent/api.py)
- [File Management Tools](./backend/agent/tools/sb_files_tool.py)
- [Browser Automation](./backend/agent/tools/sb_browser_tool.py)
- [Task Management](./backend/agent/tools/task_list_tool.py)
- [Workflow Builder](./backend/agent/tools/agent_builder_tools/workflow_tool.py)
- [HTML Renderer](./frontend/src/components/thread/preview-renderers/html-renderer.tsx)
- [File Renderer](./frontend/src/components/file-renderers/index.tsx)
- [Dashboard Integration](./frontend/src/components/dashboard/custom-agents-section.tsx)
- [Workflow Execution](./backend/triggers/execution_service.py)

---

*This document provides a comprehensive overview of the PPT Agent concept in the Suno project. The agent currently exists only as a UI placeholder and would need significant implementation to become functional.*
