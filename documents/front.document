# Comprehensive Code Documentation & JSDoc Generation Prompt

You are a Senior Software Architect, Technical Writer, and Staff Software Engineer.

Analyze the entire codebase and generate comprehensive code-level documentation without changing business logic.

## Objectives

1. Add complete JSDoc comments to:
   - Controllers
   - Services
   - Repositories
   - Use Cases
   - Guards
   - Strategies
   - Interceptors
   - Filters
   - Pipes
   - DTOs
   - Entities
   - Interfaces
   - Enums
   - Utility functions
   - Middleware
   - Modules
   - Event Handlers
   - Queue Consumers/Producers
   - Authentication and Authorization components
   - Custom Decorators
   - Configuration files

2. Generate documentation for:
   - Classes
   - Methods
   - Functions
   - Properties
   - Constants
   - Types
   - Interfaces
   - Enums

3. Explain:
   - Purpose
   - Responsibilities
   - Inputs
   - Outputs
   - Side effects
   - Security considerations
   - Error handling behavior
   - Dependencies
   - Usage examples

---

## JSDoc Standards

### Class Documentation

```typescript
/**
 * Manages user authentication and authorization operations.
 *
 * Responsibilities:
 * - User login
 * - User logout
 * - Password management
 * - Token validation
 *
 * Dependencies:
 * - UsersService
 * - JwtService
 * - KeycloakService
 *
 * Security:
 * - Validates credentials
 * - Prevents unauthorized access
 * - Uses secure token validation
 */
```

### Method Documentation

```typescript
/**
 * Authenticates a user and issues access credentials.
 *
 * @param loginDto User login credentials.
 * @returns Authenticated user session information.
 *
 * @throws UnauthorizedException
 * Thrown when credentials are invalid.
 *
 * @throws ForbiddenException
 * Thrown when user account is disabled.
 *
 * @example
 * const result = await authService.login({
 *   username: 'john',
 *   password: 'secret'
 * });
 */
```

### Property Documentation

```typescript
/**
 * Maximum number of login attempts allowed.
 */
private readonly maxLoginAttempts: number;
```

### Interface Documentation

```typescript
/**
 * Represents authenticated user information.
 */
export interface AuthUser {
  id: string;
  username: string;
  roles: string[];
}
```

### DTO Documentation

```typescript
/**
 * Login request payload.
 *
 * Validation Rules:
 * - username is required
 * - password is required
 */
export class LoginDto {}
```

---

## Authentication & Authorization Documentation

For all authentication and authorization components document:

### Guards

Explain:

- Purpose
- Access control logic
- Required permissions
- Required roles
- Authentication flow
- Failure scenarios

Example:

```typescript
/**
 * Ensures the current user possesses required roles.
 *
 * Authorization Flow:
 * 1. Extract JWT claims.
 * 2. Read required roles metadata.
 * 3. Compare user roles.
 * 4. Grant or deny access.
 *
 * Security:
 * Prevents privilege escalation.
 */
```

### Strategies

Document:

- Authentication mechanism
- Token validation process
- Identity provider integration
- Security assumptions

### Decorators

Document:

- Purpose
- Usage
- Expected behavior

### Permissions

Document:

- Permission model
- Role hierarchy
- Access matrix

---

## Controller Documentation

For every controller:

Document:

- Endpoint purpose
- Request flow
- Security requirements
- Validation process
- Response structure

Example:

```typescript
/**
 * User Management API.
 *
 * Provides endpoints for:
 * - User creation
 * - User updates
 * - User deletion
 * - User retrieval
 *
 * Authorization:
 * Admin only.
 */
```

---

## Service Documentation

For every service:

Document:

- Business responsibility
- Domain rules
- External dependencies
- Transactions
- Side effects

---

## Module Documentation

For every module:

Document:

- Purpose
- Exported providers
- Imported modules
- Architectural role

Example:

```typescript
/**
 * Authentication Module.
 *
 * Provides:
 * - Authentication services
 * - JWT validation
 * - Authorization guards
 *
 * Imports:
 * - UsersModule
 * - ConfigModule
 *
 * Exports:
 * - AuthService
 */
```

---

## Error Handling Documentation

Document:

- Expected exceptions
- Failure scenarios
- Recovery behavior
- Retry mechanisms

Use:

```typescript
@throws BadRequestException
@throws UnauthorizedException
@throws ForbiddenException
@throws NotFoundException
@throws ConflictException
@throws InternalServerErrorException
```

---

## Security Documentation

For security-sensitive code document:

- Authentication requirements
- Authorization requirements
- Data protection considerations
- Sensitive data handling
- Input validation
- Injection prevention
- Audit logging requirements

Example:

```typescript
/**
 * Security Notes:
 * - Never logs passwords.
 * - Validates JWT signatures.
 * - Prevents privilege escalation.
 * - Sanitizes user input.
 */
```

---

## Output Requirements

1. Add missing JSDoc comments.
2. Improve existing comments.
3. Do not modify business logic.
4. Preserve formatting conventions.
5. Use professional English.
6. Follow TypeScript JSDoc standards.
7. Ensure all public APIs are documented.
8. Ensure all authentication and authorization flows are documented.
9. Ensure every controller, service, guard, strategy, decorator, module, DTO, entity, and interface has documentation.
10. Generate documentation coverage report at the end containing:
    - Total files analyzed
    - Files documented
    - Missing documentation
    - Documentation coverage percentage
    - Security-sensitive components identified
    - Authentication components identified
    - Authorization components identified

```

```
