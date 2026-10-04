<h1 align="center">
  <img src="assets/readme/banner.svg" alt="Mohammad Ali Jesar, senior Ruby on Rails engineer for Shopify and e-commerce, AI agents, RAG and MCP" width="100%">
</h1>

<p align="center">
  <b>Senior Ruby on Rails Engineer · Shopify & E-commerce · AI Agents, RAG & MCP</b><br>
  Full-stack · Lahore, Pakistan · Open to remote roles and freelance projects
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/mjesar/"><img src="https://img.shields.io/badge/LinkedIn-mjesar-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn profile of Mohammad Ali Jesar"></a>
  <a href="https://www.fiverr.com/mjesar"><img src="https://img.shields.io/badge/Fiverr-mjesar-1DBF73?logo=fiverr&logoColor=white" alt="Fiverr profile for Ruby on Rails freelance work"></a>
  <a href="mailto:mohammadalijaisar@gmail.com"><img src="https://img.shields.io/badge/Email-open%20to%20work-informational" alt="Email Mohammad Ali Jesar, open to work"></a>
</p>

I'm Mohammad Ali Jesar (Ali), a senior Ruby on Rails engineer with 7+ years of experience building production software for international clients. I build Rails APIs and integrations, and most of my work is in Shopify and e-commerce: I contributed to five apps on the Shopify App Store (three also on BigCommerce) and built catalog, order, and marketplace integrations. I also add AI to existing Rails applications, including MCP servers, RAG on PostgreSQL, and agents that work with real application data and tools.

## What I work on

- **Ruby on Rails:** APIs, PostgreSQL, Redis, Sidekiq, performance work, and React or Hotwire frontends, with JavaScript and TypeScript. Deployments on Heroku, AWS, Google Cloud, and Docker.
- **Shopify and e-commerce:** Shopify and Shopify Plus (checkout customization, B2B features), BigCommerce apps, Shopify Functions, extensions, and Liquid
- **Integrations:** REST and GraphQL APIs, webhooks, and syncing products, inventory, and orders between systems, including Amazon SP-API
- **AI engineering:** MCP servers, RAG, AI agents, and LLM assistants connected to application data

## Featured projects

Three open-source projects that cover the same ground from different sides: safe LLM access to store data, conversational catalog search, and measuring how visible a product is to AI assistants.

<p align="center">
  <img src="assets/readme/projects-flow.svg" alt="shop_mcp_server exposes a store to Claude over MCP, ai_shop_assistant searches Shopify's live Catalog API, and product_geo_agent scores how discoverable a product is to AI shopping assistants" width="100%">
</p>

### [shop_mcp_server](https://github.com/mjesar/shop_mcp_server)
**What it does:** an MCP server in Rails that exposes a store's products, orders, and inventory to Claude.
**Problem:** an LLM needs access to real store data, and write actions should not run without a human approving them.
**What I built:** schema-validated tools, read-only and destructive annotations so clients gate writes behind approval, transactional order creation with rollback, and semantic product search with Voyage AI embeddings and pgvector. I verified it in the Rails console, MCP Inspector, and as a live Claude custom connector, and moved to the official MCP Ruby SDK after finding a legacy SSE vs. Streamable HTTP transport mismatch.
**Stack:** Rails 8.1, MCP Ruby SDK, PostgreSQL, pgvector, Voyage AI, RSpec.

### [ai_shop_assistant](https://github.com/mjesar/ai_shop_assistant)
**What it does:** a shopping assistant that answers product questions from Shopify's live Catalog API over MCP.
**Problem:** answers should come from the real catalog, not from the model's memory.
**What I built:** the chat UI with realtime replies over Turbo Streams, background jobs on Solid Queue, and a hand-written HTTP/JSON-RPC MCP client, because the existing gem failed on the protocol handshake.
**Stack:** Rails 8, RubyLLM, Google Gemini, Hotwire, MongoDB.

### [product_geo_agent](https://github.com/mjesar/product_geo_agent)
**What it does:** an agent that rates how discoverable a Shopify product is to AI shopping assistants (GEO and AEO).
**Problem:** a product page can look fine to a person and still be hard for an AI assistant to read and trust.
**What I built:** checks of product data, FAQ content, and schema.org structured data, an LLM step that judges whether it would recommend the product, and a deterministic score backed by an eval harness.
**Stack:** Rails, Google Gemini, Shopify Storefront API.

## Shopify and e-commerce

I worked on Shopify and BigCommerce apps for furniture and retail merchants, from architecture through App Store publishing and merchant support. Much of that work was keeping data in step across systems: products, inventory, and orders moving between supplier and retailer stores, Amazon, and the storefront, using the Admin APIs, webhooks, and Sidekiq jobs with retries.

