# API Design & Generation

Design, generate, and document REST or GraphQL APIs for your project.

## Usage

```
/code/api [target] [options]
```

## Arguments

- `target` - File, module, or description of the API to create/improve
- `options` - Additional flags (see below)

## Options

- `--rest` - Generate RESTful API endpoints (default)
- `--graphql` - Generate GraphQL schema and resolvers
- `--openapi` - Output OpenAPI/Swagger spec
- `--crud` - Generate full CRUD operations for a resource
- `--auth` - Include authentication middleware
- `--validate` - Add request validation logic

## What This Does

1. **Analyzes** existing code structure, models, and data schemas
2. **Designs** consistent API endpoints following REST conventions or GraphQL best practices
3. **Generates** route handlers, controllers, and middleware
4. **Adds validation** for request bodies, params, and query strings
5. **Documents** endpoints with inline comments and OpenAPI annotations
6. **Suggests** error handling patterns and status codes
7. **Reviews** for security issues like missing auth, rate limiting, input sanitization

## Examples

```
/code/api src/models/User.js --crud --auth
```
Generates full CRUD REST endpoints for the User model with auth middleware.

```
/code/api "orders management system" --graphql --validate
```
Designs a GraphQL schema for orders with input validation.

```
/code/api src/routes/ --openapi
```
Scans existing routes and outputs an OpenAPI 3.0 specification.

## Output

- Generated route/resolver files
- Request/response type definitions
- Validation schemas (Zod, Joi, or Yup depending on project)
- OpenAPI spec (if `--openapi` flag used)
- Summary of endpoints created with HTTP methods and paths

## Notes

- Follows existing project conventions and framework patterns
- Detects Express, Fastify, Django, FastAPI, etc. automatically
- Keeps generated code consistent with your current auth strategy
- Flags any endpoints that may need additional rate limiting or caching
