# Complement
Problem of Day solution (14-dec-2022) GFG

```
class Solution:

	def findRange(self,a, n):
	    l = 0
	    count = 0
	    res = (0,0,0)
	    for r in range(n):
	        count += 1 if a[r] == '0' else -1
	        while count < 0:
	            count -= 1 if a[l] == '0' else -1
	            l += 1
	        res = max(res, (count, -(l+1), -(r+1)))
	    return [-1] if res[0] == 0 else [-res[1], -res[2]]
