# python_programms
from string import ascii_letters as letters, digits
from random import choice, sample

elements = [i for i in list(letters + digits) if i not in ['l', '0', '1', 'o', 'O', 'I']]


def generate_password(m):
    return ''.join(sample(elements, m))


def main(n, m):
    variants = []
    for i in range(n):
        password = generate_password(m)
        while password in variants:
            password = generate_password(m)
        variants.append(password)

    return variants
