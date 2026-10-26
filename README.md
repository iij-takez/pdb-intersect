# pdb-intersect
Find common peering points in peeringdb.

This is a brother to https://github.com/rucarrol/PeerFinder

It will find common possible peering points, even if either of the
peering parties is NOT using the same ASN in all locations (like, incidentally, 3557 does).

## Installation

  - throw the files in your bin directory
  - edit the config file to put your pdb credentials in
  - make sure the config file is protected

Please check requirements.txt for necessary libraries.

## API key usage

Anonymous PeeringDB API access is heavily rate-limited, so using an API key is
strongly recommended. See https://docs.peeringdb.com/howto/api_keys/ for how to
create one (read-only access is sufficient).

The key is looked up in the following order; the first one found is used:

1. Environment variable `PEERINGDB_API_KEY`
2. `~/.peerfinder/peeringdb_api.key`
3. `~/.peeringdb_api.key`

The file locations are compatible with
[PeerFinder](https://github.com/rucarrol/PeerFinder), so an existing key can be shared.
Restrict the key file to your user only:

    chmod 0600 ~/.peerfinder/peeringdb_api.key

When an API key is found, it takes precedence over the username/password in
`pdb-intersect.conf`.
