# Source-review companion v0.3.1

This author-identified, source-only companion supports inspection of the implementation and wholly invented offline engineering tests. It is **not a stand-alone clinical reproduction package** and does not contain patient data, fitted models or study results. Read `REVIEW_SCOPE.txt` before use.

This package does not assert that a repository, reviewer-access URL or archive DOI is already operational. Distribution and archive status must be checked at the actual repository or archive. Sharing this source companion and authorizing clinical-data access or execution are separate decisions.

## What can be reviewed

The scientific source files are unchanged from the preceding reviewed candidate. They include SQL extraction/feature logic and R analysis helpers, including historical code context that is not a supported complete workflow. The mapping-schema specification and extraction-order specification explain required interfaces and missing production components. The source includes reviewed transformations from historical execution sources; inclusion does not establish byte identity with every historical source or full semantic equivalence.

`review.py` is an **offline review entrypoint**, not a database extractor or model runner. It has only `check` and `plan` commands. SQL concatenation is not the production workflow. The outer safeguards, mapping loader, temporal insertion, PRIMARY-specific endpoint hook, capture/cleanup logic and stage20 orchestration still require a complete portable implementation and validation before authorized clinical execution.

## Offline use

From this companion directory, after inspecting and trusting the code:

```text
python -B review.py check
python -B review.py plan
python -B tests/test_review.py
Rscript --vanilla tests/artificial_mechanisms.R .
```

Only Python standard-library modules and R base/stats are needed for these offline tests. No external R package is installed or used by them. In a restricted environment, point temporary-directory environment variables to an authorized audit directory outside this companion; see `docs/offline_test_plan.txt`. The integrity check rejects unlisted files, so do not add credentials, local data, caches or outputs to this directory.

The check compares files with the included manifest. It is not a digital signature or protection against replacement of both code and manifest. Clinical execution remains unsupported and unauthorized by this package, regardless of its distribution status. The tests operate on invented filesystem fixtures, header lists and numerical arrays. They do not validate clinical data, fit a model, create patient predictions, rerun bootstrap sampling or reproduce manuscript results. A skipped platform-specific test is not evidence that the skipped mechanism was exercised.

## Included content and limitations

- `source/`: scientific R and SQL source for inspection; historical helpers are not automatically supported runnable entrypoints.
- `docs/mapping_contract.txt` and `docs/mapping_schema.json`: the ordered, all-text source-observed mapping schema. The actual frozen mapping is not supplied. Schema information cannot establish mapping-content equivalence or permission to use a mapping. The offline header/order check is stricter than the historical loader's header-skipping behavior.
- `docs/extraction_order.txt` and `docs/assembly_plan.json`: static assembly order and explicitly unbundled production hooks. PRIMARY requires the fixed-risk endpoint `after19` path, not the generic sensitivity path.
- `tests/`: invented-input engineering tests. R parsing selects named pure helper definitions; no legacy runner is sourced and the calibration-fit branch is disabled.
- `DEPENDENCIES.json` and `DEPENDENCY_LICENCES.json`: static source dependencies and observed installed licence metadata, not a verified historical environment lockfile or a complete transitive-dependency audit.
- `CANDIDATE_MANIFEST.json`: exact companion file hashes and clinical-execution boundaries, not a release signature or an availability statement.

The QC SQL retains its synthetic-only guard. The temporal amendment is an insertion fragment with no independent authorization gate. It must not be run alone. Any future authorized assembler must preserve reviewed source-role, transaction, snapshot, path, identity and cleanup safeguards. No scientific-source guards were changed for this companion.

The legacy training script contains real input/output logic. It is not the final manuscript entrypoint and must not be sourced merely to inspect the code. Included IPW/sensitivity/observation helpers are code context, not evidence that those analyses were completed or reported. Configurable roots and roles do not confer operational authorization.

No patient dataset, individual prediction, trained model, learned preprocessing constants, credentials, actual mapping, clinical run outputs, numerical manuscript tables, figures or internal audit records are bundled.

## What remains for clinical execution or full reproduction

These are limitations of reproduction, **not prerequisites for inspecting or sharing the source companion**:

1. Supply a separately authorized frozen mapping with provenance and identity controls; a schema cannot substitute for its content.
2. Complete and validate portable extraction, capture, PRIMARY endpoint handling, rollback/cleanup and stage20 input/model orchestration without weakening clinical guards.
3. Establish reviewer-local data-access authority, execution configuration, privileges and identity/snapshot controls.
4. Verify the historical environment and end-to-end source/semantic equivalence and obtain actual runtime evidence.

Offline integrity or artificial-test success must not be presented as evidence that these requirements are satisfied or that manuscript results have been reproduced.

## Licence and attribution

`LICENSE` contains the MIT licence for eligible original project material, with copyright attribution to Yi Liu and Qian Sun. `AUTHORS.txt` provides project-code attribution. The offline-review engineering, tests and documentation were prepared with AI assistance and remain subject to author review.

MIT does not relicense R, separately installed dependencies, databases, patient data, third-party mappings, model objects, learned constants or study results. No third-party implementation is vendored. Consult `THIRD_PARTY_NOTICES.txt` and `DEPENDENCY_LICENCES.json`; these are not a legal compatibility certification.

The review-scope description explains capabilities and missing materials; it does not impose a confidential-review-only restriction on the MIT licence. Do not infer database access or clinical execution permission from software licensing. This package is author-identified and must not be described as anonymous.
