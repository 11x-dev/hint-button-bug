1. Locate the file that contains the hint button, one simple way is to right click the hint button in the web browser, then click inspect.  This will automatically show you the html of that in the browser. Now let's search for "bottom-graphic" in our IDE.  You'll notice the same className is in both Lesson.tsx and Puzzles.tsx.  Upon further inspection, you'll find that the hint button is located inside the src/views/Lessons/Puzzles.tsx file.  

![Hint button finding in codebase](https://res.cloudinary.com/dxq77puhi/image/upload/v1748893572/Hint_button_annotation_finding_it_in_the_codebase_5_31_2025_m0ho5g.png)

2. Now that we know which file to debug, let's look at the hint button in the JSX portion of our component. We see that the button's onClick is executing the "showHint" function. Once we find that function, we see a Typescript issue where the findBranchesWithWrongAnswer() method does not exist on "MoveTree".

![showHint method in JSX](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894255/Codesandbox_showHint_1_6_2_2025_vil7yo.png)

![showHint function](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894576/showHint_function_submodule_missing_method_6_2_2025_vfatsu.png)

3. Let's search for this missing method. We find that it's inside the MoveTree file inside our submodule, which is coded in instead of being a submodule.  We notice that the "findBranchesWithWrongAnswer()" method is missing.  How can we find this missing code?  Think about it for a little before proceeding.

![Submodule missing method search](https://res.cloudinary.com/dxq77puhi/image/upload/v1748895258/Finding_submodule_method_search_codesandbox_6_2_2025_vwgku0.png)

4. We can now infer that the problem is we had an out of date submodule, while our other code was up to date.  Let's go look at that code in the submodule.  First, navigate to the main submodule "online-go.com": https://github.com/online-go/online-go.com

Click "Submodules" -> "Goban", and in the search field that says "Go to file", type in "MoveTree.ts", now search the page for "findBranchesWithWrongAnswer()" which is the method we were missing. You should see it just below the "findBranchesWithCorrectAnswer()", around line 1099.

Here's the MoveTree file within the 2nd submodule in case you had issues finding the file: https://github.com/online-go/goban/blob/19f57ea8d2f66b52f06015e67da2cc54df9b4a1c/src/engine/MoveTree.ts

![online-go submodule Github search](https://res.cloudinary.com/dxq77puhi/image/upload/v1748907606/online_go_submodule_bug_1_6_2_2025_jj5sv0.png)
![online-go/goban submodule](https://res.cloudinary.com/dxq77puhi/image/upload/v1748907781/goban_submodule_6_2_2025_fpemgc.png)
![online-go/goban movetree search](https://res.cloudinary.com/dxq77puhi/image/upload/v1748907891/goban_movetree.ts_search_ye2mhv.png)
![online-go/goban find branch with wrong answer found](https://res.cloudinary.com/dxq77puhi/image/upload/v1748907994/findbranches_with_wrong_answer_goban_submodule_6_2_2025_mfxkbv.png)

5. Add the missing method, and associated function to the MoveTree.ts file.  Here's the code you'll need to add.  

```
    private isBranchWithWrongAnswer(branch: MoveTree): boolean {
        if (branch.wrong_answer) {
            return true;
        }
        if (!branch.branches || branch.branches.length === 0) {
            return false;
        }

        return branch.branches.some((item) => this.isBranchWithWrongAnswer(item));
    }
```

```
    findBranchesWithWrongAnswer(): Array<MoveTree> {
        return this.branches.filter((branch) => this.isBranchWithWrongAnswer(branch));
    }
```

6. Alternatively, you could copy paste the entire MoveTree.ts file.
7. Verify both bugs are fixed!

***Conclusion***

First, find the file that is causing the bug, verify that the bug exists and that you can replicate it, then notice there's a Typescript error for a missing method.  Brainstorm solutions, and come to the conclusion that we probably had an out of date submodule, then use this information to look at the submodule, and add the missing code in.

Outside of CodeSandbox where you have access to submodules, you would simply use the following command to update your submodule to the latest code from Github:

```
git submodule update --recursive
```