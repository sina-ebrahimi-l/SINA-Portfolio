# SINA Deep Link

## Overview

A branded link-routing service for recurring video destinations and one-off links used by content automation.

## The Problem

Content workflows often need a short, controlled destination that can preserve social previews, open the intended app when possible and avoid exposing infrastructure credentials to the publishing layer.

## The Solution

The service owns link storage and routing behind a branded domain. Stable video presets remain independently updateable, while mobile automation can request isolated one-off links without overwriting those recurring routes.

## Core Capabilities

- Stable branded links for recurring YouTube content
- Versioned share URLs for fresh social previews
- YouTube app/web fallback
- Isolated one-off branded links for HTTP/HTTPS destinations
- Immutable version snapshots for generated links
- Private service-to-service generation for the Content Distribution System
- Separation of link storage from publishing workflows

## My Role

Product architecture, link-routing rules, integration boundaries, operational workflow design and production verification.

## Status

**In Production — stable YouTube routing is production-verified; generic one-off link generation is deployed and integrated with the mobile content-control layer**
