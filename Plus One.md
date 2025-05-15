# Leetcode-66-Plus One

```rust
impl Solution {
    pub fn plus_one(digits: Vec<i32>) -> Vec<i32> {
        // 將輸入轉為可變的 Vec
        let mut digits = digits;
        // 從最低有效位开始處理進位
        for i in (0..digits.len()).rev() {
            if digits[i] < 9 {
                digits[i] += 1;
                return digits;
            }
            digits[i] = 0;
        }
        // 全部為 9 時需要在最前面加一位
        let mut result = Vec::with_capacity(digits.len() + 1);
        result.push(1);
        result.extend(digits);
        result
    }
}
```
