# paket-private-feed

Paket probe: authenticated private NuGet feed alongside public NuGet source.

## What this tests
- Multiple `remote:` entries in paket.lock (public + private feed)
- Authenticated source syntax in paket.dependencies (`username:` / `password:` with env vars)
- Mend UA detection of packages from both public and private sources
- Transitive dependency from private package referencing a public package

## Dependencies
- `Newtonsoft.Json 13.0.3` (public NuGet, direct)
- `Serilog 3.1.1` (public NuGet, direct)
- `Contoso.Internal.Utils 1.2.3` (private feed, direct) → `Newtonsoft.Json` (transitive)
