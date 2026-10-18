# lab-02-task-python
from email.policy import default
import numbers
import numbers


def classify_triangle(a, b, c):
    if a <= 0 or b <= 0 or c<= 0:
        raise ValueError("Invalide triangle.")
    if a + b <= c or a + c <= b or b + c <= a:
        raise ValueError("Invalide triangle")
    if a == b == c:
        return "Equilateral"
    elif a == b or b == c or a == c:
        return "Isosceles"
    else:
        return "Scalene"


def course_result(coursework, final , attendance):
        if attendance < 0.75:
            return "denied"
        if final < 30 :
            return "fail"
        total_score = coursework + final
        if total_score >= 60:
            return "pass"
        else:
            return "fail"


def fizzbuzz(n):
    result = []

    for i in range(1, n + 1):
        if i % 3 == 0 and i % 5 == 0:
            result.append("FizzBuzz")
        elif i % 3 == 0:
            result.append("Fizz")
        elif i % 5 == 0:
            result.append("Buzz")
        else:
            result.append(str(i))
            
    return result


def is_prime(n):
    if n < 2:
        return False
    for i in range ( 2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True


def primes_below(n):
    result = []
    for i in range (2, n):
        if is_prime(i):
            result.append(i)
    return result


def first_repeated(values):
    for i in range(len(values)):
        for j in range(i):
            if values[i] == values[j]:
                return values[i]  
    return None  


def count_pairs(n):
    count = 0
    for i in range(n):
        for j in range(i + 1, n):
            count += 1
    return count


def calculator(command):
    match command.split():
        case ["add", x, y]:
            return int(x) + int(y)
        case ["subtract", x, y]:
            return int(x) - int(y)
        case ["multiply", x, y]:
            return int(x) * int(y)
        case ["divide", x, y]:
            if int(y) == 0:
                raise ValueError("Cannot divide by zero.")
            return int(x) / int(y)
        case _:
            raise ValueError("Invalid command.")



def parse_int(text,default=None):
    try:
        return int(text)
    except ValueError:
        return default


def stats(*numbers):
    if not numbers:
        return  ValueError("At least one number is required.")
    mn = min(numbers)
    mx = max(numbers)
    avg = sum(numbers) / len(numbers)
    return mn, mx, avg


def append_to(item, target=None):
    if target is None:
        target = []
    target.append(item)
    return target   

def make_multiplier(k):
    return lambda x: k * x    


def apply_n(f,x,n):
    result = x
    for _ in range(n):
        result = f(result)
    return result
