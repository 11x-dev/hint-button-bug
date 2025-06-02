***CodeSandbox Setup***:

Codesandbox should automatically install the packages and run the dev server.  If not, navigate to the hamburger menu on the left, and click "Terminal" -> then click "New Terminal"

Use the following command from the root of the project (where you should be by default)

```
yarn install && npm run dev
```

If the server just needs to be started, instead of the yarn install portion, you can simply do:

```
npm run dev
```

![Codesandbox setup](https://res.cloudinary.com/dxq77puhi/image/upload/v1748840199/Codesandbox_terminal_navigation_6_1_2025_fyccxv.png)

***Viewing Website***:

Assuming the above succeeded and the dev server is running, you'll want to view the website in a separate tab, as the preview will likely be either too small, or appear too squished.  First, locate the port the server is running on, by clicking "PORTS" which is to the right of "TERMINAL". Locate the port that ends with "18888".  Right click it, and click "Open in Browser" -> Click "Open" to confirm.

![Codesandbox port 18888](https://res.cloudinary.com/dxq77puhi/image/upload/v1748892742/18888_port_11xdev_codesandbox_annotation_6_2_2025_xilnrp.png)

If you want to try opening the preview in CodeSandbox (perhaps you have a large monitor), navigate to the "CodeSandbox" section in the left navigation, which is just below the search icon, hover over the 18888 which is under the "Previews" section, and click the triangle icon to load the preview.

![Codesandbox preview](https://res.cloudinary.com/dxq77puhi/image/upload/v1748892947/Codesandbox_18888_preview_annotation_6_2_2025_jlkur4.png)

***Coding Challenge***:

The real repo uses a submodule that is located at: online-go.com, which includes another submodule at: online-go.com/submodules/goban. Due to limitations in this platform, submodules are not supported, so the code has been manually added. The main "online-go.com" submodule can be found at: https://github.com/online-go/online-go.com

There are 2 bugs with the hint feature, and your task is to fix these bugs!

The hint button is found on this page in the bottom left corner: "/learn-to-play/8/problems/capturing/1"

1. Bug 1: Clicking the hint button only shows the correct next move (green square(s) on the board), but not the wrong next move (red square(s) on the board)
2. Bug 2: Clicking the hint button a second time is not hiding the green and red squares on the board

You'll know you solved the bugs when the following happens:

1. Clicking the hint button shows both green and red squares
2. Clicking the hint button while the green and red squares are visible properly removes them

![Hint button showing red squares on board](https://res.cloudinary.com/dxq77puhi/image/upload/v1748834595/Hint_button_annotation_describing_red_square_showing_up_as_well_5_31_2025_dnulog.png)

![Hint button hiding squares on board](https://res.cloudinary.com/dxq77puhi/image/upload/v1748834686/Hint_button_annotation_hiding_squares_on_board_5_31_2025_nbm8m0.png)