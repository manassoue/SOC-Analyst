# Runbook — IPS Tuning & False Positive Management (Lab)

## Goal
Enable prevention safely: block true attacks while minimizing disruption from false positives.

## Before enabling blocking (baseline)
- Identify critical allowed services (updates, DNS, web browsing)
- Capture baseline traffic (Zeek/pcap) for comparison
- Start with IDS mode to observe alert volume

## Move from IDS → IPS (staged)
1) Enable IPS in monitor-only / alert-first mode (if possible)
2) Review top noisy signatures
3) Suppress/threshold noisy rules that are clearly benign
4) Enable blocking for high-confidence signatures

## When something breaks (false positive)
Questions:
- What exactly was blocked? (src/dst, port, rule ID, signature)
- Is it expected business traffic or suspicious?
- Is this a known-good host/domain?

Actions:
- Create a narrow exception (host/service specific)
- Reduce rule sensitivity (thresholding) instead of global disable when possible
- Document: what changed + why + evidence

## Evidence to store in portfolio
- Before/after alert volume
- Example blocked event (alert log)
- Example tuning change (rule disabled/thresholded) + justification
