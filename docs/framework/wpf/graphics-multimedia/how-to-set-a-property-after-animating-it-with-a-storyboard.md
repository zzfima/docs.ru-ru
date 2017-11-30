---
title: "Практическое руководство. Установка свойства после его анимации с помощью раскадровки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 357a9bb6c1a01b00e7f9bcfc17267797f20366b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="4ab46-102">Практическое руководство. Установка свойства после его анимации с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="4ab46-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="4ab46-103">В некоторых случаях может оказаться, что не удается изменить значение свойства после его анимации.</span><span class="sxs-lookup"><span data-stu-id="4ab46-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab46-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4ab46-104">Example</span></span>  
 <span data-ttu-id="4ab46-105">В следующем примере <xref:System.Windows.Media.Animation.Storyboard> используется для анимации цвет <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="4ab46-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="4ab46-106">Раскадровка инициируется при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="4ab46-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="4ab46-107"><xref:System.Windows.Media.Animation.Timeline.Completed> Событие обрабатывается, чтобы программа получает уведомление при <xref:System.Windows.Media.Animation.ColorAnimation> завершения.</span><span class="sxs-lookup"><span data-stu-id="4ab46-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="4ab46-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4ab46-108">Example</span></span>  
 <span data-ttu-id="4ab46-109">После <xref:System.Windows.Media.Animation.ColorAnimation> завершения программа выполняет попытку изменить синий цвет кисти.</span><span class="sxs-lookup"><span data-stu-id="4ab46-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="4ab46-110">Предыдущий код не отображается никаких действий: кисть остается желтой, что является значением, предоставляемые <xref:System.Windows.Media.Animation.ColorAnimation> , анимация кисти.</span><span class="sxs-lookup"><span data-stu-id="4ab46-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="4ab46-111">Значение базового свойства (базовое значение) фактически изменяется на синий.</span><span class="sxs-lookup"><span data-stu-id="4ab46-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="4ab46-112">Тем не менее, действующие или текущая позиция, значение останется желтый поскольку <xref:System.Windows.Media.Animation.ColorAnimation> по-прежнему переопределяет базовое значение.</span><span class="sxs-lookup"><span data-stu-id="4ab46-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="4ab46-113">Если требуется, чтобы базовое значение вновь стать действительное значение, необходимо остановить влияние свойства анимации.</span><span class="sxs-lookup"><span data-stu-id="4ab46-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="4ab46-114">Это можно сделать с помощью анимации раскадровки тремя способами:</span><span class="sxs-lookup"><span data-stu-id="4ab46-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="4ab46-115">Задать анимации <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства<xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="4ab46-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="4ab46-116">Удалите раскадровку целиком.</span><span class="sxs-lookup"><span data-stu-id="4ab46-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="4ab46-117">Удаление анимации из отдельного свойства.</span><span class="sxs-lookup"><span data-stu-id="4ab46-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="4ab46-118">Задать свойство режима FillBehavior анимации табуляции</span><span class="sxs-lookup"><span data-stu-id="4ab46-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="4ab46-119">Установив <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для <xref:System.Windows.Media.Animation.FillBehavior.Stop>, уведомляет анимацию о прекращении влияния на целевое свойство после достижения конца активного периода.</span><span class="sxs-lookup"><span data-stu-id="4ab46-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="4ab46-120">Удалите раскадровку целиком.</span><span class="sxs-lookup"><span data-stu-id="4ab46-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="4ab46-121">С помощью <xref:System.Windows.Media.Animation.RemoveStoryboard> триггера или <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> метода, вы анимациям раскадровки для остановки влияет на их целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="4ab46-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="4ab46-122">Разница между этим подходом и установкой <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство является раскадровки можно удалить в любое время, а <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство действует только при достижении конца активного периода анимацией.</span><span class="sxs-lookup"><span data-stu-id="4ab46-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="4ab46-123">Удаление анимации из отдельного свойства</span><span class="sxs-lookup"><span data-stu-id="4ab46-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="4ab46-124">Другим способом остановки влияния свойство анимации заключается в использовании <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> метод анимируемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4ab46-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="4ab46-125">Укажите как первый параметр анимируемого свойства и `null` вторым.</span><span class="sxs-lookup"><span data-stu-id="4ab46-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="4ab46-126">Этот способ также работает для анимаций без раскадровки.</span><span class="sxs-lookup"><span data-stu-id="4ab46-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab46-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4ab46-127">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [<span data-ttu-id="4ab46-128">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="4ab46-128">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="4ab46-129">Общие сведения о методах анимации свойств</span><span class="sxs-lookup"><span data-stu-id="4ab46-129">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
