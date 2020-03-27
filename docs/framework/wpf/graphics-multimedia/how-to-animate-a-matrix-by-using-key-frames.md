---
title: Практическое руководство. Анимация матрицы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344920"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="2d627-102">Практическое руководство. Анимация матрицы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="2d627-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="2d627-103">В этом примере показано, <xref:System.Windows.Media.MatrixTransform.Matrix%2A> как <xref:System.Windows.Media.MatrixTransform> оживить свойство элемента с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="2d627-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d627-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2d627-104">Example</span></span>  
 <span data-ttu-id="2d627-105">В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.MatrixTransform.Matrix%2A> для анимировать свойство <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="2d627-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="2d627-106">Пример использует <xref:System.Windows.Media.MatrixTransform> объект для преобразования внешнего вида <xref:System.Windows.Controls.Button>и положения .</span><span class="sxs-lookup"><span data-stu-id="2d627-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="2d627-107">Эта анимация <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> использует класс для создания двух ключевых кадров и делает следующее с ними:</span><span class="sxs-lookup"><span data-stu-id="2d627-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="2d627-108">Оживляет первое <xref:System.Windows.Media.Matrix> в течение первых 0,2 секунды.</span><span class="sxs-lookup"><span data-stu-id="2d627-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="2d627-109">Пример изменяет <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A> свойства <xref:System.Windows.Media.Matrix>и свойства .</span><span class="sxs-lookup"><span data-stu-id="2d627-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="2d627-110">Это изменение приводит к тому, что кнопка растягивается и становится искаженной.</span><span class="sxs-lookup"><span data-stu-id="2d627-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="2d627-111">Пример также <xref:System.Windows.Media.Matrix.OffsetX%2A> изменяет <xref:System.Windows.Media.Matrix.OffsetY%2A> свойства так, чтобы кнопка изменяла положение.</span><span class="sxs-lookup"><span data-stu-id="2d627-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="2d627-112">Оживляет второе <xref:System.Windows.Media.Matrix> место на 1,0 секунды.</span><span class="sxs-lookup"><span data-stu-id="2d627-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="2d627-113">Кнопка перемещается в другое положение, в то время как кнопка больше не перекос или растягивается.</span><span class="sxs-lookup"><span data-stu-id="2d627-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="2d627-114">Повторяет анимацию на неопределенный срок.</span><span class="sxs-lookup"><span data-stu-id="2d627-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d627-115">Ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> получаемые из объекта, создают резкие скачки между значениями, то есть движение анимации отрывисто.</span><span class="sxs-lookup"><span data-stu-id="2d627-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="2d627-116">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="2d627-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d627-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2d627-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="2d627-118">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="2d627-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="2d627-119">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="2d627-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
