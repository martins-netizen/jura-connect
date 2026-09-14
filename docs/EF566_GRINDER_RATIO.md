# EF566 grinder-ratio hardware verification

On 2026-09-08, a contributor tested the two extreme
`GRINDER_RATIO` values on a JURA GIGA 6 using the bundled EF566
profile. The product was Espresso (`Code="02"`), started through the
Home Assistant integration and this library's normal
`ProductDef.build_recipe_hex()` path.

| Selected item | F2 value | Physical observation |
| --- | --- | --- |
| `100_0` | `00` | Beans moved only in the left hopper; the drink completed normally. |
| `0_100` | `04` | Beans moved only in the right hopper; the drink completed normally. |

Both brews completed without an error and the preparation matched the
selected hopper. The contributor watched the beans in both hoppers
during grinding, so this verifies that EF566 names the ratio
**left:right**, including both endpoints.

No raw wire trace was recorded for these two brews. This is therefore
an end-to-end physical observation, not a verbatim frame capture. The
corresponding recipe blobs produced by the profile are covered by unit
tests.
