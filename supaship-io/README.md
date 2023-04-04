
# Startup project

In the supabase-io-course folder,

`yarn add vite`
`yarn create vite`

- framework: react
- select name: supaship-io
- variant: typescript

Then use `yarn` to install dependencies.

# First run

`cd supaship-io`
`yarn dev`

# Supabase dependencies

To add supabase dependencies to the project:

`yarn add -D supabase`

`supabase init`

`supabase start`

Also for the react app:

`yarn add @supabase/auth-ui-react @supabase/supabase-js`

# Supabase migration

To keep track of changes in the structure of the database:

`supabase migration new starting-ddl`

Note: ddl is data definition language

Later, when new changes are applied from the Supabase Studio interface:

`supabase db diff --use-migra --file=<name of the migration>`

However, it is recommended to write changes directly in the .sql files.

`supabase db push` to push to production

# Supabase policies

If using Supabase Studio:

Authentication tab > Policies > <table name> > Enable RLS (Row Level Security)

# Playwright is a testing tool

Within supaship-io folder:

`yarn create playwright`

- end-to-end directory: e2e
- github actions: false
- install: true

To the playwright.config.ts:

```
webServer: {
    command: 'yarn dev',
    port: 1337,
    reuseExistingServer: true,
},
```

Then to detect ports we need a dependency:
`yarn add -D detect-port`

Advantages:
- No mocking
- No auth hacks
- Speed
- Reliability



# Troubleshooting

If testing with libraries is problematic, remove module from packages.json

If issues with authentication in local, see Supabase CLI video 02:20

