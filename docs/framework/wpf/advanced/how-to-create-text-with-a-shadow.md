---
title: Практическое руководство. Создание текста с тенью
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 1b7740284afcda6eab41fb68be3b4a2f032cc77d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544762"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="b7993-102">Практическое руководство. Создание текста с тенью</span><span class="sxs-lookup"><span data-stu-id="b7993-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="b7993-103">Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="b7993-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7993-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b7993-104">Example</span></span>  
 <span data-ttu-id="b7993-105"><xref:System.Windows.Media.Effects.DropShadowEffect> Объектов позволяет создавать разнообразные эффекты тени для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="b7993-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="b7993-106">В следующем примере показано применение эффекта тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="b7993-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="b7993-107">В этом случае используется мягкая тень, то есть цвет тени размывается.</span><span class="sxs-lookup"><span data-stu-id="b7993-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="b7993-108">![Тень текста с мягкостью &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="b7993-108">![Text shadow with Softness &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="b7993-109">Пример текста с мягкой тенью</span><span class="sxs-lookup"><span data-stu-id="b7993-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="b7993-110">Можно задать ширину тени, установив <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b7993-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="b7993-111">Значение `4.0` указывает ширину тени 4 пикселя.</span><span class="sxs-lookup"><span data-stu-id="b7993-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="b7993-112">Можно управлять плавность или размытия тени, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b7993-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="b7993-113">Значение `0.0` указывает отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="b7993-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="b7993-114">В следующем примере кода показано создание мягкой тени.</span><span class="sxs-lookup"><span data-stu-id="b7993-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="b7993-115">Эти эффекты тени не проходят через [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] конвейера отрисовки текста.</span><span class="sxs-lookup"><span data-stu-id="b7993-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="b7993-116">Следовательно, тип ClearType при использовании этих эффектов отключен.</span><span class="sxs-lookup"><span data-stu-id="b7993-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="b7993-117">В следующем примере показано применение эффекта жесткой тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="b7993-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="b7993-118">В этом случае тень не размыта.</span><span class="sxs-lookup"><span data-stu-id="b7993-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="b7993-119">![Тень текста с мягкостью &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="b7993-119">![Text shadow with Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="b7993-120">Пример текста с жесткой тенью</span><span class="sxs-lookup"><span data-stu-id="b7993-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="b7993-121">Жесткой тени можно создать, присвоив <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойства `0.0`, который показывает, что отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="b7993-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="b7993-122">Можно управлять направлением тени, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b7993-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="b7993-123">Значение этого свойства угол между `0` и `360`.</span><span class="sxs-lookup"><span data-stu-id="b7993-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="b7993-124">На следующем рисунке показан направления значения <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> значение свойства.</span><span class="sxs-lookup"><span data-stu-id="b7993-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="b7993-125">![Параметр степени тени DropShadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="b7993-125">![DropShadow degree setting of shadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="b7993-126">Схема направления DropShadow</span><span class="sxs-lookup"><span data-stu-id="b7993-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="b7993-127">В следующем примере кода показано создание жесткой тени.</span><span class="sxs-lookup"><span data-stu-id="b7993-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="b7993-128">Использование эффекта размытия</span><span class="sxs-lookup"><span data-stu-id="b7993-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="b7993-129">Объект <xref:System.Windows.Media.Effects.BlurBitmapEffect> можно использовать для создания эффекта аналогичный тени, который можно поместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="b7993-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="b7993-130">Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.</span><span class="sxs-lookup"><span data-stu-id="b7993-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="b7993-131">В следующем примере показан эффект размытия, примененный к тексту.</span><span class="sxs-lookup"><span data-stu-id="b7993-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="b7993-132">![Тень текста с использованием BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="b7993-132">![Text shadow using a BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="b7993-133">Пример текста с эффектом размытия</span><span class="sxs-lookup"><span data-stu-id="b7993-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="b7993-134">В следующем примере кода показано создание эффекта размытия.</span><span class="sxs-lookup"><span data-stu-id="b7993-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="b7993-135">Использование преобразования переноса</span><span class="sxs-lookup"><span data-stu-id="b7993-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="b7993-136">Объект <xref:System.Windows.Media.TranslateTransform> можно использовать для создания эффекта аналогичный тени, который можно поместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="b7993-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="b7993-137">Следующий пример кода использует <xref:System.Windows.Media.TranslateTransform> для смещения текста.</span><span class="sxs-lookup"><span data-stu-id="b7993-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="b7993-138">В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.</span><span class="sxs-lookup"><span data-stu-id="b7993-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="b7993-139">![Тень текста с использованием TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="b7993-139">![Text shadow using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="b7993-140">Пример текста, в котором преобразование используется для создания эффекта тени</span><span class="sxs-lookup"><span data-stu-id="b7993-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="b7993-141">В следующем примере кода показано создание эффекта тени с помощью преобразования.</span><span class="sxs-lookup"><span data-stu-id="b7993-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
