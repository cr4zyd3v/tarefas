Tarefa 1 - URL : https://www.hackerrank.com/challenges/validate-list-of-email-address-with-filter/problem

Código:
```
def fun(s):
    if not s:
        return False
    if s.count("@") != 1:
        return False
    if "." in s:
        extension = s.split(".")[1]
        if len(extension) <= 3:
            extensionLen = len(extension)
        else:
            return False
    else:
        return False
    if "@" in s:
        username = s.split("@")[0]
        website = s.split("@")[1][:-extensionLen-1]
        if username.isalpha() or username.isdigit() or "-" in s or "_" in s:
            for character in website:
                if character.isalpha() or character.isdigit():
                    continue
                else:
                    return False
            return True
        else:
            return False

    else:
        return False

def filter_mail(emails):
    return list(filter(fun, emails))

if __name__ == '__main__':
    n = int(input())
    emails = []
    for _ in range(n):
        emails.append(input())

    filtered_emails = filter_mail(emails)
    filtered_emails.sort()
    print(filtered_emails)

```


Tarefa 2 - URL: https://www.hackerrank.com/challenges/reduce-function/problem
Código:
```
from fractions import Fraction
from functools import reduce

def product(fracs):
    t = reduce(lambda x, y: x*y, fracs)
    return t.numerator, t.denominator

if __name__ == '__main__':
    fracs = []
    for _ in range(int(input())):
        fracs.append(Fraction(*map(int, input().split())))
    result = product(fracs)
    print(*result)
```

Tarefa 3 - URL:https://www.hackerrank.com/challenges/words-score/problem

Código:
```
def is_vowel(letter):
    return letter in ['a', 'e', 'i', 'o', 'u', 'y']

def score_words(words):
    score = 0
    for word in words:
        num_vowels = 0
        for letter in word:
            if is_vowel(letter):
                num_vowels += 1
        if num_vowels % 2 == 0:
            score += 2
        else:
            score += 1
    return score


n = int(input())
words = input().split()
print(score_words(words))
```
