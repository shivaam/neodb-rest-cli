# neodb-rest-cli

Generated CLI for the [NeoDB](https://neodb.net) REST API.

This wrapper is built from the public OpenAPI spec at
`https://neodb.social/api/openapi.json` using
[`openapi-cli-gen`](https://github.com/shivaam/openapi-cli-gen).

## Install

```bash
pipx install neodb-rest-cli
```

The generated package defaults to:

```bash
https://neodb.social
```

Override the target instance with:

```bash
export NEODB_REST_CLI_BASE_URL=https://your.instance
```

## Examples

### Verified Commands

These commands were run successfully before publishing `0.1.0`.

Public/read-only catalog search against `https://neodb.social`:

```bash
neodb-rest-cli catalog search-item --query Dune --category book --output-format json
```

Result marker: the response included populated `data`, `pages`, and `count`
fields.

Additional public/read-only commands:

```bash
neodb-rest-cli trending book --output-format json
neodb-rest-cli trending movie --output-format json
```

Authenticated personal-data workflows:

```bash
neodb-rest-cli shelf list-marks-on --type book --output-format json
neodb-rest-cli tag list --output-format table
neodb-rest-cli collection list-user --output-format json
```

## Auth

NeoDB exposes bearer/OAuth-style auth in its spec. Set a token when calling
authenticated endpoints:

```bash
export NEODB_REST_CLI_TOKEN=...
```

## Notes

This is an unofficial community wrapper. Start with read-only commands before
testing shelf, review, note, tag, or collection writes against personal data.
