---
title: Практическое руководство. Переопределение метода панели OnRender
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666707"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="4f791-102">Практическое руководство. Переопределение метода панели OnRender</span><span class="sxs-lookup"><span data-stu-id="4f791-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="4f791-103">В этом примере показано, как переопределить <xref:System.Windows.Controls.Panel.OnRender%2A> метод, <xref:System.Windows.Controls.Panel> чтобы добавить пользовательские графические эффекты в элемент макета.</span><span class="sxs-lookup"><span data-stu-id="4f791-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f791-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4f791-104">Example</span></span>  
 <span data-ttu-id="4f791-105">Используйте метод <xref:System.Windows.Controls.Panel.OnRender%2A> , чтобы добавить графические эффекты в отображаемый элемент Panel.</span><span class="sxs-lookup"><span data-stu-id="4f791-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="4f791-106">Например, этот метод можно использовать для добавления пользовательской границы или фонового эффекта.</span><span class="sxs-lookup"><span data-stu-id="4f791-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="4f791-107"><xref:System.Windows.Media.DrawingContext> Объект передается в качестве аргумента, который предоставляет методы для рисования фигур, текста, изображений или видео.</span><span class="sxs-lookup"><span data-stu-id="4f791-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="4f791-108">В результате этот метод полезен для настройки объекта Panel.</span><span class="sxs-lookup"><span data-stu-id="4f791-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4f791-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4f791-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="4f791-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="4f791-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="4f791-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="4f791-111">How-to Topics</span></span>](panel-how-to-topics.md)
