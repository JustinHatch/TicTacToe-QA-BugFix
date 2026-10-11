# Reset clears visible marks but leaves previously occupied cells unusable

**Application:** Tic for Tot browser game.  
**Affected example:** `broken_version/index.html`.  
**Corrected example:** `fixed_version/index.html`.  
**Impact:** a board can appear empty while rejecting moves, preventing a normal new round.

## Reproduction

1. Open the broken HTML file in a browser.
2. Click the top-left square and confirm a player mark appears.
3. Click **Restart Playtime**; the visible mark disappears.
4. Click the top-left square again.

**Expected:** the square accepts the first player's mark and the next turn begins.  
**Actual:** the square remains visually empty and rejects the move because its previous value remains in the internal board array.

The same state problem affects starting a new round after a completed game. The screenshot notes report reproduction in Chrome and Firefox; exact historical browser versions were not recorded in the supplied evidence.

## Cause and correction

`resetGame()` in the broken example clears cell text and styles but leaves the `board` array populated. The existing fixed example reinitializes that array to nine empty strings, resets the active player/game state, and clears the visible cells.

## Verification evidence

- [TestRail steps and expected result](screenshots/tik%20for%20tot%20test%20rail%20screenshot%20fixed%20date%201.png)
- [Recorded passed reset test](screenshots/tik%20for%20tot%20test%20rail%20fixed%20screenshot%202.png)
- [Existing test-case record](TestCases.md)

For a focused recheck, repeat the steps on the fixed version and verify that the previously occupied square accepts input. Do not treat the single passed TestRail reset case as proof that every game scenario was executed in that run. Original evidence and dates are preserved.
