class Solution {
public:
    vector<vector<int>> diagonalSort(vector<vector<int>>& mat) {
    vector<int> decompile;
    vector<vector<int>> ans;
    for(int rows = 0; rows < mat.size(); rows++)
    {
        for(int columns = 0; columns < mat[rows].size(); columns++)
        {
            decompile.push_back(mat[rows][columns]);
        }
    }
    sort(decompile.begin(), decompile.end());
    
    for(int i = 0; i < mat.size(); i++)
    {
        vector<int> row;
        for(int j = 0; j < mat[i].size(); j++)
        {
            if( (i == 0 or j == 0) and !decompile.empty())
            {
                row.push_back(decompile.front());
                decompile.erase(decompile.begin());
            }
            else if( (i > 0 and j > 0) and (ans[i-1][j-1] < decompile.front()) and !decompile.empty())
            {
                row.push_back(decompile.front());
                decompile.erase(decompile.begin());
            }
            else if( (i > 0 and j > 0) and (ans[i-1][j-1] >= decompile.front()) and !decompile.empty())
            {
                for(int k = 0; k < decompile.size(); k++)
                {
                    if(decompile[k] > ans[i-1][j-1])
                    {
                        row.push_back(decompile.front() + k);
                        decompile.erase(decompile.begin() + k);
                        break;
                    }
                    else
                    {
                        continue;
                    }
                }
            }
        }
        ans.push_back(row);
    }
    return ans;
    }
};

/*  
CASE 1:
INPUT
[3, 3, 1, 1]
[2, 2, 1, 2]
[1, 1, 1, 2]

EXPECTED OUTPUT
[1, 1, 1, 1]
[1, 2, 2, 2]
[1, 2, 3, 3]

MY OUTPUT
[1, 1, 1, 1]
[1, 2, 2, 2]
[1, 2, 3, 3]

========================

CASE 2:
INPUT
[11, 25, 66,  1, 69,  7]
[23, 55, 17, 45, 15, 52]
[75, 31, 36, 44, 58,  8]
[22, 27, 33, 25, 68,  4]
[84, 28, 14, 11,  5, 50]
  
EXPECTED OUTPUT
[ 5, 17,  4,  1, 52,  7]
[11, 11, 25, 45,  8, 69]
[14, 23, 25, 44, 58, 15]
[22, 27, 31, 36, 50, 66]
[84, 28, 75, 33, 55, 68]

PROPOSED MATRIX & MY OUTPUT
[ 1,  4,  5,  7,  8, 11]
[11, 14, 15, 17, 22, 23]
[25, 25, 27, 28, 31, 33]
[36, 44, 45, 50, 52, 55]
[58, 66, 68, 69, 75, 84]
 */
