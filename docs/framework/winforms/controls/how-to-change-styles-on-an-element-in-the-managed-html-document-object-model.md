---
title: "Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968dd4210e13e301ba2f0ca24617df23706cefc0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="d3853-102">Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="d3853-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="d3853-103">Стили в формате HTML можно использовать для управления внешним видом документа и его элементов.</span><span class="sxs-lookup"><span data-stu-id="d3853-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="d3853-104"><xref:System.Windows.Forms.HtmlDocument>и <xref:System.Windows.Forms.HtmlElement> поддерживает <xref:System.Windows.Forms.HtmlElement.Style%2A> свойств, которые принимают строки в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="d3853-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>  
  
 `name1:value1;...;nameN:valueN;`  
  
 <span data-ttu-id="d3853-105">Вот `DIV` со строкой стиля, задающей шрифт Arial и весь текст полужирным шрифтом:</span><span class="sxs-lookup"><span data-stu-id="d3853-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>  
  
 `<DIV style="font-face:arial;font-weight:bold;">`  
  
 `Hello, world!`  
  
 `</DIV>`  
  
 <span data-ttu-id="d3853-106">Проблема при управлении стилей с помощью <xref:System.Windows.Forms.HtmlElement.Style%2A> свойство заключается в том, что может оказаться нелегкой задачей Добавление и удаление отдельных параметров стилей из строки.</span><span class="sxs-lookup"><span data-stu-id="d3853-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="d3853-107">Например, он стал бы сложная процедура для отображение текста курсивом, при наведении курсора на `DIV`и отключение курсивного начертания, когда курсор покидает `DIV`.</span><span class="sxs-lookup"><span data-stu-id="d3853-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="d3853-108">Времени может возникнуть проблема, если необходимо управлять большим числом стили таким образом.</span><span class="sxs-lookup"><span data-stu-id="d3853-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>  
  
 <span data-ttu-id="d3853-109">Следующая процедура содержит код, который можно использовать, чтобы упростить управление стилями в HTML-документы и элементы.</span><span class="sxs-lookup"><span data-stu-id="d3853-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="d3853-110">Процедура требует, что вы знаете, как для выполнения основных задач в Windows Forms, такие как создание нового проекта и добавление элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="d3853-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>  
  
### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="d3853-111">Для обработки изменений стиля в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3853-111">To process style changes in a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="d3853-112">Создайте проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d3853-112">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="d3853-113">Создайте новый файл класса, в которых заканчиваются расширением, соответствующим выбранному языку программирования.</span><span class="sxs-lookup"><span data-stu-id="d3853-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>  
  
3.  <span data-ttu-id="d3853-114">Копировать `StyleGenerator` класс в следующем примере в этом разделе в файл класса и сохраните код.</span><span class="sxs-lookup"><span data-stu-id="d3853-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>  
  
4.  <span data-ttu-id="d3853-115">Сохраните следующий HTML-код в файл с именем отнести.</span><span class="sxs-lookup"><span data-stu-id="d3853-115">Save the following HTML to a file named Test.htm.</span></span>  
  
    ```  
    <HTML>  
        <BODY>  
  
            <DIV style="font-face:arial;font-weight:bold;">  
                Hello, world!  
            </DIV><P>  
  
            <DIV>  
                Hello again, world!  
            </DIV><P>  
  
        </BODY>  
    </HTML>  
    ```  
  
5.  <span data-ttu-id="d3853-116">Добавить <xref:System.Windows.Forms.WebBrowser> управления с именем `webBrowser1` в главную форму проекта.</span><span class="sxs-lookup"><span data-stu-id="d3853-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>  
  
6.  <span data-ttu-id="d3853-117">Добавьте следующий код в файл кода проекта.</span><span class="sxs-lookup"><span data-stu-id="d3853-117">Add the following code to your project's code file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d3853-118">Убедитесь, что `webBrowser1_DocumentCompleted` обработчика событий настраивается в качестве прослушивателя <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий.</span><span class="sxs-lookup"><span data-stu-id="d3853-118">Ensure that the `webBrowser1_DocumentCompleted` event hander is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="d3853-119">В [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], дважды щелкните на <xref:System.Windows.Forms.WebBrowser> управления; в текстовом редакторе, настройте прослушиватель программными средствами.</span><span class="sxs-lookup"><span data-stu-id="d3853-119">In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>  
  
     [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]  
  
7.  <span data-ttu-id="d3853-120">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="d3853-120">Run the project.</span></span> <span data-ttu-id="d3853-121">Наведите курсор на первый `DIV` Обратите внимание на действия кода.</span><span class="sxs-lookup"><span data-stu-id="d3853-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3853-122">Пример</span><span class="sxs-lookup"><span data-stu-id="d3853-122">Example</span></span>  
 <span data-ttu-id="d3853-123">В следующем примере кода показан полный код для `StyleGenerator` класс, который выполняет синтаксический анализ значение существующего стиля, поддерживает добавление, изменение и удаление стилей и возвращает значение нового стиля с требуемыми изменениями.</span><span class="sxs-lookup"><span data-stu-id="d3853-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>  
  
 [!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
 [!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d3853-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d3853-124">See Also</span></span>  
 <xref:System.Windows.Forms.HtmlElement>
