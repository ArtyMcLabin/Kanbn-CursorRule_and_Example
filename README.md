# Cursor Kanbn Example + Cursor Rule

Tutorial on how to have a local Kanban board in your Cursor projects, fully operational by LLM. it is based on "Kanbn" extension in Cursor IDE (see below). fully local and git oriented solution. just works better than MCP's to web kanbans as of writing this. 

Note (if you don't want the extension): you technically don't depend on the extension and can skip it,  but it's good to have it for viewing stuff visually and being able to edit it yourself while your LLM cooks your pasta. also i designed the cursor rule around using a board that is initiated by the Kanbn extension, for consistent format. you would need to alter it.

## Tutorial

1. **Install the Kanbn extension** in Cursor IDE:
   
   - Open Cursor IDE
   - Go to Extensions tab (Ctrl+Shift+X)
   - Search for "Kanbn"
   - Install the extension (i am not affiliated with the developer. their github repo is https://github.com/samgiz/vscode-kanbn ) . as of 19jun2025 it seems secure. i have cyber-audited manually the downloaded extension.

2. **Create/Open a board**:
   
   - Use `Ctrl+Shift+P` → "Kanbn: Create Board / Open Board"
   - The board is created locally in `.kanbn_boards/`

3. Download the project rules (from this repo you are reading now), and put it in your project (you technically can create a user rule instead of kanban.mdc , for global useage, but i can't recommend it)

4. I STRONGLY reccomend adding @kanban.mdc to references in your prompt, explicitly. otherwise the LLM will often forget to use it

5. If you see emptiness instead of your board, it means that your LLM violated the board/card structure, tell it "fix it according to @kanban.mdc" and then re-open the board. (close tab first). 

## Example of how it works in practice:

Initial dummy state:

![image](https://github.com/user-attachments/assets/cfb52b4b-79aa-4698-95aa-4a13409e0a8a)

LLM Prompt in Cursor (fresh chat session):  
//update - don't forget tagging @kanban.mdc thugh, screenshots are outdated

![image](https://github.com/user-attachments/assets/17b650b6-ba36-4f2d-a12b-553a4eafc17d)

Result:

![image](https://github.com/user-attachments/assets/b184e042-b442-44bc-af38-e64e42f017ff)


