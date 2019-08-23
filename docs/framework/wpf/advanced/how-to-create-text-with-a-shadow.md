---
title: Практическое руководство. Создание текста с тенью
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 0fe64e4e9e7aadbd30a38743647251f9fa49ba95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960443"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="a7340-102">Практическое руководство. Создание текста с тенью</span><span class="sxs-lookup"><span data-stu-id="a7340-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="a7340-103">Примеры в этом разделе демонстрируют создание эффекта тени для отображаемого текста.</span><span class="sxs-lookup"><span data-stu-id="a7340-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7340-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a7340-104">Example</span></span>  
 <span data-ttu-id="a7340-105">Объект позволяет создавать разнообразные эффекты тени для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] объектов. <xref:System.Windows.Media.Effects.DropShadowEffect></span><span class="sxs-lookup"><span data-stu-id="a7340-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="a7340-106">В следующем примере показано применение эффекта тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="a7340-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="a7340-107">В этом случае используется мягкая тень, то есть цвет тени размывается.</span><span class="sxs-lookup"><span data-stu-id="a7340-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Тень текста с мягкостью &#61; 0,25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg) 
  
 <span data-ttu-id="a7340-109">Можно управлять шириной тени, задавая <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a7340-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="a7340-110">Значение `4.0` указывает, что ширина тени равна 4 пикселям.</span><span class="sxs-lookup"><span data-stu-id="a7340-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="a7340-111">Можно управлять мягкостью тени или размытием, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a7340-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="a7340-112">Значение `0.0` указывает на отсутствие размытия.</span><span class="sxs-lookup"><span data-stu-id="a7340-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="a7340-113">В следующем примере кода показано создание мягкой тени.</span><span class="sxs-lookup"><span data-stu-id="a7340-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="a7340-114">Эти эффекты тени не проходят через [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] конвейер отрисовки текста.</span><span class="sxs-lookup"><span data-stu-id="a7340-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="a7340-115">Следовательно, тип ClearType при использовании этих эффектов отключен.</span><span class="sxs-lookup"><span data-stu-id="a7340-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="a7340-116">В следующем примере показано применение эффекта жесткой тени к тексту.</span><span class="sxs-lookup"><span data-stu-id="a7340-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="a7340-117">В этом случае тень не размыта.</span><span class="sxs-lookup"><span data-stu-id="a7340-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Тень текста с мягкостью &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg) 
  
 <span data-ttu-id="a7340-119">Можно создать жесткую тень, присвоив <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> `0.0`свойству значение, которое указывает, что размытие не используется.</span><span class="sxs-lookup"><span data-stu-id="a7340-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="a7340-120">Можно управлять направлением тени, изменяя <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a7340-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="a7340-121">Задайте в качестве значения для этого свойства степень между `0` и. `360`</span><span class="sxs-lookup"><span data-stu-id="a7340-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="a7340-122">На следующем рисунке показаны направленные значения <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> параметра свойства.</span><span class="sxs-lookup"><span data-stu-id="a7340-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Параметр степени тени DropShadow](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="a7340-124">В следующем примере кода показано создание жесткой тени.</span><span class="sxs-lookup"><span data-stu-id="a7340-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="a7340-125">Использование эффекта размытия</span><span class="sxs-lookup"><span data-stu-id="a7340-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="a7340-126"><xref:System.Windows.Media.Effects.BlurBitmapEffect> Можно использовать, чтобы создать эффект, подобный тени, который можно поместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="a7340-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="a7340-127">Если к тексту применяется эффект размытия для точечных рисунков, текст равномерно размывается во всех направлениях.</span><span class="sxs-lookup"><span data-stu-id="a7340-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="a7340-128">В следующем примере показан эффект размытия, примененный к тексту.</span><span class="sxs-lookup"><span data-stu-id="a7340-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Тень текста с использованием BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="a7340-130">В следующем примере кода показано создание эффекта размытия.</span><span class="sxs-lookup"><span data-stu-id="a7340-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="a7340-131">Использование преобразования переноса</span><span class="sxs-lookup"><span data-stu-id="a7340-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="a7340-132"><xref:System.Windows.Media.TranslateTransform> Можно использовать, чтобы создать эффект, подобный тени, который можно поместить позади текстового объекта.</span><span class="sxs-lookup"><span data-stu-id="a7340-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="a7340-133">В следующем примере кода используется <xref:System.Windows.Media.TranslateTransform> для смещения текста.</span><span class="sxs-lookup"><span data-stu-id="a7340-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="a7340-134">В этом примере слегка смещенная копия текста под основным текстом создает эффект тени.</span><span class="sxs-lookup"><span data-stu-id="a7340-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Тень текста с использованием TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)    
  
 <span data-ttu-id="a7340-136">В следующем примере кода показано создание эффекта тени с помощью преобразования.</span><span class="sxs-lookup"><span data-stu-id="a7340-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
