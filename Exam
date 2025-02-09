#include <vector>
#include <map>
#include <queue>
#include <functional>

using namespace std;

class Solution {
public:
    vector<vector<int>> sortMatrix(vector<vector<int>>& grid) {
        int n = grid.size();
        map<int, priority_queue<int>> maxDiags;
        map<int, priority_queue<int, vector<int>, greater<int>>> minDiags;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i - j < 0)
                    minDiags[i - j].push(grid[i][j]);
                else
                    maxDiags[i - j].push(grid[i][j]);
            }
        }

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i - j < 0) {
                    grid[i][j] = minDiags[i - j].top();
                    minDiags[i - j].pop();
                } else {
                    grid[i][j] = maxDiags[i - j].top();
                    maxDiags[i - j].pop();
                }
            }
        }

        return grid;
    }
};
# exmas
