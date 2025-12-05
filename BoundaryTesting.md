| The boundary | Why its a boundary |
| - | - |
| Wall Collisions | we need to be able to handle the real position and when the player actually loses health/dies |
| Health | We need to be able to handle negative health, and make sure it works at weird values like 0 and over max health |
| Timer (for bullet) | We need to be able to handle the transition between being a human and a bullet, the bullet is ha by a timer so it needs to go back to human form at the proper time. |




| Boundary Input | Test Data Example | Expected Outcome |
| - | - | - |
| Health  | -1  | The player dies |
| Health  | 0  | The player dies |
| Health  |  2,147,483,647  | The player’s health is reset back to maxHealth |
| Timer (for bullet) | -1  | The timer ends |
| Timer (for bullet) | 0  | The timer ends |
| Timer (for bullet) | 0.0001  | The timer ends in one frame |
| Timer (for bullet) |  2,147,483,647  | The timers doesn’t reset |
| Wall Collisions | directly in front of wall | player stays alive |
| Wall Collisions | at the exact position of the wall | player dies or loses health |
| Wall Collisions | a few milliseconds after supposed collision | the player should have already died or lost health, is broken if this never happens |
| Wall Collisions | a the corner of the geometry | the player should still lose health or die (only once) |
