### Install

~~~bash
$ git clone https://github.com/sdegutis/hydra-grid.git ~/.hydra/ext/grid
~~~

### Documentation

~~~lua
-- Usage:

require "ext.grid.init"

-- The grid is an partition of your screen; by default it is 3x2, i.e. 3 cells wide by 2 cells tall.
-- The height is always fixed to 2 cells.
--
-- Grid cells are just a table with keys: x, y, w, h
-- For a grid of 2x2:
--   * a cell {x=0, y=0, w=1, h=1} will be in the upper-left corner
--   * a cell {x=1, y=0, w=1, h=1} will be in the upper-right corner
--   * and so on...
--
-- The core functions:

function ext.grid.get(win)                  -- Gets the cell this window is on
function ext.grid.set(win, grid, screen)    -- Sets the cell this window should be on
function ext.grid.snap(win)                 -- Snaps the window into a cell
function ext.grid.adjustwidth(by)           -- Widens the grid by the given number of cells; may be negative

-- The convenience functions:

function ext.grid.adjust_focused_window(fn) -- Passes the focused window's cell to fn and uses the result as its new cell
function ext.grid.maximize_window()         -- Maximizes the focused window along the given cell
function ext.grid.pushwindow_nextscreen()   -- Moves the focused window to the next screen, using its current cell on that screen
function ext.grid.pushwindow_prevscreen()   -- Moves the focused window to the previous screen, using its current cell on that screen
function ext.grid.pushwindow_left()         -- Moves the focused window one cell to the left
function ext.grid.pushwindow_right()        -- Moves the focused window one cell to the right
function ext.grid.resizewindow_wider()      -- Resizes the focused window's right side to be one cell wider,
function ext.grid.resizewindow_thinner()    -- Resizes the focused window's right side to be one cell thinner,
function ext.grid.pushwindow_down()         -- Moves the focused window to the bottom half of the screen
function ext.grid.pushwindow_up()           -- Moves the focused window to the top half of the screen
function ext.grid.resizewindow_taller()     -- Resizes the focused window so its height is 2 cells

-- The variables

ext.grid.MARGINX = 5    -- The margin between each window horizontally
ext.grid.MARGINY = 5    -- The margin between each window vertically
ext.grid.GRIDWIDTH = 3  -- The number of cells wide the grid is
~~~
