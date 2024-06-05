---
pcx_content_type: example
summary: A compression rule where Brotli compression for all incoming requests of a given zone is disabled.
product:
  - Compression Rules
title: Disable Brotli compression for all requests of a zone
---

# Disable Brotli compression for all requests of a zone

The following example rule will disable Brotli compression for all incoming requests of a given zone. The only available compression algorithm will be Gzip.

{{<example>}}

**When incoming requests match**

- All incoming requests

**Then**

- **Compression options**: Custom
- **Define a custom order for compression types**: `Gzip`

{{</example>}}

If the client does not support Gzip compression, the response will be uncompressed.

## Example API request

The following example sets the rules of an existing [entry point ruleset](/ruleset-engine/about/rulesets/#entry-point-ruleset) (with ID `{ruleset_id}`) for the `http_response_compression` phase to a single compression rule, using the [Update a zone ruleset](/api/operations/updateZoneRuleset) operation:

```bash
curl --request PUT \
https://api.cloudflare.com/client/v4/zones/{zone_id}/rulesets/{ruleset_id} \
--header "Authorization: Bearer <API_TOKEN>" \
--header "Content-Type: application/json" \
--data '{
  "rules": [
    {
      "expression": "true",
      "action": "compress_response",
      "action_parameters": {
        "algorithms": [
          { "name": "gzip" }
        ]
      }
    }
  ]
}'