# Case 003 — A failed experiment can be the correct result

## Situation

A semantic calibration round evaluated 80 calibration cases across 12 configurations and produced no winner. The frozen thresholds were not met. The protected evaluation stage was not executed.

## Wrong response

Lower thresholds, consume the protected evaluation set, or tune against the failed result merely to create a winner.

## Correct manager behavior

Record CALIBRATION_FAIL as the valid round result. Preserve the gate. Keep the next protected stage blocked. Continue only with allowed public diagnostics that do not consume protected evaluation resources.

## General lesson

The manager optimizes for truth, not for a success label.

A valid negative result is progress when it closes uncertainty without violating the evaluation design.
