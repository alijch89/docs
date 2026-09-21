# Comprehensive Frontend Code Documentation & JSDoc Generation Prompt

You are a Senior Frontend Architect, Staff React Engineer, Next.js Expert, and Technical Writer.

Analyze the entire frontend codebase and add comprehensive, professional, maintainable code-level documentation.

The project is built with:

- Next.js
- React
- TypeScript
- App Router or Pages Router
- REST/API integrations
- Authentication and authorization
- Client-side and/or server-side state management
- Form validation
- Custom hooks
- Reusable UI components

Your primary goal is to improve code understandability, maintainability, onboarding, and architectural clarity WITHOUT changing the application's business logic or behavior.

---

# 1. General Rules

Before modifying anything:

1. Analyze the entire frontend architecture.
2. Identify the responsibility of each directory and module.
3. Identify shared components and feature-specific components.
4. Identify Server Components and Client Components.
5. Identify authentication and authorization mechanisms.
6. Identify API communication layers.
7. Identify state management mechanisms.
8. Identify custom hooks.
9. Identify reusable utilities.
10. Identify route/page/layout structure.
11. Identify forms and validation logic.
12. Identify error/loading/empty states.

Do NOT change:

- Business logic
- API contracts
- Component behavior
- State behavior
- Routing behavior
- Authentication behavior
- Authorization behavior
- Styling behavior
- Existing UX behavior

Only modify code when necessary to add or improve documentation.

---

# 2. Documentation Scope

Add or improve documentation for all relevant:

## React / Next.js Components

Document:

- Pages
- Layouts
- Templates
- Server Components
- Client Components
- Shared UI components
- Feature components
- Compound components
- Form components
- Modal/Dialog components
- Table components
- Navigation components
- Error components
- Loading components
- Empty-state components

Every non-trivial component should explain:

- Purpose
- Responsibility
- Expected props
- State
- Important interactions
- Dependencies
- Rendering behavior
- Server/Client execution context

Example:

```typescript
/**
 * Displays the authenticated user's profile information.
 *
 * Responsibilities:
 * - Displays user information.
 * - Provides access to profile actions.
 * - Handles loading and empty states.
 *
 * Rendering:
 * Client Component.
 *
 * @param props Component configuration and user information.
 *
 * @example
 * <UserProfile user={user} />
 */
```

---

# 3. Server Components vs Client Components

For every important component explicitly document whether it is:

- Server Component
- Client Component

For Client Components explain why client-side execution is required.

Example:

```typescript
/**
 * Client Component.
 *
 * This component requires client-side execution because it:
 * - Uses React state.
 * - Handles browser events.
 * - Accesses browser APIs.
 */
```

For Server Components:

```typescript
/**
 * Server Component.
 *
 * This component executes on the server and does not require
 * client-side JavaScript.
 *
 * Server-side responsibilities:
 * - Fetches initial data.
 * - Performs server-side authorization checks.
 * - Renders the initial UI.
 */
```

Do not add `"use client"` or remove it unless it already exists and the change is strictly required by the existing architecture.

---

# 4. Pages and Routes

For every route/page document:

- Route
- Purpose
- Required authentication
- Required authorization
- Data dependencies
- Server/client execution
- Navigation behavior
- Loading state
- Error state
- Empty state

Example:

```typescript
/**
 * User Dashboard Page.
 *
 * Route:
 * /dashboard
 *
 * Authentication:
 * Requires an authenticated user.
 *
 * Responsibilities:
 * - Loads dashboard data.
 * - Renders dashboard widgets.
 * - Provides navigation to user features.
 *
 * States:
 * - Loading
 * - Error
 * - Empty
 * - Success
 */
```

---

# 5. Layouts

Document:

- Root layout
- Nested layouts
- Authentication layouts
- Dashboard layouts
- Protected layouts
- Shared navigation
- Providers

Explain why each layout exists and what responsibility it owns.

---

# 6. React Hooks

Document every custom hook.

Examples:

- useAuth
- useUser
- useSession
- useApi
- useFetch
- useMutation
- useForm
- useDebounce
- usePagination
- useModal
- usePermissions
- useAuthorization

Example:

```typescript
/**
 * Provides access to the current authenticated user.
 *
 * Responsibilities:
 * - Reads the current authentication state.
 * - Exposes authenticated user information.
 * - Provides authentication status.
 *
 * @returns Authentication state and current user information.
 *
 * @example
 * const { user, isAuthenticated } = useAuth();
 */
```

For each hook document:

- Purpose
- Inputs
- Return value
- State managed
- Side effects
- Dependencies
- Cleanup behavior
- Browser/server restrictions

---

# 7. API / HTTP Layer

Document all:

- API clients
- HTTP clients
- Fetch wrappers
- Axios instances
- API services
- Request helpers
- Response transformers
- Error handlers
- Interceptors

