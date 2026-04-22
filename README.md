# Kelp DAO Research

On-chain forensic research on the Kelp DAO rsETH exploit of April 2026.

## What this is

A timeline of the exploit drawn from Ethereum mainnet transaction data, verified against public RPCs and the rsETH contract source on Sourcify. Three claims in the piece have not appeared in public reporting as of 2026-04-22:

1. The attacker attempted three `lzReceive` calls. Only the first succeeded.
2. The retries reverted at the rsETH token contract (selector `0x5f4854f9` = `TransfersBlocked`), not at the LayerZero Endpoint or the OFT adapter.
3. Kelp recovered approximately $101.8M via `FrozenFundsRecovered` at 07:15:59 UTC on 2026-04-19, reclaiming 40,373.72 rsETH from the OFT adapter to custody.

## Methodology

Every claim ties to a publicly verifiable on-chain artifact. See `/Users/francis/LygosYouTube/2026-04-20_kelp-dao-exploit/assets/tier4_verify/` for the cached RPC responses used in compilation. Canonical timestamps are the block timestamps returned by `eth_getBlockByNumber`.

## Local development

```bash
npm run dev
# opens on http://localhost:3000
```

## Deployment

```bash
vercel           # preview
vercel --prod    # production
```

## Sources

Full source list inside `public/index.html`. Primary references: LayerZero V2 Endpoint on-chain logs, Sourcify-verified rsETH implementation at `0x7159107483e623707c18c6e06cbc095bd0717783`, QuillAudits, Innora.ai, DeFiPrime, Aave governance incident report.

## License

Content under CC BY 4.0. Attribution appreciated, not required.
