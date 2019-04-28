---
title: Практическое руководство. Анимация контекстного меню
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911291"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="12ec3-102">Практическое руководство. Анимация контекстного меню</span><span class="sxs-lookup"><span data-stu-id="12ec3-102">How to: Animate a Popup</span></span>
<span data-ttu-id="12ec3-103">В этом примере показаны два способа анимировать <xref:System.Windows.Controls.Primitives.Popup> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="12ec3-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12ec3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="12ec3-104">Example</span></span>  
 <span data-ttu-id="12ec3-105">В следующем примере задается <xref:System.Windows.Controls.Primitives.PopupAnimation> свойство в значение <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, чего <xref:System.Windows.Controls.Primitives.Popup> для «слайд в» когда он появится.</span><span class="sxs-lookup"><span data-stu-id="12ec3-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="12ec3-106">Для смены <xref:System.Windows.Controls.Primitives.Popup>, этот пример назначает <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойство <xref:System.Windows.Controls.Canvas>, который является дочерним элементом элемента <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="12ec3-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="12ec3-107">Для корректной работы преобразования, в примере необходимо присвоить <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="12ec3-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="12ec3-108">Кроме того <xref:System.Windows.FrameworkElement.Margin%2A> на <xref:System.Windows.Controls.Canvas> содержимого необходимо указать достаточно места для <xref:System.Windows.Controls.Primitives.Popup> для поворота.</span><span class="sxs-lookup"><span data-stu-id="12ec3-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="12ec3-109">В следующем примере показан как <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие, возникающее при <xref:System.Windows.Controls.Button> нажатии триггеры <xref:System.Windows.Media.Animation.Storyboard> , запускает анимацию.</span><span class="sxs-lookup"><span data-stu-id="12ec3-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="12ec3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="12ec3-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="12ec3-111">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="12ec3-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="12ec3-112">Общие сведения о контекстном меню</span><span class="sxs-lookup"><span data-stu-id="12ec3-112">Popup Overview</span></span>](popup-overview.md)
