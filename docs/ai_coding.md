These are some useful AI prompts to help you while you code:

- create a function with type hints and docstring using google style called { } that { }
- create the tests for the function { } adding type hints and following the AAA style where the Act section is represented contains a returns = (thing to test) line or if the function to test doesn't return any value append an # act comment at the end of the line. Use paragraphs to separate the AAA blocks and don't add comments inside the tests for the sections

If you use [espanso](espanso.md) you can simplify the filling up of these prompts on the AI chats. For example:

```yaml
---
matches:
  - trigger: :function
    form: |
      Create a function with type hints and docstring using google style called [[name]] that:
      [[text]] 
    form_fields:
      text:
        multiline: true
  - trigger: :tweak
    form: |
      Tweak the next code:
      [[code]] 

      So that: 

      [[text]] 
    form_fields:
      text:
        multiline: true
      code:
        multiline: true
  - trigger: :test
    form: |
      create the tests for the function:
      [[text]] 

      Following the next guidelines:

      - Add type hints 
      - Follow the AAA style 
      - In the Act section if the function to test returns a value always name that variable returns. If the function to test doesn't return any value append an # act comment at the end of the line. 
      - Use paragraphs to separate the AAA blocks and don't add comments like # Arrange or # Act or # Act/Assert or # Assert

    form_fields:
      text:
        multiline: true
  - trigger: :refactor
    form: |
     Refactor the next code
     [[code]] 
     with the next conditions
     [[conditions]]
    form_fields:
      code:
        multiline: true
      conditions:
        multiline: true
```
