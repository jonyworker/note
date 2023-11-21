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

## 建立折疊部分
可以透過建立讀者可以選擇展開的折疊部分來暫時隱藏 Markdown 的分區。 例如，當想在問題評論中包含可能不是每個讀者都相關或感興趣的技術細節時，可以將這些細節放在折疊部分中。

`<details>` 區塊中的任何 Markdown 都會被折疊，直到讀者點擊 展開詳細資料。

在 `<details>` 區塊中，使用 `<summary>` 標記讓讀者知道裡面的內容。 標籤顯示在 的右側。

<pre>
<code class="hljs language-markdown"><span class="xml"><span class="hljs-tag">&lt;<span class="hljs-name">details</span>&gt;</span></span>

	<span class="xml"><span class="hljs-tag">&lt;<span class="hljs-name">summary</span>&gt;</span></span>Tips for collapsed sections<span class="xml"><span class="hljs-tag">&lt;/<span class="hljs-name">summary</span>&gt;</span></span>

	<span class="hljs-section">### You can add a header</span>

	You can add text within a collapsed section. 

	You can add an image or a code block, too.

	<span class="hljs-code">```ruby
		puts "Hello World"
	```</span>

<span class="xml"><span class="hljs-tag">&lt;/<span class="hljs-name">details</span>&gt;</span></span>
</code></pre>

預設情況下，`<summary>` 標籤中的 Markdown 將被折疊如下：

<details>

<summary>Tips for collapsed sections</summary>

### You can add a header

You can add text within a collapsed section. 

You can add an image or a code block, too.

```ruby
   puts "Hello World"
```

</details>


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

### 語法突顯顯示
您可以新增可選的語言標識符，以在圍欄代碼區塊中啟用語法突顯。

語法突出顯示功能會變更原始程式碼的顏色和樣式，使其更易於閱讀。

例如，要語法突顯 Ruby 程式碼：

````
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
````
這將使用語法突出顯示功能顯示程式碼區塊：
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
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

## 使用表情符號
你可以透過鍵入 `:EMOJICODE:`（冒號後面跟著表情符號的名稱）將表情符號加入寫作。

```
@octocat :+1: This PR looks great - it's ready to merge! :heart_eyes:
```
@octocat :+1: This PR looks great - it's ready to merge! :heart_eyes:

呈現的 GitHub Markdown 的螢幕截圖，其中顯示了 +1 的表情符號代碼以及 shipit 如何直觀呈現表情符號。

鍵入 `:` 將顯示建議的表情符號清單。 清單將在你鍵入時進行篩選，因此一旦找到所需表情符號，請按 Tab 或 Enter 鍵以填寫突出顯示的結果 。

有關可用表情符號和代碼的完整列表，請參閱 
 [Emoji-Cheat-Sheet](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)。


## 警告樣式
```
> [!NOTE]
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help user be more successfull.

> [!IMPORTANT]
> Crucial information necessary for users to succeed.

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.
```
> [!NOTE]
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help user be more successfull.

> [!IMPORTANT]
> Crucial information necessary for users to succeed.

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.

## 腳註解
```
Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

[^1]: My reference.
[^2]: To add line breaks within a footnote, prefix new lines with 2 spaces.
  This is a second line.
```
腳註解呈現如下：

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

[^1]: My reference.
[^2]: To add line breaks within a footnote, prefix new lines with 2 spaces.
  This is a second line.

>注意：Markdown 中脚注的位置不会影响该脚注的呈现位置。 您可以在引用脚注后立即写脚注，脚注仍将呈现在 Markdown 的底部。
