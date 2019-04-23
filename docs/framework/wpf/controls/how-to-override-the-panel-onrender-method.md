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
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102535"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="7c06b-102">Практическое руководство. Переопределение метода панели OnRender</span><span class="sxs-lookup"><span data-stu-id="7c06b-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="7c06b-103">В этом примере показано, как переопределить <xref:System.Windows.Controls.Panel.OnRender%2A> метод <xref:System.Windows.Controls.Panel> для добавления пользовательских графических эффектов в элемент макета.</span><span class="sxs-lookup"><span data-stu-id="7c06b-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c06b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7c06b-104">Example</span></span>  
 <span data-ttu-id="7c06b-105">Используйте <xref:System.Windows.Controls.Panel.OnRender%2A> метод для добавления графических эффектов к элементу отображаемой панели.</span><span class="sxs-lookup"><span data-stu-id="7c06b-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="7c06b-106">Например этот метод можно использовать для добавления пользовательских границу или фон эффекты.</span><span class="sxs-lookup"><span data-stu-id="7c06b-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="7c06b-107">Объект <xref:System.Windows.Media.DrawingContext> объект передается как аргумент, который предоставляет методы для рисования фигур, текста, изображений и видео.</span><span class="sxs-lookup"><span data-stu-id="7c06b-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="7c06b-108">Таким образом этот метод полезен для настройки объекта панели.</span><span class="sxs-lookup"><span data-stu-id="7c06b-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c06b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7c06b-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="7c06b-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="7c06b-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="7c06b-111">Пример пользовательской радиальной панели</span><span class="sxs-lookup"><span data-stu-id="7c06b-111">Custom Radial Panel Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159982)
- [<span data-ttu-id="7c06b-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="7c06b-112">How-to Topics</span></span>](panel-how-to-topics.md)
