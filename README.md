RGB Game of Life

A cellular automota based on Conway's Game of Life.

---

Simulates the RGB Game of Life on a Torus.

There are three classes of life; R, G, and B.

The food chain is cyclic: R preys on G, G preys on B, and B preys on R.

Terminology is as follows:

   * A **cell** is the smallest element in the game of life.
   * A cell can be **live** (R, G, or B) or **dead**.
   * A **neighbour** is a live cell adjacent to a cell in question.
   * A**predatory** neighbour of a cell a neighbour that preys on it. (E.g. B is a predator of R.)
   * A **prey** neighbour of a cell is a neighbour that cell preys on. (E.g. R preys on G.)
   * A **like** neighbour is a cell of the same kind. (E.g. R is like R.)
   * A **friendly** neighbour is a cell that is like or prey. (E.g. R and G are friendly to R.)
   * A **non-prey** neighbour is a cell that is like or predator. (E.g. R and B are non-prey neighbours of R.)

Live cells continue to live so long as they have ample friendly neighbours. Predatory cells can convert a live cell or kill it. The rules for live cells are as follows:

   * **Overopulation**: Any live cell with 4 like neighbours dies
   * **Starvation**: Any live cell with fewer than two friendly neighbours dies
   * **Encroachment**: Friendly neighbours of a live cell must outnumber predatory neighbors, else it is subject to encroachment.
   * **Conversion**: Any live cell subject to encroachment with three or more non-prey neighbours is converted to be a cell of it's own predator.
   * **Stifling**: Any live cell subject to encroachment but not conversion dies.

Dead cells can become living cells subject to the following rules:

   * **Reproduction**: A dead cell with three neighbours of the same class becomes a living cell of the same class.
   * **Expansion**: A dead cell with three or four neighbours of exactly two different classes (one predatory class and one prey class) is converted to the predatory class if the prey neighbours do not outnumber the predatory neighbours.

 
---

Simulates Conway's Game of Life on a torus.

CLI usage:

    -s --savepic    Save a pic of each iteration (e.g. 000.png, 001.png, ...)
    -l --loadpic    Load the board from a black and white image.
    -i --iterate n  Iterate n times, print the board at each iteration
       --noprint    Don't print the board to console

---

tools.py

    