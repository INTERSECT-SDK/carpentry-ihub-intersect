# Carpentry Lesson for iHub and Interconnected Science Ecocystem (INTERSECT)

This lesson is a template lesson that uses [The Carpentries Workbench][workbench]. 

Website: https://intersect-sdk.github.io/carpentry-ihub-intersect/

## Local development & CI checks using Docker

You can validate the lesson locally without installing R by using the official Carpentries sandpaper Docker image.

**Check the lesson:**

```bash
docker run --rm \
  -v "$(pwd):/lesson" \
  -w /lesson \
   ghcr.io/carpentries/workbench-docker:latest \
  Rscript -e "library(sandpaper); sandpaper::check_lesson('.')"
```

**Full local build:**

```bash
docker run --rm \
  -v "$(pwd):/lesson" \
  -w /lesson \
   ghcr.io/carpentries/workbench-docker:latest \
  Rscript -e "library(sandpaper); sandpaper::build_lesson('.')"
```

**Live preview server (auto-reloads on file changes):**

```bash
docker run --rm \
  -v "$(pwd):/lesson" \
  -w /lesson \
  -p 4321:4321 \
   ghcr.io/carpentries/workbench-docker:latest \
  Rscript -e "sandpaper::serve(host = '0.0.0.0', port = '4321', quiet = FALSE)"
```

Then open <http://localhost:4321> in your browser. The site updates automatically whenever you save a source file.


[workbench]: https://carpentries.github.io/sandpaper-docs/
