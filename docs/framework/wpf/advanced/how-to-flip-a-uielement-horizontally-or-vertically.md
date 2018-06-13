---
title: Как отразить объект UIElement по горизонтали или по вертикали
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544399"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="f65e3-102">Как отразить объект UIElement по горизонтали или по вертикали</span><span class="sxs-lookup"><span data-stu-id="f65e3-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="f65e3-103">В этом примере показано, как использовать <xref:System.Windows.Media.ScaleTransform> отражение <xref:System.Windows.UIElement> горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="f65e3-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="f65e3-104">В этом примере <xref:System.Windows.Controls.Button> управления (тип <xref:System.Windows.UIElement>) Перевернутая путем применения <xref:System.Windows.Media.ScaleTransform> для его <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f65e3-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f65e3-105">Пример</span><span class="sxs-lookup"><span data-stu-id="f65e3-105">Example</span></span>  
 <span data-ttu-id="f65e3-106">Кнопка для отражения на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="f65e3-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="f65e3-107">![Кнопка без преобразования](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="f65e3-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="f65e3-108">Элементов пользовательского интерфейса, чтобы отразить</span><span class="sxs-lookup"><span data-stu-id="f65e3-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="f65e3-109">Ниже показан код, который создает кнопку.</span><span class="sxs-lookup"><span data-stu-id="f65e3-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="f65e3-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f65e3-110">Example</span></span>  
 <span data-ttu-id="f65e3-111">Чтобы отразить кнопку горизонтально, создайте <xref:System.Windows.Media.ScaleTransform> и задайте его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство в значение -1.</span><span class="sxs-lookup"><span data-stu-id="f65e3-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="f65e3-112">Применить <xref:System.Windows.Media.ScaleTransform> на кнопку <xref:System.Windows.UIElement.RenderTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f65e3-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="f65e3-113">![Кнопка, перевернута горизонтально &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="f65e3-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="f65e3-114">Кнопка после применения ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="f65e3-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="f65e3-115">Пример</span><span class="sxs-lookup"><span data-stu-id="f65e3-115">Example</span></span>  
 <span data-ttu-id="f65e3-116">Как видно из предыдущего рисунка, кнопка была отражена, но он был перемещен.</span><span class="sxs-lookup"><span data-stu-id="f65e3-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="f65e3-117">Это так, как кнопка была отражена от верхнего левого угла.</span><span class="sxs-lookup"><span data-stu-id="f65e3-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="f65e3-118">Чтобы отразить кнопку на месте, необходимо применить <xref:System.Windows.Media.ScaleTransform> к ее центру, но не его угла.</span><span class="sxs-lookup"><span data-stu-id="f65e3-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="f65e3-119">Простой способ применения <xref:System.Windows.Media.ScaleTransform> к кнопкам центр — задать свойству кнопки <xref:System.Windows.UIElement.RenderTransformOrigin%2A> значение 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="f65e3-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="f65e3-120">![Кнопка, перевернута горизонтально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="f65e3-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="f65e3-121">Кнопка с RenderTransformOrigin 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="f65e3-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="f65e3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f65e3-122">Example</span></span>  
 <span data-ttu-id="f65e3-123">Чтобы отразить кнопку по вертикали, задайте <xref:System.Windows.Media.ScaleTransform> объекта <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойство вместо его <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f65e3-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="f65e3-124">![Кнопка, перевернута вертикально по центру](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="f65e3-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="f65e3-125">По вертикали отраженных кнопки</span><span class="sxs-lookup"><span data-stu-id="f65e3-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65e3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f65e3-126">See Also</span></span>  
 [<span data-ttu-id="f65e3-127">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="f65e3-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
