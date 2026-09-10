# 10/09/2026 

- Horizontal scrollbar in notes still visible and it only scroll the app horizontally very little. The scrollbar positions in overview should be hidden
- Remove unnecessary elements:
    - Border/separator between rails and detail pane
    - Background differences between detail pane's header and its body should be unified
        - We should use the darker background variant for the detail pane, so we can se the content more clearly
        - When opening item other than a note, the distinctive side pane that contains all of our links and images information and metadata is quite out of place
-  Floating sidebar design adjustment:
    - Instead of creating a UI switch, can we make it **floating**, where it levitates on top of the other contents 
- **a11y** issue: 
    - Sidebar item's active state in window material mode activated looks different than if we don't have the window material option activated
- Bring back slash menu `/` 
- Simplify our search functionality
    - We should integrate a more translucency *vibe*, like how context menu or dropdown menu work with it
    - For the right pane, lets remove the header 
    - For the left pane, remove leading big icon that indicates the type
    - Discuss with me the cost of implementing these redesign points, and propose fix
---

- Inline formatting when selecting texts
- Discuss with me the cost of implementing these redesign points, and propose fix
- Unfolding lines and trailing lines that shows our the indentation levels
    - The trailing lines features for nested content appear in our current source mode
    - We just want it in our current live mode
- In vim mode, should pressing `Ctrl + B` in note editing/writing bold the text? How should we work with other inline formatting while in Vim mode? How's obsidian implementing it? 