- **Shopify apps:** embedded apps with Polaris and App Bridge, Admin and Storefront REST and GraphQL APIs, webhooks, Shopify CLI, and App Store publishing and compliance
- **Shopify Functions and checkout:** Functions (including Scripts-to-Functions migration for discounts, delivery, and payment customizations), Checkout UI Extensions, and Checkout Extensibility
- **Themes:** Theme App Extensions and Liquid
- **Shopify Plus:** checkout customization with Shopify checkout extensions, and Shopify Plus B2B features
- **BigCommerce:** apps built on the Catalog, Orders, and Checkout APIs (REST and GraphQL), with webhooks and app store publishing
- **Amazon SP-API:** product listings, variants, and image uploads, including an Amazon Import & Sync System that keeps listings in step between Amazon and e-commerce stores
- **Production support:** led deployment, versioning, and updates to the app stores, and fixed issues across app code, DNS, and email delivery

Apps published on the Shopify App Store, built as part of the MGLogics development team:

- [MGLogics JSON-LD SEO Schema](https://apps.shopify.com/json-express-for-seo) (Shopify and BigCommerce): structured data for rich results and AI search. Rated 4.3/5 across 17 reviews.
- **Express Sync: Order & Inventory** (Shopify and BigCommerce): real-time product, inventory, and order sync between supplier and retailer stores.
- [MGLogics Express SEO & Schema](https://apps.shopify.com/express-seo): image optimization, JSON-LD, alt tags, redirects, and schema management.
- [GeoLocation Traffic Redirect](https://apps.shopify.com/express-geo-redirect) (Shopify and BigCommerce): country-based redirects with pop-up and automatic options.
- [Email Validator by MGLogics](https://apps.shopify.com/express-email-validator): detects fake or invalid emails on orders to prevent order scams.

## AI engineering

My AI work is application engineering: connecting models to the data and actions an existing app already has, and keeping the behavior predictable.

- **MCP:** shop_mcp_server exposes tools and resources with validated arguments and approval-gated writes. ai_shop_assistant uses a custom MCP client against Shopify's Catalog API.
- **RAG on the database you already have:** semantic product search with PostgreSQL, pgvector, and Voyage AI embeddings, with no separate vector database.
- **Agents and assistants:** ai_shop_assistant uses RubyLLM and Gemini with tool calling against a live catalog. In product_geo_agent, the LLM judges and the scoring stays deterministic code, so results are repeatable and covered by evals.
- **GEO and AEO:** product_geo_agent, plus JSON-LD structured data in the SEO apps, for making stores readable to AI assistants.

## Experience

- **MGLogics** (Dec 2021 to Jun 2026, remote): full-stack Rails and React engineer on Shopify and BigCommerce apps, catalog and order sync, and Amazon SP-API integrations. Worked daily with US clients.
- **SimpleDeploy** (Apr 2019 to Dec 2021): backend engineer building Rails REST APIs on SQL and NoSQL databases, and management MVP tools for German clients.
- **Education:** B.S. in Information Technology (Software), Sindh Agricultural University, 2012 to 2017.

## FAQ

**How do I add AI features to an existing Rails app?**
Start with what the model needs: your data and a few safe actions. In my projects that meant RubyLLM for the model calls, MCP tools for actions, pgvector for search, and background jobs for slow work, so the AI fits into the app you already have. [ai_shop_assistant](https://github.com/mjesar/ai_shop_assistant) is a small working example.

**Can RAG be added to a Rails app that already uses PostgreSQL?**
Yes. pgvector adds vector search to PostgreSQL, so there is no separate vector database to run. [shop_mcp_server](https://github.com/mjesar/shop_mcp_server) stores Voyage AI embeddings in pgvector for product search.

**What is involved in building a custom MCP server in Rails?**
Defining tools with validated arguments, marking which are read-only and which are destructive so clients gate writes behind approval, choosing the right transport, and testing from a real client. In shop_mcp_server I moved to the official MCP Ruby SDK after hitting an SSE vs. Streamable HTTP mismatch, and verified it in MCP Inspector and as a live Claude custom connector.

**How can an AI agent safely connect to store data and tools?**
Give it narrow tools, validate every argument, and require approval for anything that writes. Keep decisions that must be repeatable in code, not in the model. [product_geo_agent](https://github.com/mjesar/product_geo_agent) does this: the LLM judges, and the score is deterministic.

**What should I look for in a Shopify Plus developer?**
Ask to see work on checkout extensions, Shopify Functions, and B2B features, and how they handle migration and testing. My Shopify Plus work is checkout customization with checkout extensions and B2B features, on top of five apps published on the Shopify App Store.

**Can a Rails developer build Shopify apps and integrations?**
Yes. Rails powered the apps I worked on, including order and inventory sync between supplier and retailer stores, Amazon SP-API listing imports, and JSON-LD structured data apps.

**How do you keep inventory and orders in sync between Shopify and other systems?**
Webhooks for changes, Sidekiq jobs with retries for the heavy work, and the Admin APIs for writes. Syncing products, inventory, and orders between supplier and retailer stores, and importing and syncing Amazon listings, are examples of this kind of sync.

**Are you available for remote work?**
Yes, for remote roles and freelance projects. Email is below.

## Contact

Email: mohammadalijaisar@gmail.com
