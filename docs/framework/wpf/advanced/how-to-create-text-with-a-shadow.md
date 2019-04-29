---
title: Практическое руководство. Создание текста с тенью
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: a2225e297dbc0b5f9d49799cb34eb5539746e62e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776848"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="bec35-102">Практическое руководство. Создание текста с тенью</span><span class="sxs-lookup"><span data-stu-id="bec35-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="bec35-103">Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="bec35-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bec35-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bec35-104">Example</span></span>  
 <span data-ttu-id="bec35-105"><xref:System.Windows.Media.Effects.DropShadowEffect> Объекта позволяет создавать разнообразные эффекты тени для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="bec35-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="bec35-106">В следующем примере показано применение эффекта тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="bec35-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="bec35-107">В этом случае используется мягкая тень, то есть цвет тени размывается.</span><span class="sxs-lookup"><span data-stu-id="bec35-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Тень текста с мягкостью &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="bec35-109">Ширину тени можно управлять, задав <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bec35-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="bec35-110">Значение `4.0` обозначает ширину тени, равную 4 точкам.</span><span class="sxs-lookup"><span data-stu-id="bec35-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="bec35-111">Можно управлять мягкости или размытия тени, изменив <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bec35-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="bec35-112">Значение `0.0` указывает на отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="bec35-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="bec35-113">В следующем примере кода показано создание мягкой тени.</span><span class="sxs-lookup"><span data-stu-id="bec35-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="bec35-114">Эти эффекты тени не проходят через [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] конвейера отрисовки текста.</span><span class="sxs-lookup"><span data-stu-id="bec35-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="bec35-115">Следовательно, тип ClearType при использовании этих эффектов отключен.</span><span class="sxs-lookup"><span data-stu-id="bec35-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="bec35-116">В следующем примере показано применение эффекта жесткой тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="bec35-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="bec35-117">В этом случае тень не размыта.</span><span class="sxs-lookup"><span data-stu-id="bec35-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Тень текста с мягкостью &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="bec35-119">Можно создать жесткую тень, задав <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойства `0.0`, который указывает, что отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="bec35-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="bec35-120">Можно контролировать направление тени, изменив <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bec35-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="bec35-121">Значение этого свойства градус от `0` и `360`.</span><span class="sxs-lookup"><span data-stu-id="bec35-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="bec35-122">На следующем рисунке показан значения направления <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> значение свойства.</span><span class="sxs-lookup"><span data-stu-id="bec35-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Параметр степени тени DropShadow](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="bec35-124">В следующем примере кода показано создание жесткой тени.</span><span class="sxs-lookup"><span data-stu-id="bec35-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="bec35-125">Использование эффекта размытия</span><span class="sxs-lookup"><span data-stu-id="bec35-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="bec35-126">Объект <xref:System.Windows.Media.Effects.BlurBitmapEffect> может быть использован для создания аналогичного эффекта тени, который можно разместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="bec35-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="bec35-127">Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.</span><span class="sxs-lookup"><span data-stu-id="bec35-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="bec35-128">В следующем примере показан эффект размытия, примененный к тексту.</span><span class="sxs-lookup"><span data-stu-id="bec35-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Тень текста с использованием BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="bec35-130">В следующем примере кода показано создание эффекта размытия.</span><span class="sxs-lookup"><span data-stu-id="bec35-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="bec35-131">Использование преобразования переноса</span><span class="sxs-lookup"><span data-stu-id="bec35-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="bec35-132">Объект <xref:System.Windows.Media.TranslateTransform> может быть использован для создания аналогичного эффекта тени, который можно разместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="bec35-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="bec35-133">В следующем примере кода используется <xref:System.Windows.Media.TranslateTransform> для смещения текста.</span><span class="sxs-lookup"><span data-stu-id="bec35-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="bec35-134">В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.</span><span class="sxs-lookup"><span data-stu-id="bec35-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Тень текста с использованием TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="bec35-136">В следующем примере кода показано создание эффекта тени с помощью преобразования.</span><span class="sxs-lookup"><span data-stu-id="bec35-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
