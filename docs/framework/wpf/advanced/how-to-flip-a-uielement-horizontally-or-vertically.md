---
title: Практическое руководство. Отражение объекта UIElement по горизонтали или по вертикали
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 3dd9a8e2a94acf62973701094e8966c8ebff15c9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356355"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="e50be-102">Практическое руководство. Отражение объекта UIElement по горизонтали или по вертикали</span><span class="sxs-lookup"><span data-stu-id="e50be-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="e50be-103">В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> перевернуть <xref:System.Windows.UIElement> горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="e50be-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="e50be-104">В этом примере <xref:System.Windows.Controls.Button> управления (разновидность <xref:System.Windows.UIElement>) изменилось, применяя <xref:System.Windows.Media.ScaleTransform> для его <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e50be-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50be-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e50be-105">Example</span></span>  
 <span data-ttu-id="e50be-106">Ниже показан кнопка для отражения.</span><span class="sxs-lookup"><span data-stu-id="e50be-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="e50be-107">![Кнопка без преобразования](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="e50be-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="e50be-108">UIElement, чтобы отразить</span><span class="sxs-lookup"><span data-stu-id="e50be-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="e50be-109">Ниже показан код, создающий кнопки.</span><span class="sxs-lookup"><span data-stu-id="e50be-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="e50be-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e50be-110">Example</span></span>  
 <span data-ttu-id="e50be-111">Чтобы отразить кнопку горизонтально, создайте <xref:System.Windows.Media.ScaleTransform> и задайте его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство в значение -1.</span><span class="sxs-lookup"><span data-stu-id="e50be-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="e50be-112">Применить <xref:System.Windows.Media.ScaleTransform> на кнопку <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e50be-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="e50be-113">![Кнопка, перевернута горизонтально &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="e50be-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="e50be-114">Кнопка после применения ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="e50be-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50be-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e50be-115">Example</span></span>  
 <span data-ttu-id="e50be-116">Как видно из предыдущего рисунка, кнопка была отражена, но также была перемещена.</span><span class="sxs-lookup"><span data-stu-id="e50be-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="e50be-117">Том, что кнопка была отражена от верхнего левого угла.</span><span class="sxs-lookup"><span data-stu-id="e50be-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="e50be-118">Чтобы отразить кнопку на месте, необходимо применить <xref:System.Windows.Media.ScaleTransform> его центр, а не его угла.</span><span class="sxs-lookup"><span data-stu-id="e50be-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="e50be-119">Простой способ применить <xref:System.Windows.Media.ScaleTransform> к кнопкам center — присвоить кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A> значение 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="e50be-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="e50be-120">![Кнопка, перевернута горизонтально по центру](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="e50be-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="e50be-121">Кнопка с заданным для rendertransformorigin значением 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="e50be-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50be-122">Пример</span><span class="sxs-lookup"><span data-stu-id="e50be-122">Example</span></span>  
 <span data-ttu-id="e50be-123">Чтобы отразить вертикально кнопку, задайте <xref:System.Windows.Media.ScaleTransform> объекта <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства вместо его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e50be-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="e50be-124">![Кнопка, перевернута вертикально по центру](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="e50be-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="e50be-125">Вертикально отраженная кнопка</span><span class="sxs-lookup"><span data-stu-id="e50be-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50be-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e50be-126">See also</span></span>
- [<span data-ttu-id="e50be-127">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="e50be-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
