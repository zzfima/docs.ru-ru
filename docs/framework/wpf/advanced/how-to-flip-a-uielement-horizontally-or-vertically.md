---
title: Практическое руководство. Отражение объекта UIElement по горизонтали или вертикали
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767068"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="3bd6e-102">Практическое руководство. Отражение объекта UIElement по горизонтали или вертикали</span><span class="sxs-lookup"><span data-stu-id="3bd6e-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="3bd6e-103">В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> перевернуть <xref:System.Windows.UIElement> горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="3bd6e-104">В этом примере <xref:System.Windows.Controls.Button> управления (разновидность <xref:System.Windows.UIElement>) изменилось, применяя <xref:System.Windows.Media.ScaleTransform> для его <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd6e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd6e-105">Example</span></span>  
 <span data-ttu-id="3bd6e-106">Ниже показан кнопка для отражения.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="3bd6e-107">![Кнопка без преобразования](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="3bd6e-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="3bd6e-108">UIElement, чтобы отразить</span><span class="sxs-lookup"><span data-stu-id="3bd6e-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="3bd6e-109">Ниже показан код, создающий кнопки.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="3bd6e-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd6e-110">Example</span></span>  
 <span data-ttu-id="3bd6e-111">Чтобы отразить кнопку горизонтально, создайте <xref:System.Windows.Media.ScaleTransform> и задайте его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство в значение -1.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="3bd6e-112">Применить <xref:System.Windows.Media.ScaleTransform> на кнопку <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="3bd6e-113">![Кнопка, перевернута горизонтально &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="3bd6e-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="3bd6e-114">Кнопка после применения ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="3bd6e-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd6e-115">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd6e-115">Example</span></span>  
 <span data-ttu-id="3bd6e-116">Как видно из предыдущего рисунка, кнопка была отражена, но также была перемещена.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="3bd6e-117">Том, что кнопка была отражена от верхнего левого угла.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="3bd6e-118">Чтобы отразить кнопку на месте, необходимо применить <xref:System.Windows.Media.ScaleTransform> его центр, а не его угла.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="3bd6e-119">Простой способ применить <xref:System.Windows.Media.ScaleTransform> к кнопкам center — присвоить кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A> значение 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="3bd6e-120">![Кнопка, перевернута горизонтально по центру](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="3bd6e-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="3bd6e-121">Кнопка с заданным для rendertransformorigin значением 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="3bd6e-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd6e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd6e-122">Example</span></span>  
 <span data-ttu-id="3bd6e-123">Чтобы отразить вертикально кнопку, задайте <xref:System.Windows.Media.ScaleTransform> объекта <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства вместо его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3bd6e-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="3bd6e-124">![Кнопка, перевернута вертикально по центру](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="3bd6e-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="3bd6e-125">Вертикально отраженная кнопка</span><span class="sxs-lookup"><span data-stu-id="3bd6e-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd6e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd6e-126">See also</span></span>

- [<span data-ttu-id="3bd6e-127">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="3bd6e-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
