---
title: Как выполнить Назначение средства визуализации компоненту ToolStrip во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: ddedae5bd7a58b7d8babca7f92bb261a10d2ddee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511999"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="6dfe1-102">Как выполнить Назначение средства визуализации компоненту ToolStrip во время выполнения</span><span class="sxs-lookup"><span data-stu-id="6dfe1-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="6dfe1-103">С помощью пользовательского класса `ProfessionalColorTable` можно настраивать внешний вид элемента управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dfe1-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6dfe1-104">Example</span></span>  
 <span data-ttu-id="6dfe1-105">В примере кода ниже показано создание пользовательского класса `ProfessionalColorTable`.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="6dfe1-106">Этот класс определяет градиент для элементов управления <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="6dfe1-107">Чтобы использовать этот пример, выполните компиляцию и запуск приложения, после чего нажмите **Изменить цвета** для применения градиентов, определенных в классе `ProfessionalColorTable`.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="6dfe1-108">Определение пользовательского класса ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="6dfe1-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="6dfe1-109">Пользовательские градиенты определяются в классе `CustomProfessionalColors`.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="6dfe1-110">Назначение пользовательского средства отрисовки</span><span class="sxs-lookup"><span data-stu-id="6dfe1-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="6dfe1-111">Создайте новое средство отрисовки `ToolStripProfessionalRenderer` с классом `CustomProfessionalColors` и присвойте его свойству <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6dfe1-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6dfe1-112">Compiling the Code</span></span>  
 <span data-ttu-id="6dfe1-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6dfe1-113">This example requires:</span></span>  
  
-   <span data-ttu-id="6dfe1-114">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="6dfe1-115">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6dfe1-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6dfe1-116">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6dfe1-117">Также см. раздел [Как Компиляция и выполнение примера кода завершения Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6dfe1-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dfe1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6dfe1-118">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="6dfe1-119">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6dfe1-119">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
