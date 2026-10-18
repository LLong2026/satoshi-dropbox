# Satoshi Dropbox — Deterministic Bitcoin OP_RETURN Anchoring Rails (SIP-042)

**Leon Calvin Long, II — SquirlOS Technologies LLC**

> This software is a prototype and is provided for educational and research purposes only. It is not intended for production use, commercial deployment, or safety-critical environments. All systems are experimental and may contain defects. All battery payloads are synthetic.

The rails that executed the October 18, 2026 end-to-end tokenization loop: a patent artifact sealed permanently on Bitcoin mainnet, reconstructed byte-identically in a keyless browser, ownership transferred A → B → A with the asset never moving, and the article documenting it self-anchored by its own hash.

## What is in this repo
| File | What it is |
|---|---|
| `dropbox_reader.py` | Keyless OP_RETURN reader (no keys, no accounts, public APIs only) |
| `dropbox_writer.py` | Legacy P2PKH writer (testnet lineage) |
| `dropbox_writer_sw.py` | Segwit P2WPKH writer, BIP143 signing validated against official BIP-143 vectors |
| `custody_transfer.py` | Ownership transfer tool: A→B→A custody round trip, asset hash re-anchored per hop |
| `PREREG_M-DROP-1.md` | Frozen SIP-042 DROPBOX prereg (sha-verified) |
| `DROPBOX_M1_RUNLOG.md` | Mainnet runlog: patent seed, block 972023 |
| `THE_FULL_LOOP_ARTICLE.md` | The self-anchored end-to-end paper (DOI 10.5281/zenodo.23456550) |

## Doctrine (frozen)
- **Transfer-only**: delivers, retains nothing. **Binary outcome**: lands or not.
- **No monetary function**: fee = postage only. Hash-only payloads: 4-byte marker + version + 32 bytes.
- **Keys live ONLY on the writer side**: no WIF, no signing, no spending code is ever published here.
- **Reader is keyless**: anyone can pull any anchor by txid from any block explorer.

## Verify the receipts yourself
1. **DOI tier**: DOI 10.5281/zenodo.23455954 (complete receipts corpus), 10.5281/zenodo.23456550 (the loop paper).
2. **Bitcoin tier**: patent seed tx `97d8cd38...a5b89` (block 972023); IP ledger tx `549bcf47...90118` (block 972026); custody round trip `1f550498...d5093e` + `c850f1d4...d11ec8` (block 972031); article self-anchor `9276a041...e2605`.
3. **Git tier**: append-only master ledger at github.com/LLong2026/four-horsemen (since Sept 7, 2026).
4. **Viewer**: paste the patent seed hash at https://deterministic-code-dsos.base44.app/genesis-viewer and watch the artifact rebuild from 32 bytes.

## Not in this repo (deliberately)
- Writer private keys (writer-side only, never committed anywhere).
- The TGC generation engine — licensed commercial product, not distributed in source form.
- Any customer, client, or tenant data. All payloads are the company's own records or synthetic material.

## License
Code: MIT. Written materials: CC-BY-4.0. Patent statuses: USPTO 19/693,343 pending; THREADZERO 64/081,490 pending. No patent claim is granted or asserted by this repository.

## Dual Mesh Benchmark
Status: MEASURED (scoped) — DOI 10.5281/zenodo.23345241 (DeepSeek column); cross-engine expansion DOI 10.5281/zenodo.23348675.
