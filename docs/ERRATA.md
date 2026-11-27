# Errata & Notes on the Book and CML Lab Files

This document summarizes errata and supplementary notes regarding differences between the initial configuration listings in the book and the CML YAML files (or their runtime display in CML) in this repository.

---

## Lab-07: `ip routing` on SW1 (Note)

- **Book listing**: The initial configuration for `[SW1]` includes `ip routing`.
- **Behavior in CML**: Because the `ioll2-xe` image used for SW1 has `ip routing` enabled by default, it is omitted from `show running-config`.
- **Action required**: None. Both the routed port (`no switchport`) and IP routing are active by default; you do not need to re-enter `ip routing` or change the node definition. Proceed with the exercise as written.

---

## Lab-31: EEM Timer Syntax Correction (Errata)

- **Target**: Initial configuration of Lab-31 (OSPFv2 Broadcast / Incomplete DR Failover)
- **Issue**: The command `event timer countdown time 240` listed in the book's initial configuration can be parsed incompletely without a timer name when the node boots in CML.
- **Action taken**: `labs/Lab-31.yaml` in this repository has already been updated to explicitly specify the timer name:

```text
event timer countdown name PRIO time 240
```

*Note: If you import `labs/Lab-31.yaml` directly from this repository, no manual fix is required.*