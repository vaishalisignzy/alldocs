---
description: This page covers the description of the FieldVerificationResult enumeration
---

# FieldVerificationResult

`FieldVerificationResult` enumeration contains identifiers determining verification and comparison of text fields.

```kotlin
object FieldVerificationResult {
    const val DISABLED = 0
    const val VERIFIED = 1
    const val NOT_VERIFIED = 2
    const val COMPARE_TRUE = 3
    const val COMPARE_FALSE = 4
}
```



| Constant           | Description                              |
| ------------------ | ---------------------------------------- |
| **DISABLED**       | comparison wasn't done, result undefined |
| **VERIFIED**       | verification passed                      |
| **NOT\_VERIFIED**  | verification failed                      |
| **COMPARE\_TRUE**  | positive comparison result               |
| **COMPARE\_FALSE** | negative comparison result               |
