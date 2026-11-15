# Repository editor review-fix evidence

Source commit: `3ae1326f6ea09e34d73250c2d7f698bf7e8e605c` (PR7095).

Six browser captures of synthetic repository/link data: desktop detail and phone Large-text detail/editor, each in light and dark. The capture clips are taken directly by Chrome at the rendered component bounds; no image editing is applied. All six were visually inspected. The complete rendered check covers six viewport/theme/text-size combinations and three deferred response sequences (255 checks), including a background request crossing open/close, a fresh close-read while the old response is pending, a late404, and a later save using the refreshed revision.

The API fixture uses isolated Manager/PostgreSQL state built from `b8b1d7607`; its association replies and version signals are synthetic for the browser regression. The current Web source is tested separately from the backend build/regressions. No production account, engine or live validation model is used.

Web full suite: 13006 passed, one optional live compatibility test skipped. Standard build/typecheck/lint and docs/privacy checks pass. Backend first-read and real-lock regressions pass; the complete assistant suite retains a failing PromptSizeRatchet (also failing on clean main, with additional association-tool growth on this PR). These captures do not establish a green backend suite or hosted CI.

Human screenshot review remains required before merging the overall feature.
