# [freeCodeCamp Scientific Computing with Python](https://www.freecodecamp.org/learn/scientific-computing-with-python)

## [Arithmetic-Formatter](https://www.freecodecamp.org/learn/scientific-computing-with-python/scientific-computing-with-python-projects/arithmetic-formatter)

My git repo: https://github.com/Raff1010X/01.Roadmap

```python
def arithmetic_arranger(problems, show_answers=False):
    result = [''] * 4

    if len(problems) > 5:
        return 'Error: Too many problems.'

    for index, problem in enumerate(problems):
        numbers = problem.split()
        
        if numbers[1] != "+" and numbers[1] != "-":
            return "Error: Operator must be '+' or '-'."
        if not numbers[0].isdigit() or not numbers[2].isdigit():
            return 'Error: Numbers must only contain digits.'
        if len(numbers[0]) > 4 or len(numbers[2]) > 4:
            return 'Error: Numbers cannot be more than four digits.'

        max_len = max(len(number) for number in numbers) + 2
        inline_space = ' ' * (max_len - len(numbers[2]) - 1)
        end = ' ' * 4
        
        if index == len(problems) - 1: 
            end = ''
        
        result[0] += numbers[0].rjust(max_len) + end
        result[1] += f'{numbers[1]}{inline_space}{numbers[2]}'.rjust(max_len) + end
        result[2] += '------'[:max_len] + end
        result[3] += str(eval(problem)).rjust(max_len)  + end

    return '\n'.join(result[:4] if show_answers else result[:3])
```
