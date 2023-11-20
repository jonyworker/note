# Markdown基本撰寫和格式語法

## 標題樣式
要建立標題，請在標題文字之前添加一到六個 `#` 符號。 `#` 的數量將決定層次結構級別語標題的大小。

```
# A first-level heading
## A second-level heading
### A third-level heading
#### A fourth-level heading
##### A fifth-level heading
###### A sixth-level heading
```
# A first-level heading
## A second-level heading
### A third-level heading
#### A fourth-level heading
##### A fifth-level heading
###### A sixth-level heading


使用兩個或多個標題時，GitHub 會自動產生一個目錄，可以透過點擊檔案標題中的漢堡icon來存取該目錄。 每個標題都列在目錄中，可以按一下某個標題導覽到所選部分。

![漢堡位置示意](../img/00_工具包用圖/headings-toc.webp)

## 字體樣式

<table>
	<tr>
		<td>Style</td>
		<td>語法</td>
		<td>示例</td>
		<td>輸出</td>
	</tr>
	<tr>
		<td>加粗</td>
		<td>
			<code>** **</code> 或 <code>__ __</code>
		</td>
		<td>
			<code>**This is bold text**</code>
		</td>
		<td><strong>這是粗體文字</strong></td>
	</tr>
	<tr>
		<td>斜體</td>
		<td>
		<code>* *</code> 或 <code>_ _</code>
		</td>
		<td>
		<code>_This text is italicized_</code>
		</td>
		<td><em>這是斜體文字</em></td>
	</tr>
	<tr>
		<td>刪除線</td>
		<td>
			<code>~~ ~~</code>
		</td>
		<td>
			<code>~~This was mistaken text~~</code>
		</td>
		<td><del>這是錯誤文字</del></td>
	</tr>
	<tr>
		<td>上標</td>
		<td><code>&lt;sup&gt; &lt;/sup&gt;</code></td>
		<td>
			<code>This is a &lt;sup&gt;superscript&lt;/<wbr>sup&gt; text</code>
		</td>
		<td>這是<sup>上標</sup>文字</td>
	</tr>
	<tr>
		<td>下標</td>
		<td><code>&lt;sub&gt; &lt;/sub&gt;</code></td>
		<td>
			<code>This is a &lt;sub&gt;subscript&lt;/<wbr>sub&gt; text</code>
		</td>
		<td>這是<sub>下標</sub>文字</td>
	</tr>
</table>

## 引用文字

可以使用 `>` 來引用文字。
```
> Text that is a quote
```

Text that is not a quote

> Text that is a quote

```
> 引用的內容
> > 引用的內容的子內容
> > > 引用的內容的子子內容
```


> 引用的內容
> > 引用的內容的子內容
> > > 引用的內容的子子內容

## 引用代碼
使用單引號 ``` ` ``` 可標註句子中的代碼或指令。 反引號中的文字不會被格式化。 你也可以按下 Command+E (Mac) 或 Ctrl+E (Windows/Linux) 鍵盤捷徑將程式碼區塊的反引號插入到 Markdown 一行。

```
Use `git status` to list all new or modified files that haven't yet been committed.
```
Use `git status` to list all new or modified files that haven't yet been committed.

若要將程式碼或文字格式化為各自的不同區塊，請使用三反引號。

<pre>
Some basic Git commands are:
```
git status
git add
git commit
```
</pre>


Some basic Git commands are:
```
git status
git add
git commit
```
## 支援顏色模型
可以使用反引號在句子中標註顏色。 反引號內支援的顏色模型將顯示顏色的視覺化效果。
```
The background color is `#ffffff` for light mode and `#000000` for dark mode.
```
The background color is `#ffffff` for light mode and `#000000` for dark mode.

下面是當前支援的顏色模型。
<table>
	<tr>
		<td>Color</td>
		<td>語法</td>
		<td>示例</td>
		<td>輸出</td>
	</tr>
	<tr>
		<td>加粗</td>
		<td>
			<code>`#RRGGBB`</code>
		</td>
		<td>
			<code>`#0969DA`</code>
		</td>
		<td><code>`#0969DA`</code></td>
	</tr>
</table>

## 連結
透過將連結文字用方括號 `[ ]` 括起來，然後將 URL 用括號 `( )` 括起來，可建立內嵌連結。 也可以使用鍵盤快捷方式 Command+K 建立連結。 選擇文字後，可以貼上剪貼簿中的 URL 以自動從所選內容建立連結。

也可以透過反白文字並使用鍵盤快捷方式 Command+V 建立 Markdown 超連結。 如果要將文字替換為鏈接，請使用鍵盤快捷方式 Command+Shift+V。

```
This site was built using [GitHub Pages](https://pages.github.com/).
```
This site was built using [GitHub Pages](https://pages.github.com/).

## 相對連結
您可以在渲染的文件中定義相對連結和圖像路徑，以幫助讀者導航到倉庫中的其他文件。

相對連結是相對於目前文件的連結。 例如，如果在倉庫根目錄下有一個自述文件，而在 docs/CONTRIBUTING.md 中有另一個文件，則自述文件中的 CONTRIBUTING.md 的相關連結如下所示 ：
```
[Contribution guidelines for this project](docs/CONTRIBUTING.md)
```
GitHub 將根據您目前使用的分支自動轉換相對連結或影像路徑，從而使連結或路徑始終有效。 連結的路徑將相對於目前檔案。 以 `/` 開頭的連結將相對於儲存庫根目錄。 可使用所有相對連結運算元，例如 `./` 和 `../`。

相對連結更便於使用者克隆倉庫。 絕對連結可能無法用於倉庫的克隆 - 建議使用相對連結來引用倉庫中的其他文件。

## 連結圖片
透過新增 `!` 並 將 alt 文字用 `[ ]` 括起來，可顯示圖像。 替換文字是等效於圖像中資訊的短文字。 然後將圖像的連結用括號 `()` 括起來。
```
![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](https://myoctocat.com/assets/images/base-octocat.svg)
```
![Screenshot of a comment on a GitHub issue showing an image, added in the Markdown, of an Octocat smiling and raising a tentacle.](https://myoctocat.com/assets/images/base-octocat.svg)

## 列表
可透過在一行或多行文字前面加上 `-`、`*` 或 `+` 來建立一個無序列表。

```
- George Washington
* John Adams
+ Thomas Jefferson
```

- George Washington
* John Adams
+ Thomas Jefferson

若要對清單排序，請在每行前面新增編號。

```
1. James Madison
1. James Monroe
1. John Quincy Adams
```
1. James Madison
1. James Monroe
1. John Quincy Adams

## 嵌套列表
### 無序階層
* 這是第一層
 * 這是第一層
   - 這是第二層
     - 這是第三層
       - 其實還可以有好多好多層

程式碼：

```
 * 這是第一層
 * 這是第一層
   - 這是第二層
     - 這是第三層
       - 其實還可以有好多好多層
```
### 有序階層
1. 這是第一層
2. 這是第一層
   1. 這是第二層
      1. 這是第三層
         1. 一樣也可以有好多好多層
程式碼：

```
1. 這是第一層
2. 這是第一層
   1. 這是第二層
      1. 這是第三層
         1. 一樣也可以有好多好多層
```

## 任務列表
```
- [ ] 待辦
  - [x] 買些沙拉
  - [ ] 刷牙
  - [x] 喝水

```
- [ ] 待辦
  - [x] 買些沙拉
  - [ ] 刷牙
  - [x] 喝水

