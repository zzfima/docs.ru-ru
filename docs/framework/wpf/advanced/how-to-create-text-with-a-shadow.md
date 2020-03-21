---
title: Практическое руководство. Создание текста с тенью
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186851"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="ee904-102">Практическое руководство. Создание текста с тенью</span><span class="sxs-lookup"><span data-stu-id="ee904-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="ee904-103">Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="ee904-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee904-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ee904-104">Example</span></span>  
 <span data-ttu-id="ee904-105">Объект <xref:System.Windows.Media.Effects.DropShadowEffect> позволяет создавать различные эффекты тени [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] падения для объектов.</span><span class="sxs-lookup"><span data-stu-id="ee904-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="ee904-106">В следующем примере показано применение эффекта тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="ee904-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="ee904-107">В этом случае используется мягкая тень, то есть цвет тени размывается.</span><span class="sxs-lookup"><span data-stu-id="ee904-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Текстовая тень с мягкостью &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="ee904-109">Вы можете управлять шириной тени, <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> установив свойство.</span><span class="sxs-lookup"><span data-stu-id="ee904-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="ee904-110">Значение `4.0` указывает на ширину тени 4 пикселя.</span><span class="sxs-lookup"><span data-stu-id="ee904-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="ee904-111">Вы можете контролировать мягкость, или размытие, <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> тени, изменяя свойство.</span><span class="sxs-lookup"><span data-stu-id="ee904-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="ee904-112">Значение `0.0` указывает на отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="ee904-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="ee904-113">В следующем примере кода показано создание мягкой тени.</span><span class="sxs-lookup"><span data-stu-id="ee904-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="ee904-114">Эти эффекты теней [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] не проходят через конвейер визуализации текста.</span><span class="sxs-lookup"><span data-stu-id="ee904-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="ee904-115">Следовательно, тип ClearType при использовании этих эффектов отключен.</span><span class="sxs-lookup"><span data-stu-id="ee904-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="ee904-116">В следующем примере показано применение эффекта жесткой тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="ee904-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="ee904-117">В этом случае тень не размыта.</span><span class="sxs-lookup"><span data-stu-id="ee904-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Текстовая тень с мягкостью &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="ee904-119">Можно создать твердую тень, <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> установив `0.0`свойство, что указывает на то, что размытие не используется.</span><span class="sxs-lookup"><span data-stu-id="ee904-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="ee904-120">Вы можете управлять направлением тени, <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> изменяя свойство.</span><span class="sxs-lookup"><span data-stu-id="ee904-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="ee904-121">Установите направленную стоимость этого свойства `0` в `360`определенной степени между и .</span><span class="sxs-lookup"><span data-stu-id="ee904-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="ee904-122">На следующей иллюстрации показаны <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> значения направления настройки свойства.</span><span class="sxs-lookup"><span data-stu-id="ee904-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Параметр степени тени DropShadow](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="ee904-124">В следующем примере кода показано создание жесткой тени.</span><span class="sxs-lookup"><span data-stu-id="ee904-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="ee904-125">Использование эффекта размытия</span><span class="sxs-lookup"><span data-stu-id="ee904-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="ee904-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> может быть использован для создания эффекта, похожего на тени, который может быть размещен за текстовым объектом.</span><span class="sxs-lookup"><span data-stu-id="ee904-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="ee904-127">Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.</span><span class="sxs-lookup"><span data-stu-id="ee904-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="ee904-128">В следующем примере показан эффект размытия, примененный к тексту.</span><span class="sxs-lookup"><span data-stu-id="ee904-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Тень текста с использованием BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="ee904-130">В следующем примере кода показано создание эффекта размытия.</span><span class="sxs-lookup"><span data-stu-id="ee904-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="ee904-131">Использование преобразования переноса</span><span class="sxs-lookup"><span data-stu-id="ee904-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="ee904-132">A <xref:System.Windows.Media.TranslateTransform> может быть использован для создания эффекта, похожего на тени, который может быть размещен за текстовым объектом.</span><span class="sxs-lookup"><span data-stu-id="ee904-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="ee904-133">В следующем примере <xref:System.Windows.Media.TranslateTransform> кода используется для смещения текста.</span><span class="sxs-lookup"><span data-stu-id="ee904-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="ee904-134">В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.</span><span class="sxs-lookup"><span data-stu-id="ee904-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Тень текста с использованием TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="ee904-136">В следующем примере кода показано создание эффекта тени с помощью преобразования.</span><span class="sxs-lookup"><span data-stu-id="ee904-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
