# Test a test

Next, I force an error. I edit **test\_formatter.py** and mangle the test string.

```
def test_upper(self):
    test_text = "John ORaw"
    result = formatter.convert_upper(test_text)
    self.assertEqual(result, "JoHN ORAW")
```

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

The test failed as expected and the location of the error was pointed out to me. There are many different test types you could use in unittest, look through and understand the flexibility you have. 
