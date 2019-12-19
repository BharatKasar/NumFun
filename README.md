# NumFun
# A class method for different operations on a positive integer


from math import sqrt
from itertools import permutations

class NumFun(object):
    """module for getting some useful math operations"""

    def __init__(self, num):
        self.num = num

    def checking_palindrome(self):
        """This function returns True if the given number is palindrome"""

        list_input = [int(x) for x in str(self.num)]
        n = len(list_input)
        x = 0

        while x < n:
            if list_input[x] == list_input[n-x-1]:
                if x == n-1:
                    return True
                else:
                    x += 1
            else:
                return False


    def is_prime(self):
        """This function returns True if the given number is prime"""

        i = 2
        while i*i <= self.num:
            if self.num % i == 0:
                return False
            i += 1
        return True


    def factorial(self):
        """This function returns factorial of a number"""

        fact_term = self.num
        if self.num!= 0:
            for i in range(self.num, 1, -1):
                fact_term = fact_term*(i-1)
            return fact_term
        else:
            return 1


    def reversing_number(self):
        """This function rerturns reverse form a of a number."""

        list_input = [x for x in str(self.num)]
        list_input.reverse()

        blank_str = ""
        for s in list_input:
            blank_str += s

        reversed_number = int(blank_str)
        return reversed_number

    def converting_in_binary(self):
        """This function returns binary digits of a number"""
        binary_list = []

        if self.num != 0:
            while self.num != 0:
                rem = self.num%2
                if rem != 0:
                    binary_list.insert(0, 1) # for making binary list new remainder need to be added at the start of the list
                else:
                    binary_list.insert(0, 0)
                self.num = self.num // 2

            blank_str = ""
            for s in binary_list:
                blank_str += str(s)

            binary = int(blank_str)
            return binary

        else:
            return 0


    def binary_to_num(self):
        """This method converts a binary number to an integer."""
        binary_list = [int(x) for x in str(self.num)]
        binary_list.reverse()
        binary_count = 0
        index = 0

        for term in binary_list:
            if term == 1:
                binary_count += 2**index
            index += 1

        return binary_count


    def hcf(self, y):
        """This function returns the HCF of two numbers(Eucledian Algorithm)"""
        while y != 0:
            self.num, y = y, self.num % y

        return self.num

    def generate_num_list(self):
        """This function gives list of all the digits in a given number"""
        str_num = str(self.num)
        num_list = [int(x) for x in str_num]
        return num_list
