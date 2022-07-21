# PythonGenerators


What are generators in Python?

    Generators are a special type of thing in Python that allows us to generate a sequence of values over time. We have actually used a generator
    before: range()
    
    We can use a generator (such as range) to create a list but the difference between using range and craeting a list with 100 entries using range,
    is that when we create the list, the 100 entries are created all at once and stored in memory, while with range, it generates the numbers 
    sequentially, 1 by 1, without holding it in memory. 
    
    Generators allow us to use a special keyword, called yield, that allows us to start/stop while the items are generating.
    
    Lists are iterable, meaning we can loop through it as it contains the __iter__ dunder under the hood, telling the interpreter that this object
    should be iterable. 
    
    Generators are also iterable, meaning we can iterate over them. Generators are subsets of iterables. 
    
    def generator_function():
        for in in range(num):
            yield i 
            
    for item in generator_function(1000):
        print(item)
            
                VS
     
    def make_list(num):
        result = []
        for i in range(num):
            result.append(i*2)
        return result
        
        
    The first function is a generator as it yields i.
    
    You're able to iterate over the generator via the "next" keyword, which essentially tells the generator to move onto the next item to iterate over.
    ex:
    
    g = generator_function(100)
    next(g) -> current state = i*2 (0x2) = 0
    next(g) -> current state = ix2 (1x2) = 2
    print(next(g)) -> current state = ix2 (2x2) = 4
    
    Rather than holding all of the values in a list or writing them to memory, generators save one spot in memory for the current state, or the current
    iteration. Then calling the next keyword instructs the generator to move to the next value to be iterated over.
    
    This makes using generators more performant than using lists.
    
 For more information on generators:
 https://www.programiz.com/python-programming/generator
 
 Link to Repl.it demonstrating performance difference between lists and generators:
 https://replit.com/@AutomationApe/GeneratorsPerformance#main.py
