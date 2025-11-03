class Solution(object):
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """
        # List of (value, symbol) in descending order
        values = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
        symbols = ["M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"]
        
        result = []
        for val, sym in zip(values, symbols):
            if num == 0:
                break
            count = num // val
            if count > 0:
                result.append(sym * count)
                num -= val * count
        
        return "".join(result)
        
