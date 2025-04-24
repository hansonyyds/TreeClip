# TreeClip 文本批量选择器

厌倦了逐个复制网页内容？难以选中结构相似但排版混乱的列表项？想一次性复制页面上分散的多处文本？还是想通过通配符快速提取文本？

**TreeClip** 是一款Chrome扩展工具，它提供了多种灵活的页面文本选择方式（同类选择、点选、框选、文本搜索），并结合了层级导航、内部元素选择、层级绑定、自定义输出格式等功能，大幅提升您从网页复制信息的效率。
<p dir="auto" align="center">
    <a href="https://chrome.google.com/webstore/detail/bipfdahpmodcpkfpmcjnpkmdjhffbnad" rel="nofollow"><img src="https://img.shields.io/badge/Plugin-Chrome-green" alt="Chrome Plugin" style="max-width: 100%;"></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow" alt="MIT License" style="max-width: 100%;"></a>
</p>
<p dir="auto" align="center">
  <a href="/preview/preview_p1.gif" target="_blank">
    <img src="/preview/preview_p1.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>


**核心启用方式：** 按住`Shift`键，然后用鼠标 **点击** 或 **框选** 页面元素即可选中元素，选中后按 `F` 键可快速批量选中同类元素，选中的内容会自动复制到剪贴板。

## 主要模式

### 1. 批量选择 (同类元素)

*   **使用场景：** 需要复制结构相同、类型一致的内容，例如搜索结果、商品标价、表格列项、贴文标题、标签名称等。普通划选可能会选中多余元素或导致排版混乱。我们将对相似的元素结构（标签名、CSS类等）进行识别，批量选中同类元素。
*   **使用方法：**
    1.  按住 `Shift` 键并 **点击** 任意一个你想选择的目标元素。（当你选中两个类型相同的元素时，程序也会主动提示）
    2.  按下键盘上的 `F` 键。
    3.  工具会自动识别并选中页面上所有与你选中元素的结构相同的 **同类型** 元素，并将所有元素的文本内容添加至剪切板。
<p dir="auto" align="center">
  <a href="/preview/preview_p2.gif" target="_blank">
    <img src="/preview/preview_p2.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>

### 2. 多点选择

*   **使用场景：** 需要同时复制页面上分散在不同位置、结构可能不同的多个文本块。模拟了类似 Excel 中按住 `Ctrl` 选择不相邻单元格的操作。
*   **使用方法：**
    1.  按住 `Shift` 键。
    2.  依次 **点击** 你需要选择的每一个元素或文本块，也可以结合`Shift`+`F`批量选择。
    3.  所有被点击的元素都会加入到选择列表中，其文本将被添加至剪切板。
<p dir="auto" align="center">
  <a href="/preview/preview_p3.gif" target="_blank">
    <img src="/preview/preview_p3.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>

### 3. 框选选择

*   **使用场景：** 快速选中一个可视化矩形区域内的所有可见、有意义的元素文本。
*   **使用方法：**
    1.  按住 `Shift` 键。
    2.  按住鼠标左键并 **拖动**，绘制一个覆盖目标元素的矩形选框。
    3.  松开鼠标，选框范围内的有效元素将被自动选中，其文本将被添加至剪切板。
<p dir="auto" align="center">
  <a href="/preview/preview_p4.gif" target="_blank">
    <img src="/preview/preview_p4.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>

### 4. 文本/模式搜索

*   **使用场景：** 在页面中查找包含特定文本或符合特定模式的内容，并将找到的对应元素添加到选择中。
*   **使用方法：**
    1.  在选择器面板的“文本/模式搜索”区域输入关键词或模式。
    2.  **支持的模式：**
        *   `*`：匹配任意数量字符 (例如: `数据*分析`)
        *   `?`：匹配单个字符 (例如: `第?章`)
        *   `[a,b,c]`：匹配括号内任一项 (例如: `第[一,二,三]章` 或 `[10,20,30]%`)
        *   `"..."`：引号内字符按字面匹配 (例如: `"*"` 只匹配星号，`"[1,2]"` 匹配 `[1,2]` 字符串)
    3.  点击“搜索”按钮。
    4.  匹配的文本会在页面上高亮显示。
        *   如果匹配的文本位于当前 **不可见** 的元素内（如折叠菜单），其 **最近的可见父元素** 会显示橙色虚线轮廓提示。
    5.  使用“前一项”/“后一项”按钮在结果间跳转，页面会自动滚动到对应位置。
    6.  点击“添加到选择”按钮，会将 **所有搜索结果** 对应的 **最近有意义的父元素** 添加到当前的选择列表中。
