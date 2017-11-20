# CPSC 449 - Assignment 2: Quad Tree in Haskell

-- CPSC 449: Programming Paradigms
-- Professor: Dr. Ben Stephenson
-- University of Calgary
--
-- Assignment 2
-- Evan Loughlin
-- 00503393
-- June 19, 2017

-- Description:
-- In this assignment, a quad tree data structure is used to store data with 
-- a two-dimensional structure. A quad tree has internal nodes that have up to
-- four children. Each leaf node contains data for the region that it 
-- represents. In particular, each of the four nodes represents the colour 
-- of a single square. Leaf nodes represent data, as follows:
--
--          First Node: Top Left (TL)
--          Second Node: Top Right (TR)
--          Third Node: Bottom Left (BL)
--          Fourth Node: Bottom Right (BR)
--                     ___                      ___________________
--                    /   \                    |         |         |
--                 __|     |_                  |  TL     |  TR     |
--                /   \___/  \                 | (R,G,B) | (R,G,B) |
--               /     | |    \                |         |         |
--              /      | |     \               |---------|---------|
--             /       | |      \              |         |         |
--            /        | |       \             |  BL     |  BR     |
--           /        _| |_       \            | (R,G,B) | (R,G,B) |
--          /        |    |        \           |_________|_________|
--      ___/     ___ |    |___      \___
--     /   \    /   \     /   \     /   \
--    |  TL |  |  TR |   |  BL |   |  BR |
--     \___/    \___/     \___/     \___/
--
--
--  Each leaf node also contains three Int values (Red, Green, Blue), which 
-- represents the colour of that region. If the entire region is of a single
-- colour, then that node has no children, otherwise, it is recursively
-- called until each unique pixel is correctly coloured.
--
-- (For example, a pure black square would contain (R,G,B) = (0,0,0), and have
-- no children nodes.
-- 
-- NOTE: Bonus Rectangle image was attempted, although the result is buggy due to a logic error.



******* INSTRUCTIONS TO RUN *******

1) Load a2.hs using a Haskell program such as WinGHCi
2) Run "main"
3) Output is in quadtree.html

Note: To change the image that is rotated, change the name of the file in line 413 of a2.hs. This program runs only on square images, and is most efficient with images that contain large areas of the same colour.