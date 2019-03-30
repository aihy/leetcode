## 118

```cpp
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> res;
        vector<int> iknow;
        vector<int> newi;
        int is,newis,item;
        for (int i2=0; i2<numRows; i2++)
        {
            is = iknow.size();
            newis = is + 1;
            for (int i=0; i<newis; i++)
            {
                if (i==0 || i==newis-1)
                {
                    item = 1;
                }
                else
                {
                    item = iknow[i-1] + iknow[i];
                }
                newi.push_back(item);
            }
            res.push_back(newi);
            iknow = newi;
            newi.clear();
        }
        return res;
    }
};
```

* vector是一个变长数组
* `vector<int> xxx` 定义xxx
* `xxx.size()` 返回长度
* `xxx.push_back(item)` 相当于python里的append
* `xxx.clear()` 清空这个数组