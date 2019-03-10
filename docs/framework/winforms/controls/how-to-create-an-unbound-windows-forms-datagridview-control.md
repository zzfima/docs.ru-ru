---
title: Практическое руководство. Создание элемента управления DataGridView в Windows свободной формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: da59f02c3f0465d330f73cfd5453d5bce58fca12
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718380"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="7bd62-102">Практическое руководство. Создание элемента управления DataGridView в Windows свободной формы</span><span class="sxs-lookup"><span data-stu-id="7bd62-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7bd62-103">В следующем примере кода показано, как выполнить заполнение элемента управления <xref:System.Windows.Forms.DataGridView> программным путем без привязки к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="7bd62-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="7bd62-104">Это полезно при наличии небольшого объема данных, которые нужно отобразить в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bd62-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="7bd62-105">Полное описание этого примера кода, см. в разделе [Пошаговое руководство: Создание не связанного с данными Windows Forms элемента управления DataGridView](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7bd62-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bd62-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7bd62-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7bd62-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7bd62-107">Compiling the Code</span></span>  
 <span data-ttu-id="7bd62-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7bd62-108">This example requires:</span></span>  
  
-   <span data-ttu-id="7bd62-109">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7bd62-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7bd62-110">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7bd62-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7bd62-111">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="7bd62-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7bd62-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7bd62-112">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="7bd62-113">Пошаговое руководство: Создание не связанного с данными Windows Forms элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="7bd62-113">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7bd62-114">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bd62-114">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="7bd62-115">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bd62-115">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
