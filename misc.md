# 杂项

## 编程模板
这是我在翻答案库的时候看到别人粘贴在代码前面的一段工具库。它能让你在打 Log 和建立复杂数据结构的时候节省时间。

```C++
typedef long long ll;
typedef unsigned long long ull;
typedef long double ld;
typedef std::map<int, int> mii;
typedef std::vector<int> vi;
typedef std::vector<std::vector<int>> vvi;
typedef std::pair<int, int> pii;
typedef std::pair<int, std::pair<int, int>> pipii;
typedef std::vector<std::pair<int, int>> vpii;
const int INF = 0x3F3F3F3F;
const int MOD = 1e9 + 7;
const float PI = 3.14159265358979323846;
const float EPS = 1e-6;

template <typename T> T sum(std::vector<T> &v) { return std::accumulate(v.begin(), v.end(), 0); }
template <typename T> T sum(std::vector<T> &v, int l, int r) {
    return std::accumulate(v.begin() + l, v.begin() + r, 0);
}
template <typename T> T gcd(T a, T b) { return b == 0 ? a : gcd(b, a % b); }
template <typename T> T lcm(T a, T b) { return a / gcd(a, b) * b; }
template <typename Container> void qsort(Container &c) { std::sort(c.begin(), c.end()); }
template <typename Container> void qsort_reverse(Container &c) {
    std::sort(c.begin(), c.end(), std::greater<typename Container::value_type>());
}
template <typename Container> void reverse(Container &c) { std::reverse(c.begin(), c.end()); }
template <typename T> inline int ones(T n) { return __builtin_popcount(n); }

template <typename T> bool in(const T e, std::unordered_set<T> &s) { return s.count(e) > 0; }
template <typename T> bool in(const T e, std::set<T> &s) { return s.count(e) > 0; }
template <class K, class V> bool in(const K e, std::unordered_map<K, V> &s) { return s.count(e) > 0; }
template <class K, class V> bool in(const K e, std::map<K, V> &s) { return s.count(e) > 0; }
template <typename T> bool between(const T &x, const T a, const T b) { return a <= x && x <= b; }

namespace fio {
template <typename T> void say(const T &s) { std::cout << s << std::endl; }
template <typename T> void say(const std::pair<T, T> &p) { std::cout << p.first << ", " << p.second << "\n"; }
template <typename T> void say(const std::vector<T> &vt) {
    for (auto &t : vt) std::cout << t << ", ";
    std::cout << "\n";
}
template <typename T> void say(const std::unordered_set<T> &s) {
    for (auto i : s) std::cout << i << ", ";
    std::cout << "\n";
}
template <typename T> void say(const std::set<T> &s) {
    for (auto i : s) std::cout << i << ", ";
    std::cout << "\n";
}
template <typename K, typename V> void say(const std::map<K, V> &m) {
    std::cout << "{" << "\n";
    for (auto &kv : m)
        std::cout << "  " << kv.first << ": " << kv.second << "," << "\n";
    std::cout << "}" << "\n";
}
template <typename K, typename V> void say(const std::unordered_map<K, V> &m) {
    std::cout << "{" << "\n";
    for (auto &kv : m)
        std::cout << "  " << kv.first << ": " << kv.second << "," << "\n";
    std::cout << "}" << "\n";
}
template <typename T> void say(std::vector<std::vector<T>> &vv) {
    for (auto &v : vv) {
        std::cout << "[";
        for (int i = 0; i < v.size(); ++i) {
            std::cout << v[i];
            if (i < v.size() - 1) std::cout << ", ";
        }
        std::cout << "]" << "\n";
    }
}
template <typename T> void say(std::vector<std::pair<T, T>> &vv) {
    for (auto v : vv) std::cout << v.first << ", " << v.second << "\n";
}
template <typename T> void say(T a[], int n) {
    std::cout << "[";
    for (int i = 0; i < n; i++) {
        if (i) std::cout << ", ";
        std::cout << a[i];
    }
    std::cout << "]" << "\n";
}
template <typename T, typename... Args> void say(T t, Args... args) { // recursive variadic function
    std::cout << t << " ";
    say(args...);
}
} // namespace fio

// fast IO
static auto _su_ = []() {
    std::ios::sync_with_stdio(false);
    std::cin.tie(0);
    return 0;
}();
```