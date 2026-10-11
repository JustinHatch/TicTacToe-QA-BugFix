# Tic for Tot test cases

These nine existing scenarios retain their recorded historical Fail/Pass outcomes. The reset description has been corrected to distinguish visual clearing from internal state reset. Reproduction steps use the actual **Restart Playtime** label and the game's bottle/baby players. Clarified steps are not claims of a new full test run.

Number squares 1–9 from left to right, top to bottom. Each scenario starts with a fresh page/game. For a completed game, dismiss the result using **Play Again!** to begin another round.

| Test Case ID | Scenario | Steps | Expected result | Recorded actual result | Recorded status |
| --- | --- | --- | --- | --- | --- |
| TC-001 | Reset allows reuse of occupied cells — broken version | Click square 1 → Restart Playtime → click square 1 again | Visible board and internal state reset; square 1 accepts a new mark | Visible marks clear, but previously occupied square rejects input | Fail |
| TC-002 | Reset allows reuse after the fix | In fixed version, click square 1 → Restart Playtime → click square 1 again | Square accepts a new mark and play continues normally | Board resets and accepts input | Pass |
| TC-003 | Detect horizontal win | Alternate moves at squares 1, 4, 2, 5, 3 | Bottle player wins across the top row; win message appears | Win message displayed | Pass |
| TC-004 | Prevent moves after a win | Complete the win sequence above → attempt another square before starting a new round | No additional game moves accepted | No additional moves allowed | Pass |
| TC-005 | Detect draw | Alternate moves at squares 1, 2, 3, 5, 4, 6, 8, 7, 9 | Draw message appears without a winner | Draw message displayed | Pass |
| TC-006 | Prevent move on an occupied square | Click square 1 twice without resetting | Second click does not replace the mark or change the turn | Second move ignored | Pass |
| TC-007 | Alternate player turns | Click square 1, then square 2 | Bottle and baby players alternate | Turns switch correctly | Pass |
| TC-008 | Render board on desktop | Open game in desktop browser | Grid and UI display cleanly and centered | Layout appears as expected | Pass |
| TC-009 | Restart control is visible | Load game and locate Restart Playtime | Control is visible and clickable | Button visible and clickable | Pass |

See the [bug report](BugReport.md) for the reset-state defect. The TestRail screenshot contains one passed reset case; it does not independently verify all nine rows. Original project and screenshot dates remain unchanged.
