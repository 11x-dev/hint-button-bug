1. Locate the file that contains the hint button, one simple way is to right click the hint button in the web browser, then click inspect.  This will automatically show you the html of that in the browser. Now let's search for "bottom-graphic" in our IDE.  You'll notice the same className is in both Lesson.tsx and Puzzles.tsx.  Upon further inspection, you'll find that the hint button is located inside the Puzzles.tsx file.  

![Hint button finding in codebase](https://res.cloudinary.com/dxq77puhi/image/upload/v1748893572/Hint_button_annotation_finding_it_in_the_codebase_5_31_2025_m0ho5g.png)

2. Now that we know which file to debug, let's look at the hint button in the JSX portion of our component. We see that the button's onClick is executing the "showHint" function. Once we find that function, we see an issue where the findBranchesWithWrongAnswer() method does not exist on "MoveTree", which is inside our submodule.

![Hint button finding in codebase](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894255/Codesandbox_showHint_1_6_2_2025_vil7yo.png)

![Hint button finding in codebase](https://res.cloudinary.com/dxq77puhi/image/upload/v1748894576/showHint_function_submodule_missing_method_6_2_2025_vfatsu.png)


