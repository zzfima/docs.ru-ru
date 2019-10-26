---
title: Исходный код L2DBForm.xaml.cs
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 882699a76eab3c291cd92c298287bc5d28fb08e1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921158"
---
# <a name="l2dbformxamlcs-source-code"></a><span data-ttu-id="003bb-102">Исходный код L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="003bb-102">L2DBForm.xaml.cs source code</span></span>

<span data-ttu-id="003bb-103">На этой странице содержится содержимое и описание C# исходного кода в файле *L2DBForm.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="003bb-103">This page contains the contents and description of the C# source code in the file *L2DBForm.xaml.cs*.</span></span> <span data-ttu-id="003bb-104">Разделяемый класс L2XDBForm, содержащийся в этом файле, можно разбить на три логических раздела: элементы данных и обработчики событий `OnRemove` и `OnAddBook`.</span><span class="sxs-lookup"><span data-stu-id="003bb-104">The L2XDBForm partial class contained in this file can be divided into three logical sections: data members and the `OnRemove` and `OnAddBook` button click event handlers.</span></span>

## <a name="data-members"></a><span data-ttu-id="003bb-105">Элементы данных</span><span class="sxs-lookup"><span data-stu-id="003bb-105">Data members</span></span>

<span data-ttu-id="003bb-106">Для обеспечения связи этого класса с ресурсами окна из *L2DBForm.xaml* используются два закрытых элемента данных.</span><span class="sxs-lookup"><span data-stu-id="003bb-106">Two private data members are used to associate this class to the window resources used in *L2DBForm.xaml*.</span></span>

- <span data-ttu-id="003bb-107">Переменная пространства имен `myBooks` инициализируется значением `"http://www.mybooks.com"`.</span><span class="sxs-lookup"><span data-stu-id="003bb-107">The namespace variable `myBooks` is initialized to `"http://www.mybooks.com"`.</span></span>

- <span data-ttu-id="003bb-108">Элемент `bookList` инициализируется в конструкторе строкой CDATA из *L2DBForm.xaml* с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="003bb-108">The member `bookList` is initialized in the constructor to the CDATA string in *L2DBForm.xaml* with the following line:</span></span>

    ```csharp
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a><span data-ttu-id="003bb-109">Обработчик события OnAddBook</span><span class="sxs-lookup"><span data-stu-id="003bb-109">OnAddBook event handler</span></span>

<span data-ttu-id="003bb-110">В этом методе содержатся следующие три инструкции.</span><span class="sxs-lookup"><span data-stu-id="003bb-110">This method contains the following three statements:</span></span>

- <span data-ttu-id="003bb-111">Первая условная инструкция используется для проверки правильности ввода.</span><span class="sxs-lookup"><span data-stu-id="003bb-111">The first conditional statement is used for input validation.</span></span>

- <span data-ttu-id="003bb-112">Во второй инструкции создается элемент <xref:System.Xml.Linq.XElement> из строковых значений, введенных пользователем в разделе пользовательского интерфейса **Add New Book**.</span><span class="sxs-lookup"><span data-stu-id="003bb-112">The second statement creates a new <xref:System.Xml.Linq.XElement> from the string values the user entered in the **Add New Book** user interface (UI) section.</span></span>

- <span data-ttu-id="003bb-113">В третьей инструкции происходит добавление этого нового элемента в поставщик данных *L2DBForm.xaml*.</span><span class="sxs-lookup"><span data-stu-id="003bb-113">The last statement adds this new book element to the data provider in *L2DBForm.xaml*.</span></span> <span data-ttu-id="003bb-114">Следовательно, благодаря динамической привязке данных происходит автоматическое обновление пользовательского интерфейса с учетом этого нового элемента, поэтому дополнительный пользовательский код не требуется.</span><span class="sxs-lookup"><span data-stu-id="003bb-114">Consequently, dynamic data binding will automatically update the UI with this new item; no extra user-supplied code is required.</span></span>

## <a name="onremove-event-handler"></a><span data-ttu-id="003bb-115">Обработчик события OnRemove</span><span class="sxs-lookup"><span data-stu-id="003bb-115">OnRemove event handler</span></span>

<span data-ttu-id="003bb-116">Обработчик события `OnRemove` сложнее обработчика события `OnAddBook` по двум причинам.</span><span class="sxs-lookup"><span data-stu-id="003bb-116">The `OnRemove` handler is more complicated than the `OnAddBook` handler for two reasons.</span></span> <span data-ttu-id="003bb-117">Во-первых, необработанный код XML содержит сохраненные пробелы, поэтому в записи книги следует также удалить соответствующие символы перевода строки.</span><span class="sxs-lookup"><span data-stu-id="003bb-117">First, because the raw XML contains preserved white space, matching newlines must also be removed with the book entry.</span></span> <span data-ttu-id="003bb-118">Во-вторых, выделение, которое относилось к удаленному элементу, для удобства переустанавливается на предыдущий элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="003bb-118">Second, as a convenience, the selection, which was on the deleted item, is reset to the previous one in the list.</span></span>

<span data-ttu-id="003bb-119">Но основная работа по удалению выделенного элемента выполняется только двумя инструкциями.</span><span class="sxs-lookup"><span data-stu-id="003bb-119">However, the core work of removing the selected book item is accomplished by only two statements:</span></span>

- <span data-ttu-id="003bb-120">Вначале извлекается элемент книги, связанный с выделенным в настоящее время пунктом в окне списка.</span><span class="sxs-lookup"><span data-stu-id="003bb-120">First, the book element associated with the currently selected item in the list box is retrieved:</span></span>

    ```csharp
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

- <span data-ttu-id="003bb-121">Затем этот элемент удаляется из поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="003bb-121">Then, this element is deleted from the data provider:</span></span>

    ```csharp
    selBook.Remove();
    ```

<span data-ttu-id="003bb-122">И в этом случае динамическая привязка данных обеспечивает автоматическое обновление пользовательского интерфейса программы.</span><span class="sxs-lookup"><span data-stu-id="003bb-122">Again, dynamic data binding assures that the program's UI is automatically updated.</span></span>

## <a name="example"></a><span data-ttu-id="003bb-123">Пример</span><span class="sxs-lookup"><span data-stu-id="003bb-123">Example</span></span>

### <a name="code"></a><span data-ttu-id="003bb-124">Код</span><span class="sxs-lookup"><span data-stu-id="003bb-124">Code</span></span>

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}
```

### <a name="comments"></a><span data-ttu-id="003bb-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="003bb-125">Comments</span></span>

<span data-ttu-id="003bb-126">Сведения о связанном источнике данных XAML для этих обработчиков см. в статье [L2DBForm.xaml Source Code](l2dbform-xaml-source-code.md) (Исходный код L2DBForm.xaml).</span><span class="sxs-lookup"><span data-stu-id="003bb-126">For the associated XAML source for these handlers, see [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="003bb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="003bb-127">See also</span></span>

- [<span data-ttu-id="003bb-128">Пошаговое руководство. Пример LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="003bb-128">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="003bb-129">Исходный код L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="003bb-129">L2DBForm.xaml source code</span></span>](l2dbform-xaml-source-code.md)
