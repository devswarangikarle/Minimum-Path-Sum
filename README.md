# Minimum-Path-Sum

Given a m x n grid filled with non-negative numbers, find a path from top left to bottom right, which minimizes the sum of all numbers along its path.

class Solution:
    def minPathSum(self, grid: List[List[int]]) -> int:
            
        
        m, n = len(grid), len(grid[0])
        
        for i in range(1, m):
            grid[i][0] += grid[i-1][0]
        
        for i in range(1, n):
            grid[0][i] += grid[0][i-1]
        
        for i in range(1, m):
            for j in range(1, n):
                grid[i][j] += min(grid[i-1][j], grid[i][j-1])
        
        return grid[-1][-1]
    
        
