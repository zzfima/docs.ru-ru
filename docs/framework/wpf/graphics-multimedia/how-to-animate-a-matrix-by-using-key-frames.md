---
title: Практическое руководство. Анимация матрицы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963029"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="e9ecb-102">Практическое руководство. Анимация матрицы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="e9ecb-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="e9ecb-103">В этом примере показано <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform> , как анимировать свойство объекта с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ecb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e9ecb-104">Example</span></span>  
 <span data-ttu-id="e9ecb-105">В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> класс используется для <xref:System.Windows.Media.MatrixTransform.Matrix%2A> анимации свойства объекта <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="e9ecb-106">В примере используется <xref:System.Windows.Media.MatrixTransform> объект для преобразования внешнего вида и расположения <xref:System.Windows.Controls.Button>объекта.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="e9ecb-107">Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> класс для создания двух ключевых кадров и выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="e9ecb-108">Выполняет анимацию первой <xref:System.Windows.Media.Matrix> в течение первых 0,2 секунд.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="e9ecb-109">В этом примере изменяются <xref:System.Windows.Media.Matrix.M11%2A> свойства и <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.Matrix.M12%2A> объекта.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="e9ecb-110">Это изменение приводит к тому, что кнопка растягивается и становится неравномерной.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="e9ecb-111">В этом примере также изменяются <xref:System.Windows.Media.Matrix.OffsetX%2A> свойства и <xref:System.Windows.Media.Matrix.OffsetY%2A> , чтобы кнопка изменила расположение.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="e9ecb-112">Анимируется секунды <xref:System.Windows.Media.Matrix> в 1,0 секунд.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="e9ecb-113">Кнопка перемещается в другую точку, пока кнопка больше не наклонена или не растягивается.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="e9ecb-114">Повтор анимации в течение неограниченного времени.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9ecb-115">Ключевые кадры, производные от <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> объекта, создают резкие переходы между значениями, то есть перемещение анимации жерки.</span><span class="sxs-lookup"><span data-stu-id="e9ecb-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e9ecb-116">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="e9ecb-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ecb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e9ecb-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="e9ecb-118">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e9ecb-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e9ecb-119">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e9ecb-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
