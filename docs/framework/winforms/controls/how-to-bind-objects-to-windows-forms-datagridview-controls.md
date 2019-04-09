---
title: Практическое руководство. Связывание объектов с элементами управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 02c4f94eddfcf782d7d2323787d9b6a9b18db2d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180262"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="7fa1c-102">Практическое руководство. Связывание объектов с элементами управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fa1c-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="7fa1c-103">В следующем примере кода показано, как связать коллекцию объектов с элементом управления <xref:System.Windows.Forms.DataGridView>, чтобы каждый объект отображался отдельной строкой.</span><span class="sxs-lookup"><span data-stu-id="7fa1c-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="7fa1c-104">В этом примере также показано, как отобразить свойство с типом перечисления в <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, чтобы в раскрывающемся списке для поля со списком содержались значения перечисления.</span><span class="sxs-lookup"><span data-stu-id="7fa1c-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fa1c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="7fa1c-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7fa1c-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7fa1c-106">Compiling the Code</span></span>  
 <span data-ttu-id="7fa1c-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7fa1c-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7fa1c-108">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="7fa1c-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7fa1c-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7fa1c-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7fa1c-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="7fa1c-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fa1c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7fa1c-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="7fa1c-112">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fa1c-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7fa1c-113">Практическое руководство. Доступ к связанным объектам в строках DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fa1c-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
