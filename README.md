# Android Material Design 3 底部导航控件

一个基于 Android 原生 API 实现的 Material Design 3 风格底部导航控件，支持平滑动画、圆角矩形指示器以及仅选中项显示文字标签


## 使用方法


在布局 XML 文件中添加 `BottomNavigation` 控件：

```xml
<com.yuuki.hook_manager.ui.widget.BottomNavigation
    android:id="@+id/bottom_navigation"
    android:layout_width="match_parent"
    android:layout_height="80dp" />
```


```java
BottomNavigation bottomNav = findViewById(R.id.bottom_navigation);

// 创建导航项
List<BottomNavigation.NavigationItem> items = new ArrayList<>();
items.add(new BottomNavigation.NavigationItem("首页", ContextCompat.getDrawable(this, R.drawable.ic_home)));
items.add(new BottomNavigation.NavigationItem("搜索", ContextCompat.getDrawable(this, R.drawable.ic_search)));
items.add(new BottomNavigation.NavigationItem("个人", ContextCompat.getDrawable(this, R.drawable.ic_profile)));

// 设置导航项
bottomNav.setItems(items);

// 设置选中监听器
bottomNav.setOnItemSelectedListener((index, item) -> {
    Toast.makeText(this, "选中: " + item.title, Toast.LENGTH_SHORT).show();
    return;
});

// 可选：自定义外观
bottomNav.setSelectedColor(Color.parseColor("#2E7D32")); // 深绿色
bottomNav.setIndicatorColor(Color.parseColor("#E8F5E8")); // 浅绿色
bottomNav.setShowLabels(true);
bottomNav.setIndicatorWrapText(true);
bottomNav.setAnimationDuration(300);
```


## 自定义选项

| 方法 | 描述 | 默认值 |
| --- | --- | --- |
| `setItems(List<NavigationItem>)` | 设置导航项 | \- |
| `setSelectedColor(int)` | 设置选中项颜色 | `#2E7D32`（深绿色） |
| `setUnselectedColor(int)` | 设置未选中项颜色 | `#757575`（灰色） |
| `setIndicatorColor(int)` | 设置指示器背景颜色 | `#E8F5E8`（浅绿色） |
| `setShowLabels(boolean)` | 显示/隐藏选中项的文字标签 | `true` |
| `setIndicatorWrapText(boolean)` | 设置指示器是否包裹图标和文字（`true`）或仅图标（`false`） | `true` |
| `setIndicatorCornerRadius(float)` | 设置指示器圆角半径（单位：dp） | `16dp` |
| `setIndicatorPadding(float, float)` | 设置指示器的水平和垂直内边距（单位：dp） | `12dp, 4dp` |
| `setAnimationDuration(long)` | 设置动画持续时间（单位：毫秒） | `300ms` |
| `setEnableAnimation(boolean)` | 启用/禁用动画 | `true` |

## 演示


![false](./art/false.gif)
![true](./art/true.gif)
