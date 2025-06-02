The real repo uses a submodule that is located at: online-go.com, which includes another submodule at: online-go.com/submodules/goban. Due to limitations in this platform, submodules are not supported, so the code has been manually added to this coding challenge. The main submodule is located at this repo: https://github.com/online-go/online-go.com

There are 2 bugs with the hint feature, and your task is to fix these bugs!

The hint button is found on this page in the bottom left corner: "/learn-to-play/8/problems/capturing/1"

1. Bug 1: Clicking the hint button only shows the correct next move (green square(s) on the board), but not the wrong next move (red square(s) on the board)
2. Bug 2: Clicking the hint button a second time is not hiding the green and red squares on the board

You'll know you solved the bugs when the following happens:

1. Clicking the hint button shows both green and red squares
2. Clicking the hint button while the green and red squares are visible properly removes them

![Hint button showing red squares on board](https://res.cloudinary.com/dxq77puhi/image/upload/v1748834595/Hint_button_annotation_describing_red_square_showing_up_as_well_5_31_2025_dnulog.png)

![Hint button hiding squares on board](https://github.com/ScriabinOp8No12/hint-button-bug-11xdev/blob/main/Hint%20button%20annotation%20hiding%20squares%20on%20board%205_31_2025.png)