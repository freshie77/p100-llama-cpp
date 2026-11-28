# Native rolling RAM acceptance — November 28, 2026

Installed native backend remains immutable `unified-p100-incremental-20`, source `44aa03b40fd009c46d0aa99fcba8fe4d64a50675`. One shared model, two 65,536-token slots, native vision, full hybrid state, core/CUDA libraries and model/projector artifacts are unchanged. Subsequent source commits update build/storage tooling and evidence; they do not identify a new deployed binary. Push this branch only to the owner fork (`freshie77/p100-llama-cpp`, PR 1), never upstream.

Actual installed-native measurements are retained at `/mnt/archive-disks/disk13/andrew-runtime-storage/latency-installed-benchmarks-20261128`, with guard completion and `production-restored.json`. The guard exited 0 and restored both opaque native slot states, the original native process, protected identity and production callers.

| Criterion | Evidence/result |
| --- | --- |
| Matched 24K complete hybrid restoration | Same 964,069,476-byte state, six interleaved legacy/RAM samples; medians 18.795623 s and 0.586395 s, approximately 32.05x for this operation |
| Interleaved native restoration | Exact 48-token cross-slot continuation after rewind; cached prefix 22,524 tokens |
| Two occupied long contexts | 65,024 prompt tokens retained in each 65,536 slot; exact requested 256/384 generated tokens |
| Concurrent generation | Conversation 33.0069 tokens/s, operation 35.4997 tokens/s; retained conversational TTFT 0.140020 s |
| Historical reference | 33.32/35.76 tokens/s and 0.144 s TTFT; new single-run differences are reported, not presented as a statistically established regression or improvement |
| Native numerical/vision preservation | Earlier accepted r20 cross-slot fault isolation in both directions, exact 96-token native image continuation, r19 30-turn rolling and 15-turn boundary proofs retained |

The restore measurement used installed Runtime `56a94f2d` and native20. Later Runtime scheduling and media startup fixes retain the same snapshot/restore implementation and native bundle; the measurement is component evidence, not a claim of universal or whole-turn speedup. Small canonical-turn comparisons are separate and are not interleaved.

Rescue2 builds now require the installed storage preflight before writes and default to `/mnt/archive-disks/disk13/andrew-runtime-storage/engineering/builds/p100-llama-cpp-<revision>`, with bulk temporary storage. Other hosts retain the existing default. Explicit `BUILD_DIR` overrides remain available. Do not build over a loaded immutable bundle. Build shell syntax checked; no unnecessary native rebuild or deployment was performed.

Final installed Runtime is `andrew-9c8d24345f76-21ba0d84605dc24a`, source `9c8d24345f766db8a7d9d514f84deb2cbaea00bf`. Its inference modules exactly match the corrected installed `a9524a5f` cycle, which advanced both cognitive contexts from generation 2 to 3 without foreground compaction fallback. `final-applicability-20261128.json` independently verifies native20 binary hashes, its actually mapped process, the same process instance `787771978090`, two 65,536-token slots, retained rollback files and the precise changed Runtime functions since source56. The native backend was not restarted for these corrective Runtime rollouts.

The final preservation readback found Head healthy on its expected release after the earlier external disconnection. Manual browser ownership remains respected; current page/physical playback observation is deferred. These availability conditions do not invalidate independent native measurements. No physical modem outage or unrelated research was performed.