Explain:

- Base URL
- Authentication mechanism
- Headers
- Request flow
- Response handling
- Error handling
- Retry behavior
- Timeout behavior
- Token/session handling

Example:

```typescript
/**
 * HTTP client used for communication with the backend API.
 *
 * Responsibilities:
 * - Sends authenticated API requests.
 * - Applies common HTTP headers.
 * - Normalizes API errors.
 * - Handles authentication failures.
 *
 * Authentication:
 * Uses the application's session mechanism.
 *
 * Security:
 * Sensitive authentication credentials must never be logged.
 */
```

---

# 8. Authentication

Authentication code requires detailed documentation.

Document:

- Login
- Logout
- Registration
- Session management
- Token handling
- Refresh mechanisms
- Authentication context
- Auth hooks
- Auth providers
- Protected routes
- Middleware
- Session expiration
- Unauthorized handling

Explain the complete authentication flow.

For example:

```text
User
  ↓
Login Page
  ↓
Authentication API
  ↓
Backend
  ↓
Session / Token
  ↓
Frontend Authentication State
  ↓
Protected Routes
```

Document security assumptions.

Never document actual:

- Passwords
- API keys
- Access tokens
- Refresh tokens
- Client secrets
- Private keys
- Cookies containing secrets

---

# 9. Authorization

Document:

- Role-based access control
- Permission checks
- Route protection
- Component-level authorization
- Feature-level authorization
- Permission hooks
- Authorization utilities

Example:

```typescript
/**
 * Determines whether the current user has permission to access
 * the specified feature.
 *
 * Authorization:
 * Permission-based access control.
 *
 * @param permission Required application permission.
 * @returns True when the current user is authorized.
 */
```

Clearly distinguish:

- Authentication = Who is the user?
- Authorization = What can the user do?

---

# 10. Next.js Middleware

If middleware exists, document:

- Purpose
- Routes affected
- Authentication checks
- Authorization checks
- Redirect behavior
- Public routes
- Protected routes
- Security implications

Example:

```typescript
/**
 * Next.js middleware responsible for protecting application routes.
 *
 * Responsibilities:
 * - Validates authentication state.
 * - Protects private routes.
 * - Redirects unauthenticated users.
 * - Allows public routes.
 *
 * Security:
 * This middleware must not be considered the only authorization
 * boundary. Sensitive authorization must also be enforced by the backend.
 */
```

---

# 11. Forms

Document all important forms.

Document:

- Form purpose
- Fields
- Validation rules
- Submission behavior
- API interaction
- Error handling
- Loading state
- Success behavior

For DTO-like frontend types:

```typescript
/**
 * Represents the data submitted by the login form.
 *
 * Validation:
 * - email is required.
 * - password is required.
 */
```

---

# 12. Validation

Document:

- Zod schemas
- Yup schemas
- Custom validators
- Form validation
- API response validation

Explain important validation rules and why they exist.

Do not duplicate backend validation documentation unnecessarily.

Clearly distinguish:

- UI validation
- Client-side validation
- Server-side validation

---

# 13. State Management

Identify the state management approach being used:

- React Context
- Zustand
- Redux
- Redux Toolkit
- React Query / TanStack Query
- SWR
- Local component state
- URL state
- Server state

Document:

- What state is managed
- Where the source of truth is
- State lifecycle
- Cache behavior
- Mutation behavior
- Invalidation behavior

For React Query / TanStack Query specifically document:

- Query purpose
- Query key
- Query dependencies
- Cache behavior
- Mutation behavior
- Invalidation strategy

Example:

```typescript
/**
 * Fetches the current user's profile.
 *
 * Cache:
 * Managed by TanStack Query.
 *
 * Query Key:
 * ['user', 'profile']
 *
 * Invalidated when:
 * - User profile is updated.
 * - User session changes.
 */
```

---

# 14. Types, Interfaces and Enums

Document:

- Interfaces
- Types
- Enums
- Unions
- Generic types
- API response types
- API request types
- Component props
- State types

Example:

```typescript
/**
 * Represents the authenticated user returned by the API.
 */
export interface User {
  /**
   * Unique user identifier.
   */
  id: string;

  /**
   * User's display name.
   */
  name: string;

  /**
   * User's assigned application roles.
   */
  roles: string[];
}
```

---

# 15. Utilities

Document:

- Date utilities
- Formatting utilities
- Validation helpers
- URL helpers
- Storage helpers
- Permission helpers
- Data transformation functions
- Error utilities
- Browser utilities

Example:

```typescript
/**
 * Formats a date according to the application's standard
 * date representation.
 *
 * @param date Date value to format.
 * @returns Formatted date string.
 */
```

---

# 16. Error Handling

Document:

- Error boundaries
- API errors
- Network errors
- Authentication errors
- Authorization errors
- Form errors
- Validation errors
- Loading failures
- Retry mechanisms

