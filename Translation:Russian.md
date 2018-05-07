# LaTeX за несколько минут

![](https://upload.wikimedia.org/wikipedia/commons/9/92/LaTeX_logo.svg)

<!-- **Acknowledgement:** *Everything written below is from my own experience in college and after reading various materials. I am neither a professional nor expert, but a student who has great passion for the language. Anyone can open a discussion in the issue section, or a pull request in case something should be modified or added. If you consider my work valuable, a [donation](#donation) is much appreciated.** -->

**Уведомление**: *Всё написанное ниже взято из моего собственного опыта в колледже и после чтения различных материалов. Я не являюсь ни профессионалом, ни экспертом - я студент с большой страстью к языку. Кто угодно может открыть обсуждение в issues, или pull request, в случае, если что-то должно быть изменено или добавлено. Если вы считаете мою работу стоящей, [донаты](#donation) очень ценятся.*
*[Китайский](https://github.com/VoLuong/Begin-Latex-in-minutes/blob/master/Translation:Chinese.md),
[французский](https://github.com/VoLuong/Begin-Latex-in-minutes/blob/master/Translation:French.md), [португальский](https://github.com/LewisVo/Begin-Latex-in-minutes/blob/master/Translation:Portuguese.md) и [испанский](https://github.com/VoLuong/Begin-Latex-in-minutes/blob/master/Translation:Spanish.md) переводы доступны.*

### Содержание
* [Что такое LaTeX?](#what-is-latex)
* [Зачем использовать LaTeX?](#why-use-latex)
* [Настройка окружения для LaTeX](#set-up-for-latex)
* [Первый LaTeX-файл](#first-latex-file)
* [Взгляд глубже](#a-deeper-look)
* [Многоязычное использование](#multilingual-usage)
* [Списки](#lists)
* [Параграф и секция](#paragraph-and-section)
* [Cоздание содержания](#making-a-table-of-contents)
* [Сноски](#footnotes)
* [Что такое пакет?](#what-is-a-package)
* [Таблица](#table)
* [Добавление изображений](#adding-images)
* [Вставка кода в LaTeX](#insert-code-into-latex)
* [Несколько файлов в LaTeX](#Multiple-files-in-LaTeX)
* [Дополнительные инструменты](#additional-tools)

## Что такое LaTeX?

LaTeX (произносится "Ла-Тек" или "Лей-Тек") - система подготовки документов для высококачественной вёрстки. Чаще всего используется для средних-больших технических или научных документов, но может быть использована для практически любых форм публикации.

## Зачем использовать LaTeX?

* LaTeX бесплатный и мультиплатформенный.
* LaTeX - просто текстовый документ (который может быть открыт любым текстовым редакторов), легко конвертируемый в PDF.
* LaTeX разделяет содержимое и презентацию. Задайте стиль один раз, потом сфокусируйтесь на контенте.
* Процесс работы быстрее по сравнению с MS Word.
* LaTeX широко используется в научных кругах.
* LaTeX - просто лучший выбор, когда дело касается вёрстки математических выражений.

> LaTeX не идеален, но всё же стоит изучения.

## Настройка окружения для LaTeX

Вам понадобится следующее:


1. *Дистрибутив LaTeX.*
Я использую [MiKTeX](https://miktex.org/about) для Windows.
2. *LaTeX Editor.*
Я использую [TeXMaker](http://www.xm1math.net/texmaker/) для простого редактирования, хотя любой текстовый редактор может открывать и редактировать LaTeX-файлы.
3. *Просмотрщик PDF.* (необязательно)
Любой просмотрщик PDF подойдёт. Это необходимо для просмотра ваших результатов.

Также, вам нужно выбрать [компилятор](#additional-tools). Стандартный компилятор большинства редакторов - pdfLaTeX, но если вам нужна поддержка Unicode или шрифтов TTF/OTF вашей системы, используйте LuaLaTeX.

Или же вы можете выбрать простое онлайн-решение, вроде [ShareLaTeX](https://www.sharelatex.com/).
Взгляните на [Дополнительные инструменты](#additional-tools) для более широкого выбора вариантов.

## Первый LaTeX-файл

Давайте напишем традиционный **Hello World** в **LaTeX**.
Если вы установили **TexMaker**, сначала создайте новый файл с расширением `.tex`. Потом введите следующий код, чтобы отрисовать "Hello World!" и запустите "быструю сборку" ("quick build"). Для других LaTeX-редакторов, подобная процедура также должна быть доступна.

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello World !  % Это ваше содержимое

\end{document}
```

В TeXMaker это должно выглядеть так:
![](http://i.imgur.com/ZuD5N6U.png)

## Взгляд глубже

:eyes: Взгляд глубже в ваш первый LaTeX-файл показывает, что:
* Первая строчка говорит интерпретатору, что вы работаете над **статьёй** (**article**) размера А4. Другие виды документов, над которыми вы можете работать в будущем - это **отчёт** (**report**), **книга** (**book**) и так далее.
* Документ обёрнут в `begin{document}` и `\end{document}`. Считайте это сердцем документа, как `main()` в *Java* или *C++*, без которого документ не может быть отрисован.
* Часть между **begin** и **end** (которая, в данном случае, является `Hello World` ) - это просто ваше содержимое.
* **Знак процента** (%) обозначает комментарий, который LaTeX игнорирует.

#### :zap: Внимание :zap:

* Посмотрите на **\begin{document}**, **\end{document}**, **\documentclass[a4paper]{article}**. Вы можете увидеть закономерность. Они называются **командами вёрстки** (которые обычно начинаются с `\`) и **аргументами** (внутри фигурных скобок `{}`). LaTeX, в основном, обычный текст, улучшенный такими командами.
* Пока вы следуете этой инструкции, всё будет работать. Впрочем, в будущем, если будут какие-либо проблемы, **не паникуйте**. Сообщения об ошибках дружелюбные и читаемые. Если вы не можете решить проблему, поисковик вроде Google станет вам лучшим другом.
* Некоторые символы **зарезервированы в LaTeX. Вы можете использовать бэкслеши (`\\`) перед ними для правильного вывода.**

![](http://i.imgur.com/9d0bXHH.png)

## Многоязычное использование

**Некоторые языки не будут работать из коробки. Чтобы использовать LaTeX с ними, у вас есть варианты.**

#### :white_check_mark: Первый метод :white_check_mark:

Первый метод - подключение ["пакетов"](#what-is-a-package) (вы узнаете о них позже), потому что pdfLaTeX, стандартный компилятор, ограничен 256 символами и различными проблемами с кодировками. К примеру:

```tex
\documentclass[a4paper]{article}

\usepackage[T5]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Тут мы используем `usepackage[T5]{fontenc}` и `usepackage[utf8]{inputenc}`. Это очень легко понять, так как пакет подключит кодировщики шрифтов, чтобы верно отобразить ваш контент. Если вы используете TeXMaker, вот что отобразит этот код:

![](http://i.imgur.com/UQEewYi.png)

Без пакетов: :package::

![](http://i.imgur.com/xvzrQX2.png)

:umbrella: Непростая ситуация - работа с китайским/корейским. Здесь, `usepackage{CJKutf8}` с `\begin{CJK}{UTF8}` и `\end{CJK}` очень помогает. Вот японский :jp::
```tex
\documentclass[a4paper]{article}
\usepackage{CJKutf8}

\begin{document}

\begin{CJK}{UTF8}{min}
この記事を読んでいただきありがとうございます。
%Thank you for reading this article.
\end{CJK}

\end{document}
```

Так же просто, как есть :sushi: и :bento:!

![](http://i.imgur.com/vAN1WUi.png)

#### :white_check_mark: Второй метод :white_check_mark:
Другой метод доступен, если изменить ваш компилятор на [LuaLaTeX](#additional-tools) (или [XeLaTeX](#additional-tools)). Используя `fontspec` и `polyglossia`, Unicode работает "из коробки":

```tex
\documentclass[a4paper]{article}

\usepackage{fontspec}
\usepackage{polyglossia}
%\setmainfont[]{DejaVu Serif}

\begin{document}

Xin chào thế giới. This is Hello World in Vietnamese.

\end{document}
```

Стандартный шрифт (Latin Modern) не поддерживает все символы. Вы можете, впрочем, использовать практически любой шрифт, установленный в вашей системе, раскомментировав строчку `\setmainfont`. (шрифты TTF и OTF полностью поддерживаются).


## Списки

:straight_ruler: Очень важно правильно организовать ваш документ. Поэтому давайте начнём с того, что поместим все ваши элементы в список.
Два распространённых типа списков - **маркированный** и **нумерованный** список. Каждый из них может быть легко создан в LaTeX-документе:
* Маркированный список
Маркированный список требует только `itemize`.
```tex
\begin{itemize}
\item Item.
\item Another Item.
\end{itemize}
```
* Нумерованный список
Нумерованный список требует `enumerate`.
```tex
\begin{enumerate}
\item First Item.
\item Second Item.
\end{enumerate}
```

Вот как выглядят оба типа списков:

![](http://i.imgur.com/jzN4RWm.png)

## Параграф и секция

:blue_book: We begin a section with `\section` and a paragraph with `\paragraph`.
:orange_book: You can also add subsection with `\subsection` and subparagraph with `\subparagraph`

![](http://i.imgur.com/qKbZYnG.png)

## Making a table of contents

:metal: It's useful to open sections and subsections with a `\tableofcontents`

Example:

![](http://i.imgur.com/TBUOTRj.png)

:bangbang: **Tips**: you can use `\newpage` if you want to make a new page.

## Footnotes

It's as easy as pie to use footnote+label+ref to make all kinds of footnotes you want. For example:
```tex
Hi let me introduce myself\footnote{\label{myfootnote}Hello footnote}.
... (later on)
I'm referring to myself \ref{myfootnote}.
```
:point_down: :point_down: Can you see it ?  :point_down: :point_down:

![](http://i.imgur.com/BSYPX4C.png)

:bangbang: **Tips**: you can use `\newline` to make a new line.

## What is a package?

LaTeX offers a lot of functions by default, but in some situations it can come in handy to use so called packages. To import a package in LaTeX, you simply add the `\usepackage` :package:

Here is an example of using two packages for displaying math:

![](http://i.imgur.com/050nrfh.png)

Even more epic is how circuits are displayed:

![](http://i.imgur.com/If4lbLA.png)

:construction: You should Google search more if you want a package that meets your requirements. For example, amsmath is widely used for math and has a lot of extension typeset for math, circuitikz is for circuits designing, etc.. Covering them all would be impossible for this general guide.

## Table

A practical example :thought_balloon::

```tex
\begin{table}[h!]
  \centering
  \caption{Caption for the table.}
  \label{tab:table1}
  \begin{tabular}{l|c||r}
    1 & 2 & 3\\
    \hline
    a & b & c\\
  \end{tabular}
\end{table}
```

:star2: This is what it renders :star2::

![](http://i.imgur.com/XbZJJ2E.png)

Now let's take a closer look :eyes::

* For tables, first we need a table environment, which is why we have `\begin{table}` and `\end{table}`.
* You will learn about h! later in the image section. It goes with `\centering` to keep the table at the center of the page.
* Caption is for describing. Label is for tagging. You will see these more in image section.
* Tabular is the most important part. A table environment always needs a tabular environment inside.
  - the part `{l|c||r}` is where we format the content inside the table. Here we can see:
    * l or c or r means that the content inside each cell will be left-aligned or center-aligned or right-aligned, respectively.
    * the vertical slash | or || is actually the format of the vertical lines/borders inside the table's columns.
  - 1 & 2 & 3 => 1 2 3 are the contents of each cells. the ampersand & is used to separate the content of each cell in a row.
  - a `\hline` actually adds a horizontal line to separate each row.

:bangbang: **Tips**: You can use a package :package: called booktabs `\usepackage{booktabs}` for a visually better table.

## Adding images

To add an image to the LaTeX file, you need to use figure environment and the graphicx package. Use `\usepackage{graphicx}` and

```tex
\begin{figure}
  \includegraphics[width=\linewidth]{filename.jpg}
  \caption{What is it about?}
  \label{fig:whateverlabel}
\end{figure}
```

:bangbang: **Tips**: Put [width=\linewidth] to scale the image to the width of the document. If you want to float the image, then you need to attribute the begin with a certain value. Also, the fig is for later reference so name it with care.

```tex
\begin{figure}[h!]
```

:passport_control: Legit values are:

* h (here) — same location
* t (top) — top of page
* b (bottom) — bottom of page
* p (page) — on an extra page
* ! (override) — will force the specified location

Here's how the image is rendered:

![](http://i.imgur.com/ysY9MOb.png)

## Insert code into LaTeX

#### :white_check_mark: First method :white_check_mark:

One aspect of text compiling that is of the utmost importance to programmers and developers is how to professionally insert codes into the document.

For LaTeX, the process is simple and very professional. We just wrap the code with some predefined content, then we are good to go.

Example:

```tex
\documentclass[a4paper]{article}

\begin{document}

Hello world!

\begin{verbatim}
#include <iostream>

int main()
{
	std::cout << "hello world!\n";
	return 0;
}
\end{verbatim}

\end{document}
```

:speech_balloon: **LaTeX supports syntax for these languages** :speech_balloon:

![](http://i.imgur.com/FJfj8Er.png)

As you can see, with the **{verbatim}** wrapper you can easily insert code without worrying about how the syntax is formatted. Here is how it looks out of the box, clean and professional:

![](http://i.imgur.com/tpercup.png)

#### :white_check_mark: :white_check_mark: Second Method :white_check_mark: :white_check_mark:

This method gives you more options, including insert code **inline**, make **custom styles** code, choose a **specific language** for code, **import code** **from** another **file** within the same directory.... With this method, you dont use **{verbatim}**, but include a package :package: named **listings**.

Consider the following example:
```tex
\documentclass[a4paper]{article}

\usepackage{listings}
\usepackage{color}

\lstdefinestyle{mystyle}{
keywordstyle=\color{magenta},
backgroundcolor=\color{yellow},
commentstyle=\color{green},
basicstyle=\footnotesize,
}
\lstset{style=mystyle}

\begin{document}


Hello world!

\begin{lstlisting}[language=Python]

print "Hello World!"

\end{lstlisting}

\lstinputlisting[language=C++]{hello.cpp}

Lorem ipsum dolor sit amet \lstinline{print "Hello World"} , consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


\end{document}

```
From this, you can see:

1. To insert a code block, start with `\begin{lstlisting}` and end with `\end{lstlisting}`
2. To import code from another file within the same directory, you can use `lstinputlisiting{name_of_file}`
3. To specify a language for the code, use `[language=C++]`
4. To insert inline code use `\lstinline`
5. To apply custom styles, use the `\usepackage{color}` and define your own style then define the listing with your own theme (Please look at code below). You can modify many things with your own style, but you need to read the doc for the correct property name.
6. Interested ?? More [here](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

Here is how the code above compiles in TexMaker:

![](http://i.imgur.com/XwwDJNo.png)

## Multiple files in LaTeX

When we use LaTeX, we may face a problem that a document is too long to be handle. Therefore, we should divide the file so that its contents can be easily handled.

Let's look at the example:

```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

Hello Latex, This is my second part.

\end{document}
```

It's just a normal LaTeX file. Now, let's divide the document into two parts using the `\input` keyword:


```tex
% main.tex
\documentclass[a4paper]{article}

\begin{document}

Hello Latex, This is my first part.

\input{second_file}

\end{document}
```


```tex
% second_file.tex
Hello Latex, This is my second part.
```

Now the main file looks different, but better documented. Here is the result in TexMaker:

[![multi_file.png](https://s14.postimg.org/deg0kqhu9/multi_file.png)](https://postimg.org/image/hnkqmwl3h/)

:bangbang: **Tips**: For readability, clarity and maintenance purpose, it is highly suggested that you divide your Main file systematically, hierarchically and scientifically. Don't divide without reasons or you may get a mess later.

## Additional Tools

#### Distributions

* [MiKTeX](https://miktex.org/about) for Windows.
* [TeX Live](https://www.tug.org/texlive/) for Linux and Unix-based.
* [MacTeX](https://tug.org/mactex/) for macOS.
* [ShareLaTeX](https://www.sharelatex.com/) — an online editor.
* [Overleaf](https://www.overleaf.com/) — an collaborative online editor.
* [StackEdit](https://stackedit.io/) — In-browser markdown editor.

#### LaTeX Editors

* [TeXMaker](http://www.xm1math.net/texmaker/) Cross platform LaTeX editor.
* [TeXStudio](http://www.texstudio.org/) An enhanced fork of TeXMaker with more features.
* TeXShop and TeXworks (minimal editors)

#### LaTeX Compilers

* Most editors will have an option for you to change the default compiler. Here's an example:

![](http://i.imgur.com/FbNUiL7.png)

## HOORAY!!

:tada: Thank you for finishing the guide. That's basically all you need to know about LaTeX. :hammer:
If you are greatly interested, more on LaTeX can be found [here](http://www.latex-project.org/help/documentation/) or all over the web, depending on your need.

## License

 [![](http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-1.png)](http://www.wtfpl.net/)

**DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE**
Copyright (C) 2016 Luong Vo
Everyone is permitted to copy and distribute verbatim or modified copies of this license document, and changing it is allowed as long as the name is changed.
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION: You just DO WHAT THE FUCK YOU WANT TO.



<div id='donation'/>

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=5ZG5Z47L2ZGYC)

A beer in your country can buy a meal in mine.
