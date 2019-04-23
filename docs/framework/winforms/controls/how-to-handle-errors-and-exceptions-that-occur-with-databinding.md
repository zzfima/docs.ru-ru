---
title: Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 709db2a98074e3322adad8b1275b3c4418c14636
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084626"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="e1f3f-102">Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными</span><span class="sxs-lookup"><span data-stu-id="e1f3f-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="e1f3f-103">Зачастую при привязке базовых бизнес-объектов к элементам управления возникают ошибки и исключения.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="e1f3f-104">Эти ошибки и исключения можно перехватывать, а затем исправлять или передавать сведения об ошибке пользователю путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete> для конкретного компонента <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> или <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f3f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e1f3f-105">Example</span></span>  
 <span data-ttu-id="e1f3f-106">В данном примере кода показан способ обработки ошибок и исключений, возникающих при выполнении операции привязки данных.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="e1f3f-107">Он демонстрирует перехват ошибок путем обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> объектов <xref:System.Windows.Forms.Binding>.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="e1f3f-108">Для перехвата ошибок и исключений с помощью обработки этого события необходимо включить поддержку форматирования для привязки.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="e1f3f-109">Форматирование можно включить при создании привязки или добавлении в коллекцию привязок, или установив значение свойства <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> равным `true`.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="e1f3f-110">Во время выполнения, если введена пустая строка в качестве имени или значение меньше 100 в качестве числа, то появится окно с сообщением.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="e1f3f-111">Это происходит в результате обработки события <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> для привязок этих текстовых полей.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1f3f-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e1f3f-112">Compiling the Code</span></span>  
 <span data-ttu-id="e1f3f-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e1f3f-113">This example requires:</span></span>  
  
-   <span data-ttu-id="e1f3f-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e1f3f-115">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e1f3f-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e1f3f-116">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="e1f3f-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f3f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e1f3f-117">See also</span></span>

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [<span data-ttu-id="e1f3f-118">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="e1f3f-118">BindingSource Component</span></span>](bindingsource-component.md)
