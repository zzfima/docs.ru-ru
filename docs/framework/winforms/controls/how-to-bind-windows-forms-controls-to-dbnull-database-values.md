---
title: Практическое руководство. Специальная обработка значений DBNull при связывании элементов управления с данными в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45bfed3020f0fe148e9f7d33b9ec7dc243eb5c29
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="8fd0b-102">Практическое руководство. Специальная обработка значений DBNull при связывании элементов управления с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd0b-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="8fd0b-103">Если элементы управления Windows Forms привязаны к источнику данных и источник данных возвращает значение <xref:System.DBNull>, соответствующее значение можно заменить без обработки, форматирования или анализа событий.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="8fd0b-104">Свойство <xref:System.Windows.Forms.Binding.NullValue%2A> преобразует <xref:System.DBNull> в указанный объект при форматировании или анализе значений источника данных.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fd0b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8fd0b-105">Example</span></span>  
 <span data-ttu-id="8fd0b-106">В примере ниже демонстрируется привязка значения <xref:System.DBNull> в двух разных случаях.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="8fd0b-107">В первом случае показано, как задать <xref:System.Windows.Forms.Binding.NullValue%2A> для свойства строки; во втором — как задать <xref:System.Windows.Forms.Binding.NullValue%2A> для свойства изображения.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="8fd0b-108">Типы связанного свойства и свойства <xref:System.Windows.Forms.Binding.NullValue%2A> должны быть одинаковыми, иначе произойдет ошибка и следующие значения <xref:System.Windows.Forms.Binding.NullValue%2A> обрабатываться не будут.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="8fd0b-109">В этом случае исключение не создается.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fd0b-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8fd0b-110">Compiling the Code</span></span>  
 <span data-ttu-id="8fd0b-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="8fd0b-111">This example requires:</span></span>  
  
-   <span data-ttu-id="8fd0b-112">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8fd0b-113">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8fd0b-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8fd0b-114">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="8fd0b-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8fd0b-115">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="8fd0b-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd0b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8fd0b-116">See Also</span></span>  
 [<span data-ttu-id="8fd0b-117">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="8fd0b-117">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="8fd0b-118">Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными</span><span class="sxs-lookup"><span data-stu-id="8fd0b-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [<span data-ttu-id="8fd0b-119">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd0b-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
