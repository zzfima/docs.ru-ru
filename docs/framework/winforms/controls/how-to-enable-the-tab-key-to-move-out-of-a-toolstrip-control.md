---
title: Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: d4de7345a4e3ce122c4e1fc0a92f09b447204eb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113169"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="acbb5-102">Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB</span><span class="sxs-lookup"><span data-stu-id="acbb5-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="acbb5-103">Используйте следующую процедуру, чтобы пользователь мог нажать клавишу TAB для перемещения из <xref:System.Windows.Forms.ToolStrip> к следующему элементу управления в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="acbb5-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="acbb5-104"><xref:System.Windows.Forms.ToolStrip> Принимает первое нажатие клавиши TAB и ключи стрелку, выберите элементы в <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="acbb5-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="acbb5-105">При нажатии клавиши TAB во второй раз, он направляет пользователя к следующему элементу управления в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="acbb5-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="acbb5-106">Чтобы пользователь мог нажать клавишу TAB для перемещения от элемента управления ToolStrip к следующему элементу управления</span><span class="sxs-lookup"><span data-stu-id="acbb5-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="acbb5-107">Задайте <xref:System.Windows.Forms.ToolStrip.TabStop%2A> свойство <xref:System.Windows.Forms.ToolStrip> для `true`.</span><span class="sxs-lookup"><span data-stu-id="acbb5-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbb5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="acbb5-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="acbb5-109">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="acbb5-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
