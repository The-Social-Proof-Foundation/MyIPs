# MyIP Metadata Standard v1.0.0

## Overview

The MyIP Metadata Standard defines the schema for intellectual property metadata registered on the MySocial blockchain. This standard ensures consistency in how digital content ownership is represented, tracked, and verified within the MySocial ecosystem.

## Purpose

This standard aims to:
- Establish a uniform way to represent digital content ownership
- Facilitate interoperability between different applications in the MySocial ecosystem
- Ensure provenance tracking of digital content
- Enable royalty and rights management
- Support transparent ownership history

## Specification

The standard is defined as a JSON schema in [myip-metadata-standard.json](./myip-metadata-standard.json).

### Required Fields

The following fields are mandatory for any MyIP metadata:

| Field | Type | Description |
|-------|------|-------------|
| myip_id | string | Unique identifier for the intellectual property |
| title | string | Title of the content |
| creator | string | Blockchain address or identity of the original creator |
| creation_date | string (date-time) | ISO 8601 timestamp marking content creation |
| content_type | string (enum) | Type of digital content (video, image, audio, text, other) |
| hash | string | Cryptographic hash of the content |
| storage_uri | string | Decentralized storage link to access the content |

### Optional Fields

Additional fields that provide more context and functionality:

| Field | Type | Description |
|-------|------|-------------|
| license | string | License type governing content usage and rights |
| royalty_percentage | number (0-100) | Royalty percentage for resale or licensing |
| transferable | boolean | Indicates if ownership is transferable |
| owners | array of strings | List of current owner addresses |
| history | array of objects | History of significant events related to this IP |

## Implementation

Implementations must:
1. Validate all metadata against the JSON schema
2. Ensure the uniqueness of myip_id across the platform
3. Verify that the hash matches the actual content at storage_uri
4. Maintain the integrity of the history array when ownership changes

## Related MyIPs

This standard implements the specifications outlined in:
- MyIP-1: MyIP Purpose and Guidelines

## Versioning

This standard follows semantic versioning. The current version is 1.0.0.

## License

This standard is licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/).