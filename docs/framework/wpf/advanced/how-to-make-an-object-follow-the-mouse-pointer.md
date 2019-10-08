---
title: Практическое руководство. Создание объекта, следующего за указателем мыши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005063"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="16530-102">Практическое руководство. Создание объекта, следующего за указателем мыши</span><span class="sxs-lookup"><span data-stu-id="16530-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="16530-103">В этом примере показано, как изменить размеры объекта при перемещении указателя мыши на экран.</span><span class="sxs-lookup"><span data-stu-id="16530-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="16530-104">Пример включает файл [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], который создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], и файл кода программной части, который создает обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="16530-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16530-105">Пример</span><span class="sxs-lookup"><span data-stu-id="16530-105">Example</span></span>  
 <span data-ttu-id="16530-106">Следующий код XAML создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который состоит из <xref:System.Windows.Shapes.Ellipse> внутри <xref:System.Windows.Controls.StackPanel> и присоединяет обработчик событий для события <xref:System.Windows.UIElement.MouseMove>.</span><span class="sxs-lookup"><span data-stu-id="16530-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="16530-107">Следующий программный код создает обработчик событий <xref:System.Windows.UIElement.MouseMove>.</span><span class="sxs-lookup"><span data-stu-id="16530-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="16530-108">При перемещении указателя мыши высота и ширина <xref:System.Windows.Shapes.Ellipse> увеличиваются и уменьшаются.</span><span class="sxs-lookup"><span data-stu-id="16530-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="16530-109">См. также</span><span class="sxs-lookup"><span data-stu-id="16530-109">See also</span></span>

- [<span data-ttu-id="16530-110">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="16530-110">Input Overview</span></span>](input-overview.md)
