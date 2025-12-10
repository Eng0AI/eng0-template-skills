# eng0-template-skills

Centralized repository for all eng0 platform template skills. Each template has its own directory with specialized skills for setup and deployment.

## Directory Structure

```
eng0-template-skills/
├── [template-id]/
│   ├── build-and-deploy/
│   │   └── SKILL.md       # Deployment instructions
│   └── setup/
│       └── SKILL.md       # Project setup from scratch
├── README.md
```

## Available Templates

| Template ID | Name | Category | Skills |
|-------------|------|----------|--------|
| award-winning-website | Gaming Landing Page | landing | setup, build-and-deploy |
| awwwards-landing-page | Designer Portfolio | landing, portfolio | setup, build-and-deploy |
| gsap-awwwards-website | SPYLT Product Landing | landing | setup, build-and-deploy |
| natural-language-postgres | Chat App On Your Data | ai | setup |
| natural-language-postgres-presentation | Presentation On Your Data | ai, slides | setup |
| happiness-dashboard | Dashboard App | ai | setup, build-and-deploy |
| langchain-agent | LangChain Agent | ai | setup |
| langchain-retrieval | LangChain Retrieval | ai | setup |
| langchain-retrieval-agent | LangChain Retrieval Agent | ai | setup |
| ai-chatbot | AI Chatbot (Chat SDK) | ai | setup, build-and-deploy |
| nextjs-blog-netlify | Next.js Blog (Netlify) | blog | setup |
| gatsby-ecommerce-netlify | Gatsby E-commerce | starter | setup |
| tanstack-chat-netlify | TanStack Chat | starter | setup |
| content-ops-netlify | Content Ops Starter | blog | setup |
| dillion-portfolio | Developer Portfolio | portfolio | setup, build-and-deploy |
| nuxt-starter-netlify | Nuxt Starter | starter | setup |
| astro-supabase-netlify | Astro + Supabase | starter | setup |
| nextjs-supabase | Next.js + Supabase | starter | setup |
| fastapi-fullstack | FastAPI Full Stack | backend | setup |
| express-mcp | Express MCP Server | tools | setup |
| express-typescript-starter | Express TypeScript Starter | backend | setup |
| fastapi-backend-template | FastAPI Backend | backend | setup |
| nestjs-typescript-starter | NestJS TypeScript Starter | backend | setup |
| deno-monorepo-template | Deno Monorepo API | backend | setup |
| axum-rust-template | Axum Rust API | backend | setup |
| go-backend-clean-architecture | Go Clean Architecture | backend | setup |
| chrome-extension-boilerplate-react-vite | Chrome Extension Boilerplate | tools | setup |
| vite-react | React + Vite | starter | setup, build-and-deploy |
| vite-vue | Vue + Vite | starter | setup, build-and-deploy |
| screwfast | ScrewFast Landing Page | landing, blog | setup, build-and-deploy |
| mantis-react-admin | Mantis React Admin | dashboard | setup, build-and-deploy |
| tailadmin-nextjs | TailAdmin Dashboard | dashboard | setup, build-and-deploy |
| astrowind | AstroWind Landing Page | landing, blog | setup, build-and-deploy |
| magic-portfolio | Magic Portfolio | portfolio | setup, build-and-deploy |
| denuvo-slides | Denuvo Reverse Engineering Slides | slides | setup, build-and-deploy |
| ncine-presentation | nCine Game Framework Slides | slides | setup, build-and-deploy |
| py-intro | Python Zero To Hero Slides | slides | setup, build-and-deploy |
| kubecon-llm-k8s | KubeCon LLM K8s Slides | slides | setup, build-and-deploy |
| developer-portfolio | Developer Portfolio Pro | portfolio | setup, build-and-deploy |
| stripe-one-time-payment | Stripe One-Time Payment | payments | setup, build-and-deploy |
| stripe-subscription | Stripe Subscription | payments, saas | setup, build-and-deploy |

## Skills

### setup

The `setup` skill initializes a template in an empty project directory:

1. Clones the template repository
2. Installs dependencies
3. Configures environment (if needed)
4. Verifies the setup with a build

**Usage:** When starting a new project from a template, invoke the `setup` skill to bootstrap the entire project.

### build-and-deploy

The `build-and-deploy` skill handles production deployment:

1. Builds the project for production
2. Deploys to Vercel or Netlify
3. Handles environment variables
4. Database migrations (if applicable)

**Usage:** After developing your project, invoke the `build-and-deploy` skill to deploy to production.

## Usage with Claude Code

Skills are automatically available in Claude Code. Simply describe what you want to do:

- "Set up the vite-react template in this directory"
- "Deploy this project to Vercel"
- "Initialize the ai-chatbot template here"

## Usage with Other Code Agents

For other code agents (Cursor, Windsurf, Cline, etc.):

1. Navigate to the template directory: `eng0-template-skills/[template-id]/`
2. Read the relevant skill file: `setup/SKILL.md` or `build-and-deploy/SKILL.md`
3. Follow the step-by-step instructions

## Template Registry

The authoritative list of templates is maintained in:
`cctools/relay/src/data/project-templates.json`

## Contributing

To add a new template skill:

1. Create a directory with the template ID
2. Add `setup/SKILL.md` with initialization instructions
3. Add `build-and-deploy/SKILL.md` with deployment instructions (if applicable)
4. Update this README with the new template
