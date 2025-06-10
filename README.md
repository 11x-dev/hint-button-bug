***Hint***

1. Locate the file that contains the hint button, one simple way is to right click the hint button in the web browser, then click inspect.  This will automatically show you the html for that element in the browser. Now let's search for "bottom-graphic" in our IDE.  You'll notice the same className is in both Lesson.tsx and Puzzles.tsx.  Upon further inspection, you'll find that the hint button is located inside the src/views/Lessons/Puzzles.tsx file.  

![Hint button finding in codebase](https://res.cloudinary.com/dxq77puhi/image/upload/v1748893572/Hint_button_annotation_finding_it_in_the_codebase_5_31_2025_m0ho5g.png)

2. Now that we know which file to debug, let's look at the hint button in the JSX portion of our component. We see that the button's onClick is executing the "showHint" function. Once we find that function, we see a Typescript issue where the findBranchesWithWrongAnswer() method does not exist on "MoveTree".  It's not finding the method in the MoveTree.ts file at line 1081.  

To confirm that the method is actually missing, if we are using vscode, we can hold the ctrl key (cmd key for mac), then click on the findBranchesWithCorrectAnswer() method, as it's similar and in the same MoveTree.ts file.  Alternatively, you could use ctrl + p (cmd + p for mac) and type in movetree.  Then click the MoveTree.ts file and verify that our findBranchesWithWrongAnswer() method does not exist there.

![showHint method in JSX](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894255/Codesandbox_showHint_1_6_2_2025_vil7yo.png)

![showHint function](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894576/showHint_function_submodule_missing_method_6_2_2025_vfatsu.png)

We are calling the findBranchesWithWrongAnswer() method from the integrated online-go.com code and it doesn't exist.

The online-go.com code has been hardcoded into this coding challenge. You can find the original source code and its inner submodules at: https://github.com/online-go/online-go.com

With this knowledge, figure out where the missing method should be located, and then add the code back in.

![showHint function](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894576/showHint_function_submodule_missing_method_6_2_2025_vfatsu.png)