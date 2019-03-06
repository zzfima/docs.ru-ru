---
title: Практическое руководство. Применение преобразования к тексту
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: fd86293c539bf58ac93894e0b879dddb984825e1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378954"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="699c9-102">Практическое руководство. Применение преобразования к тексту</span><span class="sxs-lookup"><span data-stu-id="699c9-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="699c9-103">Преобразования могут менять отображение текста в приложении.</span><span class="sxs-lookup"><span data-stu-id="699c9-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="699c9-104">В следующих примерах используются различные типы преобразований отрисовки влияющие на отображение текста в <xref:System.Windows.Controls.TextBlock> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="699c9-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="699c9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="699c9-105">Example</span></span>  
 <span data-ttu-id="699c9-106">В следующем примере показан текст, повернутый относительно заданной точки в двухмерной плоскости x-y.</span><span class="sxs-lookup"><span data-stu-id="699c9-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="699c9-107">![Текст, повернутый с использованием RotateTransform](./media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="699c9-107">![Text rotated using a RotateTransform](./media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="699c9-108">Пример текста, повернутого на 90 градусов</span><span class="sxs-lookup"><span data-stu-id="699c9-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="699c9-109">В следующем примере кода используется <xref:System.Windows.Media.RotateTransform> вращение текста.</span><span class="sxs-lookup"><span data-stu-id="699c9-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="699c9-110"><xref:System.Windows.Media.RotateTransform.Angle%2A> Значение 90, поворачивает элемент на 90 градусов по часовой стрелке.</span><span class="sxs-lookup"><span data-stu-id="699c9-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="699c9-111">В следующем примере показаны вторая строка текста, масштабированная на 150 % вдоль оси X, и третья строка текста, масштабированная на 150 % вдоль оси Y.</span><span class="sxs-lookup"><span data-stu-id="699c9-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="699c9-112">![Текст, масштабируемый с использованием ScaleTransform](./media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="699c9-112">![Text scaled using a ScaleTransform](./media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="699c9-113">Пример масштабированного текста</span><span class="sxs-lookup"><span data-stu-id="699c9-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="699c9-114">В следующем примере кода используется <xref:System.Windows.Media.ScaleTransform> для масштабирования текста из исходного размера.</span><span class="sxs-lookup"><span data-stu-id="699c9-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="699c9-115">Масштабирование текста не равнозначно увеличению шрифта текста.</span><span class="sxs-lookup"><span data-stu-id="699c9-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="699c9-116">Размеры шрифта рассчитываются независимо друг от друга, чтобы обеспечить оптимальное разрешение для разных размеров.</span><span class="sxs-lookup"><span data-stu-id="699c9-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="699c9-117">В масштабированном тексте, с другой стороны, сохранены пропорции текста исходного размера.</span><span class="sxs-lookup"><span data-stu-id="699c9-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="699c9-118">В следующем примере показан текст, наклоненный вдоль оси X.</span><span class="sxs-lookup"><span data-stu-id="699c9-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="699c9-119">![Текст, наклоненный с использованием SkewTransform](./media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="699c9-119">![Text skewed using a SkewTransform](./media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="699c9-120">Пример наклоненного текста</span><span class="sxs-lookup"><span data-stu-id="699c9-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="699c9-121">В следующем примере кода используется <xref:System.Windows.Media.SkewTransform> для наклона текста.</span><span class="sxs-lookup"><span data-stu-id="699c9-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="699c9-122">Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат.</span><span class="sxs-lookup"><span data-stu-id="699c9-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="699c9-123">В этом примере две текстовые строки, наклоненные на –30° и 30° вдоль оси X.</span><span class="sxs-lookup"><span data-stu-id="699c9-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="699c9-124">В следующем примере показан текст, преобразованный (или перемещенный) вдоль осей X и Y.</span><span class="sxs-lookup"><span data-stu-id="699c9-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="699c9-125">![Смещение текста с использованием TranslateTransform](./media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="699c9-125">![Text offset using a TranslateTransform](./media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="699c9-126">Пример преобразованного текста</span><span class="sxs-lookup"><span data-stu-id="699c9-126">Example of translated text</span></span>  
  
 <span data-ttu-id="699c9-127">В следующем примере кода используется <xref:System.Windows.Media.TranslateTransform> для смещения текста.</span><span class="sxs-lookup"><span data-stu-id="699c9-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="699c9-128">В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.</span><span class="sxs-lookup"><span data-stu-id="699c9-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="699c9-129"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> Предоставляет широкий набор функций для создания эффектов тени.</span><span class="sxs-lookup"><span data-stu-id="699c9-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="699c9-130">Дополнительные сведения см. в разделе [Создание текста с тенью](how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="699c9-130">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699c9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="699c9-131">See also</span></span>
- [<span data-ttu-id="699c9-132">Применение анимаций к тексту</span><span class="sxs-lookup"><span data-stu-id="699c9-132">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
