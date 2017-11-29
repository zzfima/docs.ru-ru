---
title: "Практическое руководство. Анимация матрицы с помощью ключевых кадров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8c67b5c8e179485083a40aa8a196fbee3e0fc24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="6159c-102">Практическое руководство. Анимация матрицы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="6159c-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="6159c-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="6159c-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6159c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6159c-104">Example</span></span>  
 <span data-ttu-id="6159c-105">В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="6159c-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="6159c-106">В этом примере <xref:System.Windows.Media.MatrixTransform> объект для преобразования его внешний вид и расположение <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="6159c-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="6159c-107">Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> класса для создания двух ключевых кадров и выполняет следующие с ними:</span><span class="sxs-lookup"><span data-stu-id="6159c-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="6159c-108">Анимирует первый <xref:System.Windows.Media.Matrix> во время первого 0,2 секунды.</span><span class="sxs-lookup"><span data-stu-id="6159c-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="6159c-109">В примере изменяется <xref:System.Windows.Media.Matrix.M11%2A> и <xref:System.Windows.Media.Matrix.M12%2A> свойства <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="6159c-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="6159c-110">Это изменение приводит к растягивать и стать неравномерным кнопки.</span><span class="sxs-lookup"><span data-stu-id="6159c-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="6159c-111">В примере также изменяется <xref:System.Windows.Media.Matrix.OffsetX%2A> и <xref:System.Windows.Media.Matrix.OffsetY%2A> свойства, чтобы изменяется положение кнопки.</span><span class="sxs-lookup"><span data-stu-id="6159c-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="6159c-112">Анимация второго <xref:System.Windows.Media.Matrix> начиная с 1,0 секунды.</span><span class="sxs-lookup"><span data-stu-id="6159c-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="6159c-113">Кнопка перемещается в другое место, пока кнопки больше не синхронизована или распространенным.</span><span class="sxs-lookup"><span data-stu-id="6159c-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="6159c-114">Циклическое повторение анимации.</span><span class="sxs-lookup"><span data-stu-id="6159c-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6159c-115">Ключевые кадры, которые являются производными от <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> объекта создать резкие переходы между значениями, перемещение анимации является рывками.</span><span class="sxs-lookup"><span data-stu-id="6159c-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="6159c-116">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="6159c-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6159c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6159c-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="6159c-118">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="6159c-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="6159c-119">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="6159c-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