Explain how errors propagate through the application.

---

# 17. Loading and Empty States

Document important:

- Loading components
- Skeleton components
- Empty states
- Error states
- Suspense boundaries

Explain when each state is rendered and what triggers it.

---

# 18. React Performance

For performance-sensitive code, document important decisions such as:

- memo
- useMemo
- useCallback
- dynamic imports
- lazy loading
- code splitting
- virtualization
- server rendering
- caching
- prefetching

Do NOT add memoization or performance optimizations merely for documentation purposes.

Only document existing performance decisions.

---

# 19. Accessibility

For reusable UI components document important accessibility behavior:

- Keyboard interaction
- ARIA attributes
- Focus management
- Screen reader behavior
- Form labels
- Error announcements

Example:

```typescript
/**
 * Accessible modal dialog.
 *
 * Accessibility:
 * - Traps focus while open.
 * - Supports Escape to close.
 * - Provides an accessible dialog label.
 * - Restores focus to the trigger after closing.
 */
```

---

# 20. Environment and Configuration

Document:

- Environment variables
- Runtime configuration
- Build configuration
- Next.js configuration
- Feature flags
- Public vs private environment variables

Clearly distinguish:

- Browser-exposed environment variables
- Server-only environment variables

Never expose or document actual secret values.

---

# 21. Component Architecture

For every complex component explain:

- Responsibility
- Child components
- Data flow
- Event flow
- State ownership
- Composition model

Prefer documenting composition relationships rather than implementation details.

For example:

```text
Dashboard
 ├── DashboardHeader
 ├── DashboardStats
 │    ├── StatCard
 │    └── StatCard
 └── RecentActivity
      └── ActivityItem
```

Do not create unnecessary documentation for trivial JSX wrappers.

---

# 22. File-Level Documentation

For important files, add a short file-level JSDoc explaining:

- What the file contains
- Its architectural responsibility
- Important dependencies
- Important constraints

Example:

```typescript
/**
 * Authentication API client.
 *
 * Contains frontend API functions responsible for authentication
 * operations such as login, logout, and session retrieval.
 *
 * This module must not contain UI logic.
 */
```

Do not add meaningless file-level comments such as:

```typescript
/**
 * This file contains functions.
 */
```

---

# 23. Documentation Quality Rules

All documentation must:

- Be written in professional English.
- Be concise but meaningful.
- Describe WHY when architectural reasoning matters.
- Describe WHAT when behavior needs clarification.
- Avoid repeating obvious code.
- Avoid documenting implementation details that can become stale.
- Use accurate TypeScript types.
- Use correct JSDoc tags.
- Use `@param`.
- Use `@returns`.
- Use `@throws` where applicable.
- Use `@example` for non-obvious APIs.
- Use `@deprecated` when applicable.
- Use `@see` when useful.
- Avoid comments that simply repeat the function name.

Bad:

```typescript
/**
 * Gets user.
 */
getUser() {}
```

Good:

```typescript
/**
 * Retrieves the authenticated user's profile from the API.
 *
 * The result is used as the source of truth for the frontend
 * authentication context.
 *
 * @returns The authenticated user's profile.
 *
 * @throws UnauthorizedException
 * When the current session is invalid or expired.
 */
```

---

# 24. Documentation Coverage

After completing the documentation, produce a documentation coverage report.

Include:

```text
Frontend Documentation Report
=============================

Framework:
Next.js

Language:
TypeScript

Files analyzed:
X

Files documented:
X

Files requiring documentation:
X

Components:
X / X documented

Hooks:
X / X documented

Services/API clients:
X / X documented

Pages:
X / X documented

Layouts:
X / X documented

Types/Interfaces:
X / X documented

Authentication:
Documented / Partially documented / Missing

Authorization:
Documented / Partially documented / Missing

Middleware:
Documented / Partially documented / Missing

Forms:
X / X documented

Utilities:
X / X documented

Overall documentation coverage:
XX%

Potential documentation gaps:
- ...
- ...
- ...

Architecture observations:
- ...
- ...
```

---

# 25. Final Constraints

IMPORTANT:

- Do not rewrite the application.
- Do not refactor unrelated code.
- Do not change business logic.
- Do not change API contracts.
- Do not change component behavior.
- Do not change styling.
- Do not introduce new dependencies.
- Do not remove existing dependencies.
- Do not change authentication behavior.
- Do not change authorization behavior.
- Do not expose secrets.
- Do not add fake documentation.
- Do not guess undocumented behavior.

When behavior is unclear, inspect the surrounding code and usages before documenting it.

Documentation must reflect the actual implementation, not what the code should theoretically do.

If a component, hook, service, or utility has an architectural problem, document the existing behavior accurately rather than silently fixing it.

At the end, provide a concise list of architectural/documentation risks discovered during the analysis.
