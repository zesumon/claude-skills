# Database Command

Analyze, optimize, and manage database schemas, queries, and migrations.

## Usage

```
/database [action] [target]
```

## Actions

- `analyze` - Analyze schema design and suggest improvements
- `optimize` - Optimize slow queries and indexes
- `migrate` - Generate migration scripts
- `seed` - Create seed data scripts
- `diagram` - Generate ER diagram description

## What This Command Does

1. **Schema Analysis**
   - Reviews table structure and relationships
   - Identifies missing indexes
   - Flags normalization issues
   - Checks for proper foreign key constraints

2. **Query Optimization**
   - Identifies N+1 query problems
   - Suggests index additions or removals
   - Rewrites inefficient queries
   - Analyzes execution plans

3. **Migration Generation**
   - Creates up/down migration scripts
   - Handles data transformations safely
   - Ensures zero-downtime migration patterns

4. **Security Review**
   - Checks for SQL injection vulnerabilities
   - Reviews access control on sensitive tables
   - Validates input sanitization

## Examples

```
/database analyze models/user.py
/database optimize --slow-queries
/database migrate add_index_to_orders
/database seed --env development
```

## Output Format

Provides:
- Current state assessment
- Specific issues found with severity levels
- Recommended SQL or ORM changes
- Migration scripts ready to apply
- Performance impact estimates
