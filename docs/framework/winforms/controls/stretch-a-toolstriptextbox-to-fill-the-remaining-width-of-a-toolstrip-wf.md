---
title: Как выполнить Растягивание ToolStripTextBox пространства для заполнения оставшегося элемента управления ToolStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 411c00743f0a02bdd498211d03b195aaaf023ecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612272"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="46461-102">Как выполнить Растягивание ToolStripTextBox пространства для заполнения оставшегося элемента управления ToolStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="46461-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="46461-103">При задании <xref:System.Windows.Forms.ToolStrip.Stretch%2A> свойство <xref:System.Windows.Forms.ToolStrip> управления `true`, элемент управления заполняет контейнер от начала до конца и изменяет размер при изменении размеров контейнера.</span><span class="sxs-lookup"><span data-stu-id="46461-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="46461-104">В этой конфигурации могут оказаться полезными для растяжения элемента в элементе управления, такие как <xref:System.Windows.Forms.ToolStripTextBox>, чтобы заполнить доступное пространство, так и для изменения размера при изменении размера элемента управления.</span><span class="sxs-lookup"><span data-stu-id="46461-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="46461-105">Таком растягивании полезно, например, если требуется обеспечить внешний вид и поведение, аналогичное в адресную строку обозревателя Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="46461-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46461-106">Пример</span><span class="sxs-lookup"><span data-stu-id="46461-106">Example</span></span>  
 <span data-ttu-id="46461-107">В следующем примере кода предоставляет класс, производный от <xref:System.Windows.Forms.ToolStripTextBox> вызывается `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="46461-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="46461-108">Этот класс переопределяет <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> для расчета доступную ширину родительского <xref:System.Windows.Forms.ToolStrip> управления после вычитания объединенный ширину всех элементов.</span><span class="sxs-lookup"><span data-stu-id="46461-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="46461-109">Этот пример кода также предоставляет <xref:System.Windows.Forms.Form> класса и `Program` для демонстрации нового поведения.</span><span class="sxs-lookup"><span data-stu-id="46461-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46461-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="46461-110">Compiling the Code</span></span>  
 <span data-ttu-id="46461-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="46461-111">This example requires:</span></span>  
  
-   <span data-ttu-id="46461-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="46461-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46461-113">См. также</span><span class="sxs-lookup"><span data-stu-id="46461-113">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="46461-114">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="46461-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="46461-115">Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="46461-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
