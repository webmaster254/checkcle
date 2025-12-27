# Agent Development Guide

## Build/Lint/Test Commands
- **Frontend** (application/): `npm run dev` | `npm run build` | `npm run lint`
- **Backend** (server/): `./pocketbase serve --dir pb_data` (or `--http=0.0.0.0:8090` for non-localhost)
- **Service Operation** (server/service-operation/): `go run main.go` (requires .env config)
- **No test suite found** - add tests with appropriate test runner for your changes

## Code Style Guidelines

### TypeScript/React (Frontend)
- **Imports**: Use `@/` alias for src imports (e.g., `import { pb } from '@/lib/pocketbase'`)
- **Types**: Define interfaces for props/data (TypeScript strict checks disabled: noImplicitAny, strictNullChecks off)
- **Components**: Functional components with hooks (React 18), use shadcn/ui components
- **Naming**: PascalCase for components/types, camelCase for functions/variables
- **Error Handling**: Try-catch with error messages, log suppressed in production (commented console.logs)
- **Formatting**: 2-space indent, single quotes preferred, semicolons required

### Go (Backend Services)
- **Imports**: Group stdlib, external, then local packages
- **Types**: Explicit struct definitions with json tags
- **Naming**: PascalCase for exported, camelCase for unexported
- **Error Handling**: Return errors explicitly, log with `log.Printf`
- **Formatting**: Standard `go fmt`, use goroutines for concurrent monitoring