<p dir="auto" align="center">
  <a href="/preview/preview_p5.gif" target="_blank">
    <img src="/preview/preview_p5.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>

## 其他特性与高级用法
<p dir="auto" align="center">
  <a href="/preview/preview_p6.gif" target="_blank">
    <img src="/preview/preview_p6.gif" alt="Image 1" style="height: 300px; width: auto; margin-right: 10px; border-radius: 5px; box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);">
  </a>
</p>

### 层级导航与切换

*   当有元素被选中时，选择器面板会显示当前选中元素的 **层级结构**。
*   **切换操作目标类型：** 如果你选中了多种类型的元素（例如同时选了标题 `h3` 和段落 `p`），可以点击面板中显示的元素类型（如 `h3.title (5)`，将后续操作（如按 `F` 键、层级切换等）的目标限定为该类型。）
*   **切换层级：** 点击层级面板中的 **层级标签**（如 `div#main`），可以将当前选择切换到该层级的元素。通常用于向上选择父容器或向下选择更具体的子元素。

### 内部元素选择

*   **适用场景：** 当前选中的元素（例如一个列表项 `<li>`）内部包含多个子元素，你想选择其中特定的子元素。（例如该列表项内的所有链接 `<a>` 或特定 `<span>`）。
*   **识别：** 如果工具检测到这种情况，“内部元素”按钮会 **变绿高亮**。
*   **使用方法：** 点击 **绿色** 的“内部元素”按钮（或按 `Shift + →` 快捷键），进入内部元素选择模式。此时面板会列出可供选择的内部元素类型，点击其中一项即可将选择范围精确到这些内部元素。按 `Shift + ←` 可返回父级视图。

### 层级绑定 (精确匹配)

*   **适用场景：** 你只想选择那些属于 **特定父结构下** 的同类元素，忽略页面其他地方相同类型但父结构不同的元素（例如，只想选A区块的所有`<li>`，不想选B区块的`<li>`）。
*   **使用方法：**
    1.  先选中一个目标元素。
    2.  在层级面板中，找到你想要 **绑定** 的那个父层级（比如代表A区块的 `div.block-a`）。
    3.  按住 `Shift` 键并 **点击该父层级标签**。该标签会显示特殊高亮（橙色）。
    4.  此时再执行批量选择（如按 `F` 键），工具将只会寻找那些同样从属于 `div.block-a` 下的同类元素。再次 `Shift + 点击` 该层级可取消绑定。

### 输出格式与文本清理

*   在"输出格式"区域，你可以精细控制复制到剪贴板的内容：
    *   **分隔方式：** 选择内容合并时使用的分隔符（换行、空格、逗号）。
    *   **文本清理选项：**
        *   **文本空格：** 移除每个文本片段内部的所有空白字符。
        *   **代码：** 移除常见代码块模式，如 `{...}`, `(...)`, `<...>`, `[...]`。
        *   **符号：** 移除常见的标点和数学符号。
        *   **英文/中文/数字：** 分别移除对应的字符类型。
    *   **去重选项：**
        *   **去除重复项：** 自动删除复制内容中的完全重复的条目。

## 快捷键


*   **基础选择:**
    *   `Shift + 鼠标点击`: 选择或取消选择单个元素。
    *   `Shift + 鼠标拖拽`: 绘制矩形框进行框选。
    *   `Esc`: 清除所有选择，退出选择模式。
    *   `F` (当有元素被选中时): 选择所有类型相同的元素。
    *   `Ctrl + C`: 将当前选中的内容（按设定格式）复制到剪贴板。

*   **层级导航与内部选择:**
    *   `Shift + ↑`: 向上移动，选择父层级元素。
    *   `Shift + ↓`: 向下移动，选择子层级元素。
    *   `Shift + →`: 进入"内部元素"选择模式。
    *   `Shift + ←` (在内部元素模式下): 返回父层级视图。

*   **层级绑定:**
    *   `Shift + 点击` (在层级面板的某个层级标签上): 开启或关闭层级绑定，将后续选择范围精确限定在该父层级下。
