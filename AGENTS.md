# AGENTS.md

## Project

Remotion video project for programmatic video creation using React/TypeScript.

## Commands

```bash
pnpm install          # Install dependencies
pnpm dev              # Start Remotion Studio (preview)
pnpm build            # Bundle for deployment
pnpm lint              # ESLint + TypeScript check
npx remotion render HelloWorld out/video.mp4   # Render composition to file
npx remotion still HelloWorld out/frame.png    # Render still image
```

## Structure

```
src/
  index.ts       # Entry point (registers root)
  Root.tsx       # Compositions defined here
  HelloWorld.tsx # Main component
  HelloWorld/    # Component subfolder
  index.css      # Global styles (Tailwind)
public/          # Static assets (use staticFile() to reference)
```

## Key Files

- `remotion.config.ts` - Configures Tailwind v4 via `enableTailwind()`, JPEG image format
- Each `<Composition>` in `Root.tsx` defines a renderable video with unique `id`

## Conventions

- Package manager: **pnpm** (pnpm-lock.yaml present)
- Tailwind v4 enabled via `@remotion/tailwind-v4`
- Props schemas use Zod (`z.object()`) with `zColor()` from `@remotion/zod-types`
- Default composition: 1920x1080, 30fps

## Remotion Best Practices

See `.agents/skills/remotion-best-practices/SKILL.md` for comprehensive Remotion guidance including:

- `<Video>`, `<Audio>`, `<Img>`, `<Gif>` tag usage
- `interpolate()`, `spring()`, `random()` helpers
- `Sequence`, `Series`, `TransitionSeries` for timing
- `AbsoluteFill` for layering
- Lambda/cloud rendering workflow
