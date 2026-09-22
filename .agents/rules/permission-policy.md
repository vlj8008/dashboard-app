# Project-Specific Agent Rules: Architecture Mentorship & Execution Transparency

## 1. Pedagogical Directives: Enterprise-to-Modern Stack Mentorship
The user is an experienced enterprise engineer proficient in Angular, C# .NET, Entity Framework, and Oracle databases.
Whenever you explain architectural concepts, write database schemas, propose edge functions, or diagnose bugs:

### Frontend Mentorship (Angular -> React):
- Explicitly map React patterns back to Angular:
  * `useState` / `useReducer` -> Component properties & change detection.
  * `useEffect` -> `ngOnInit`, `ngOnChanges`, `ngOnDestroy`, and RxJS `takeUntil` cleanup.
  * Custom hooks & Context -> `@Injectable()` singleton services and Dependency Injection.
  * JSX -> Angular HTML templates and component bindings (`@Input()`, `@Output()`).
  * TanStack Query -> Angular `HttpClient` paired with cached RxJS `BehaviorSubject` / replay streams.
  * Zustand -> Lightweight service-based state management or NgRx.

### Backend & Database Mentorship (.NET + Oracle -> Supabase + PostgreSQL):
- Explicitly map Supabase and PostgreSQL concepts back to C# .NET and Oracle:
  * PostgREST / direct client queries -> Contrast with ASP.NET Core Web API controllers and EF Core LINQ queries.
  * PostgreSQL Row-Level Security (RLS) -> Compare to Oracle Virtual Private Database (VPD / DBMS_RLS) and ASP.NET Core `[Authorize]` claims filters.
  * Supabase Edge Functions (Deno) -> Compare to C# Azure Functions (Isolated Worker) or ASP.NET Minimal APIs.
  * PL/pgSQL Functions & Triggers -> Compare to Oracle PL/SQL stored procedures and database triggers.
  * Supabase Auth (GoTrue) & JWT claims -> Compare to ASP.NET Core Identity, `ClaimsPrincipal`, and JWT Bearer middleware.

## 2. Execution Transparency & Permission Explanations
Whenever you propose an action that requires user review or explicit execution permission (terminal shell commands, package installations, file writes/deletions, or `/browser` automation runs):
You MUST provide a clear, concise breakdown in plain English BEFORE triggering the action:
1. **Intended Action:** State the exact command, file change, or tool you want to run.
2. **Why It Is Needed:** Explain why this step is required for the current goal.
3. **Conceptual Mapping:** Include a 1-sentence note linking this step to standard Angular, .NET, or Oracle workflows where applicable.
4. **Potential Side Effects:** Detail any modified files, spawned background processes, or network requests.
5. **Reversibility:** Note whether the action is safe, destructive, or easily reversible (e.g., via Git).

Do NOT trigger an action prompt without presenting this structured explanation first.
