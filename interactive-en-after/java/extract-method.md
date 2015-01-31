Let's take a look at <i>Extract Method</i> using this function as an example.

Begin with a very, very simple case. The code for displaying a banner can be easily extracted via copy and paste.

Replace the code in the original method with a call to the new method.

Let's compile to check for errors in code.

Now things get trickier. The problem with extracting complex methods is hidden in local variables.

Let's extract the method for displaying the details.

Let's launch the compiler.

Yes, we really did move the <code>outstanding</code> variable out of the original method but no value is assigned to it in the new method.

The better solution is to make the variable a method parameter and pass its value from the original method.

Let's launch the compiler.

Now on to extraction of the code for calculating amounts outstanding.

Additional difficulties here are caused by local variables to which new values are assigned. It is quite possible that these values are used in the remaining code of the main method.

If a value is assigned to the parameter, you can get rid of this by using Remove Assignments to Parameters.

Check each variable.

Here, the problem is caused by the <code>outstanding</code> variable, which is then used in the <code>PrintDetails()</code> call.

Pass it back to the original method.

Let's perform the final compilation and testing.

The refactoring is complete! You can compare the old and new code, if you like.