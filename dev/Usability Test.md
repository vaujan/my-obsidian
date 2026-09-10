## findings
- The main app's layout (overview) looks sucks. The action buttons is not highlighted, there is not true workflow that can be done only via keyboard
    - But we have two different main actions: `Add item` and `Add note`
    - For "**Add Note**" Maybe it's this: `ctrl + n` -> `Type a content` -> `Done`
- The floating sidebar should only occur in the smallest breakpoint
- In the narrowest breakpoint, it works flawlessly. But the chevron icon button should be changed to a hamburger buttons (stacked horizontal lines)
- Languages support: 
    - Vocabulary support in the to check typos
    - User should able to pick which languages that their content supports
- Separated font system for Note content. This one should be separated from the UI font and the code font (which is obvious)
    - Some user may prefer to have their content presented in serif font, while keeping the rest of the app the way it is (code still use the dedicated code font)
- For our current zen mode, always show the 'quit zen mode' button
- Setting still sucks, it should be integrated as a separate window like how obsidian does it
- The slash menu still doesn't open, here's I found it
    - I'm in live mode, then I press `/`. Nothing happened. Is this expected?  
- The horizontal scrollbar in code block, still appears in the rails and overview card (we don't open in and is not in detail pane)
- Sidebar toggle doesn't works in when detail pane is opened

#### 11/09/2026
- The icon buttons (sort and filter button, new note button, and new item button) should be improved to show the 'lifted' state better
    - For instance, our filter button shows a 

## need to be grilled
- Table and images editing/writing experiences in live mode should be improved. The user should able to write table and images content expecting anything to break 
- Inline formatting when selecting texts using cursor
    - Why I need to explicitly says 'using cursor', because selecting it via Vim's visual mode doesn't seem to be *intuitive*
- Unfolding lines and trailing lines that shows our the indentation levels
    - The trailing lines features for nested content appear in our current source mode
    - We just want it in our current live mode
- In vim mode, should pressing `Ctrl + B` in note editing/writing bold the text? How should we work with other inline formatting while in Vim mode? How's obsidian implementing it? 
- Persistent caret positions when switching between modes
    - Let say we're in live mode and we select multiple lines, switching to read mode and then back to live mode, we should the previous selected texts. This interaction appears in Obsidian and it's good