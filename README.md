*******************
***Initial Setup***
*******************

Clone the repo

```
git clone https://github.com/ScriabinOp8No12/hint-button-bug-11xdev.git
```

Navigate to the root of the project:

```
cd hint-button-bug-11xdev
```

Install packages and start the frontend server:

```
yarn install && npm run dev
```

View localhost on port 18888

```
localhost:18888
```


************************
***Hints and Solution***
************************

If you are stuck and need a hint or want to see a possible solution, navigate to this document [here](/Hints-And-Solutions.md)

If you think there are better hints or there are alternative or better solutions, please email me at nharwit@gmail.com

**********************
***Coding Challenge***
**********************

The real codebase uses a submodule that is located at online-go.com, which includes another submodule at online-go.com/submodules/goban. For simplicity, the code has been manually added. The main online-go.com submodule can be found at https://github.com/online-go/online-go.com

There are 2 bugs with the hint feature:

1. Bug 1: Clicking the hint button only shows the correct next move (green squares on the board), but not the wrong next move (red squares on the board)
2. Bug 2: Clicking the hint button a second time is not hiding the green and red squares on the board

The hint button is found on this page in the bottom left corner: 

```
localhost:18888/learn-to-play/8/problems/capturing/1"
```

************************
***Estimated Time***
************************

Estimated time for this bug fix is 30 minutes - 2 hours.  If you are stuck for more than 30 minutes, you could consider looking at the hint.  

**********************
**Requirements**
**********************

1. Clicking the hint button shows both green and red squares
2. Clicking the hint button while the green and red squares are visible properly removes them

This was a real bug from a real production codebase!  Feel free to use any resources you want on this coding challenge, have fun!  

![Hint button showing red squares on board](https://res.cloudinary.com/dxq77puhi/image/upload/v1749016613/Hint_bug_screenshot_1_11xdev_kfntqf.png)

![Hint button hiding squares on board](https://res.cloudinary.com/dxq77puhi/image/upload/v1749016615/Hint_bug_screenshot_2_11xdev_tbasui.png)

