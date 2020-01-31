---
title: Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742837"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="da163-102">Практическое руководство. Растягивание ToolStripTextBox для заполнения оставшегося пространства элемента управления ToolStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="da163-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="da163-103">Если для свойства <xref:System.Windows.Forms.ToolStrip.Stretch%2A> элемента управления <xref:System.Windows.Forms.ToolStrip> задано значение `true`, элемент управления заполняет его контейнер от сквозного к концу и изменяет размеры при изменении размера контейнера.</span><span class="sxs-lookup"><span data-stu-id="da163-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="da163-104">В такой конфигурации может оказаться полезным растяжение элемента в элементе управления, например <xref:System.Windows.Forms.ToolStripTextBox>, для заполнения доступного пространства и изменения размера при изменении размера элемента управления.</span><span class="sxs-lookup"><span data-stu-id="da163-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="da163-105">Такое растяжение полезно, например, если требуется обеспечить внешний вид и поведение, аналогичные адресной строке в Microsoft® Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="da163-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da163-106">Пример</span><span class="sxs-lookup"><span data-stu-id="da163-106">Example</span></span>  
 <span data-ttu-id="da163-107">В следующем примере кода представлен класс, производный от <xref:System.Windows.Forms.ToolStripTextBox> с именем `ToolStripSpringTextBox`.</span><span class="sxs-lookup"><span data-stu-id="da163-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="da163-108">Этот класс переопределяет метод <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>, чтобы вычислить доступную ширину родительского элемента управления <xref:System.Windows.Forms.ToolStrip> после вычитания общей ширины всех остальных элементов.</span><span class="sxs-lookup"><span data-stu-id="da163-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="da163-109">Этот пример кода также предоставляет класс <xref:System.Windows.Forms.Form> и класс `Program` для демонстрации нового поведения.</span><span class="sxs-lookup"><span data-stu-id="da163-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da163-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="da163-110">Compiling the Code</span></span>  
 <span data-ttu-id="da163-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="da163-111">This example requires:</span></span>  
  
- <span data-ttu-id="da163-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="da163-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da163-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="da163-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="da163-114">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="da163-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="da163-115">Практическое руководство. Интерактивное использование свойства Spring в элементе управления StatusStrip</span><span class="sxs-lookup"><span data-stu-id="da163-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
