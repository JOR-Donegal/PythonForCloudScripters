# Logical and Boolean Operators

George Boole was an Irish scientist who worked out many of the principles of binary logic long before the invention of computers. We refer to this branch of mathematics as Boolean algebra. In binary, there are only two values: zero and one. They can also be represented by the symbols True and False. It is useful to be able to check more than one comparison operator. For this we can use Boolean tests. I tried these out at the Python command prompt, results are in the right-most column.

<table><thead><tr><th width="136.33333333333331">Operator</th><th width="337">Description</th><th>Example</th></tr></thead><tbody><tr><td>and</td><td>Return True if both statements are True.</td><td><p>>>> 4>3 and 1==1 </p><p>True</p></td></tr><tr><td>or</td><td>Return True if either statement is True</td><td><p>>>> 4>3 or 1==2 </p><p>True</p></td></tr><tr><td>not</td><td>Inverts the result</td><td><p>>>> not(4>3 or 1==1) </p><p>False</p></td></tr><tr><td>in</td><td>Returns True if a value is in a sequence</td><td><p>>>> ‘J’ in “JOR” </p><p>True</p></td></tr></tbody></table>

Checking a Boolean value for a variable which is not a Boolean is also possible.&#x20;

A variable which is 0 or None or an empty string “” will evaluate as False.&#x20;

A variable which is and value other than 0 or a string such as “Hello” will evaluate as True.
