# Configuration

This folder is reserved for configuration introduced alongside executable code. Phase 0 has no configuration loader, deployed environment, or runtime configuration file.

Future configuration may describe source locations, table destinations, environment identifiers, and processing parameters. We will add only settings needed by an implemented phase and validate required values when they are loaded.

Configuration separates an environment-specific value from reusable logic. For example, changing a source location should not require rewriting a transformation.

Version-controlled configuration should contain safe defaults or examples. Local credentials belong outside tracked configuration. `.env` files, `.databrickscfg`, and `config/*.local.json` are ignored; `.env.example` is allowed if needed later.

We will choose a configuration format and loading approach when the first code needs them, without adding a library in advance.
