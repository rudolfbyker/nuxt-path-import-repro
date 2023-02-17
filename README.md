# Reproduction for a weird nuxt issue

## Problem statement

When the parent folder of a nuxt project contains the string "nuxt", some imports fail.

## Steps to reproduce

1. Create a folder with `nuxt` in the name: `mkdir -p ~/tmp/foo-nuxt-examples`
2. Go there: `cd ~/tmp/foo-nuxt-examples`
3. Clone this repo into a sub-folder with any name, say "app". It may or may not contain "nuxt": `git clone ... app`
4. Go into the sub-folder: `cd app`
5. Install dependencies: `yarn`
6. Start the development server: `yarn dev`
7. Open the browser at http://localhost:3000
8. Observe error 500: `Cannot find module './stringify' Require stack: …`

## Workaround: Rename the parent folder to something else that does not contain "nuxt"

1. Stop the server: `Ctrl+C`
2. Go up: `cd ../..`
3. Rename the parent folder to something else that does not contain "nuxt": `mv foo-nuxt-examples foo-my-examples`
4. Go back into the sub-folder: `cd foo-my-examples/app`
5. Start the development server: `yarn dev`
6. Open the browser at http://localhost:3000
7. No errors this time.
