---
title: Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: c9250b723e68ac97d1486a896392bf64c66cdfbc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591594"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a><span data-ttu-id="571aa-102">Практическое руководство. Задание средства визуализации компонента ToolStrip для приложения</span><span class="sxs-lookup"><span data-stu-id="571aa-102">How to: Set the ToolStrip Renderer for an Application</span></span>
<span data-ttu-id="571aa-103">Настройка внешнего вида элементов управления <xref:System.Windows.Forms.ToolStrip> может производиться отдельно для каждого из них или для всех элементов управления <xref:System.Windows.Forms.ToolStrip>, используемых в приложении.</span><span class="sxs-lookup"><span data-stu-id="571aa-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> controls individually or for all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="571aa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="571aa-104">Example</span></span>  
 <span data-ttu-id="571aa-105">В примере кода ниже показано, как выборочно применить пользовательское средство отрисовки к элементу управления <xref:System.Windows.Forms.ToolStrip> и элементу управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="571aa-105">The following code example demonstrates how to selectively apply a custom renderer to a <xref:System.Windows.Forms.ToolStrip> control and a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="571aa-106">Чтобы использовать этот пример, скомпилируйте и запустите приложение, а затем выберите область пользовательской отрисовки в элементе управления <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="571aa-106">To use this code example, compile and run the application, and then select the scope of the custom rending from the <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="571aa-107">Нажмите **Применить**, чтобы задать средство отрисовки.</span><span class="sxs-lookup"><span data-stu-id="571aa-107">Click **Apply** to set the renderer.</span></span>  
  
 <span data-ttu-id="571aa-108">Чтобы увидеть пользовательскую отрисовку элемента меню, выберите <xref:System.Windows.Forms.MenuStrip> параметр из <xref:System.Windows.Forms.ComboBox> управлять, щелкните **применить**, а затем откройте **файл** пункта меню.</span><span class="sxs-lookup"><span data-stu-id="571aa-108">To see custom menu item rendering, select the <xref:System.Windows.Forms.MenuStrip> option from the <xref:System.Windows.Forms.ComboBox> control, click **Apply**, and then open the **File** menu item.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 <span data-ttu-id="571aa-109">Чтобы применить пользовательское средство отрисовки ко всем элементам управления <xref:System.Windows.Forms.ToolStrip>, используемым в приложении, задайте свойство <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="571aa-109">Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to all the <xref:System.Windows.Forms.ToolStrip> controls in your application.</span></span>  
  
 <span data-ttu-id="571aa-110">Чтобы применить пользовательское средство отрисовки к отдельному элементу управления <xref:System.Windows.Forms.ToolStrip>, задайте свойство <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="571aa-110">Set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to apply a custom renderer to an individual <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="571aa-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="571aa-111">Compiling the Code</span></span>  
 <span data-ttu-id="571aa-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="571aa-112">This example requires:</span></span>  
  
- <span data-ttu-id="571aa-113">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="571aa-113">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571aa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="571aa-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="571aa-115">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="571aa-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
