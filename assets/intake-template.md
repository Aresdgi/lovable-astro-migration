# Lovable → Astro intake template

Use or adapt this when the user gives a repo, folder, or partial context.

## Minimal intake

- Source: repo URL or local folder
- Target: existing Astro project or new Astro migration
- Goal: preserve Lovable design with high fidelity
- Constraints: package manager, deployment target, libraries to keep/remove
- Priority pages/components: if the user has any

## Default assumptions when the user is brief

If the user does not specify otherwise, assume:

- preserve the exported Lovable aesthetics as closely as possible
- keep Tailwind if the source uses Tailwind
- migrate static UI to Astro
- keep interactivity in narrow React islands
- avoid unnecessary redesigns and broad refactors
- deliver implementation, not just a plan

## Example trigger prompts

- “Migrá este repo de Lovable a Astro sin perder la estética.”
- “Convertí este export de Lovable en un proyecto Astro manteniendo Tailwind y separando islands correctamente.”
- “Estoy en un proyecto Astro. Integrá este diseño de Lovable y hacé la migración completa.”
- “Analizá este repo de Lovable y pasalo a Astro con la mínima hidratación posible.”
