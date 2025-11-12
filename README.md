
# Directory Tree Simulator

A command-line program that simulates a hierarchical file system using Binary Search Trees (BSTs) for efficient organization and retrieval. This project demonstrates core data structures and algorithms by modeling a common real-world system: a directory tree.

## Features

*   **BST-Based Organization:** Files and folders are stored and sorted within their parent directory using two separate Binary Search Trees:
    *   **One BST for Files:** Sorted by file name.
    *   **One BST for Subfolders:** Sorted by folder name.
*   **Add Items:** Dynamically add new files or folders to any point in the directory tree.
*   **Delete Items:** Remove files or folders. Deleting a folder also removes all of its contents recursively.
*   **Efficient Searching:** Leverages the BST structure for fast lookups by name and type within any given directory.
*   **Tree Traversal:** Display the entire directory structure using an in-order traversal, producing a sorted, visually intuitive tree view.

## How It Works

The core idea is that every `Directory` (folder) object in the tree contains:

1.  **`filesBST`**: A Binary Search Tree where each node represents a `File`. The nodes are sorted based on the file's name.
2.  **`subdirectoriesBST`**: A Binary Search Tree where each node represents a `Directory` (a subfolder). The nodes are sorted based on the folder's name.

This structure allows for efficient, sorted storage and retrieval. When you navigate to a directory, finding a file or subfolder is a fast O(log n) operation on average, thanks to the BST.

### Example Structure Visualization

```
root/
├── Documents/ (subdirectoriesBST)
│   ├── Essays/ (subdirectoriesBST)
│   │   ├── draft.txt (filesBST)
│   │   └── final.pdf (filesBST)
│   └── Resume.doc (filesBST)
├── Pictures/ (subdirectoriesBST)
│   ├── vacation.jpg (filesBST)
│   └── wallpaper.png (filesBST)
└── readme.txt (filesBST)
```

## Why Binary Search Trees?

Using BSTs for this simulator provides several key benefits:
*   **Maintained Order:** Items are always stored in sorted order, making listings predictable and clean.
*   **Efficient Operations:** Common actions like adding, deleting, and searching have an average time complexity of **O(log n)**, which is significantly faster than a linear list, especially as the number of items grows.
*   **Educational Value:** This project is an excellent practical application of BSTs, recursion, and tree traversal algorithms (in-order, pre-order) for managing hierarchical data.

## Installation & Compilation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YOUR_USERNAME/directory-tree-simulator.git
    cd directory-tree-simulator
    ```

2.  **Compile the source code:** (Example using g++)
    ```bash
    g++ -std=c++17 -o simulator main.cpp Directory.cpp File.cpp BST.cpp
    ```

## Usage

Run the executable and use the interactive menu to manage your directory tree.

```bash
./simulator
```

### Example Commands (within the program):
- `add file /Documents/report.txt`
- `add folder /Pictures/Holidays`
- `delete /Documents/old_draft.txt`
- `list /` (to display the entire tree from the root)
- `exit`

## Project Structure

```
directory-tree-simulator/
├── src/
│   ├── main.cpp          # Entry point and user interface
│   ├── Directory.h/cpp   # Directory class with two BSTs
│   ├── File.h/cpp        # File class
│   ├── BST.h/cpp         # Generic Binary Search Tree implementation
│   └── TreeNode.h/cpp    # Node class for the BST
├── README.md
└── Makefile              (Optional, for easier compilation)
```

## Future Enhancements

*   Implement a Red-Black Tree or AVL Tree for self-balancing, guaranteeing O(log n) performance.
*   Add move/copy functionality for files and folders.
*   Search for a file/folder by name across the entire filesystem.
*   Calculate and display the total size of a directory.
*   Persist the directory tree to a file upon exit and load it on startup.

## License

This project is licensed under the MIT License.
