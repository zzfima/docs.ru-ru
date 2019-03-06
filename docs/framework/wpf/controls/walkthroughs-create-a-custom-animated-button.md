---
title: 'Пошаговые руководства: Создание пользовательской анимированной кнопки'
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 3c601641a0eb1024722b4f449f0ab23e54fe93dd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357213"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="d1dca-102">Пошаговые руководства: Создание пользовательской анимированной кнопки</span><span class="sxs-lookup"><span data-stu-id="d1dca-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="d1dca-103">Как предполагает имя, очень удобно для получения насыщенных презентаций опыта создания для клиентов Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d1dca-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="d1dca-104">В этих пошаговых руководствах показано, как настроить внешний вид и поведение кнопки (включая анимацию).</span><span class="sxs-lookup"><span data-stu-id="d1dca-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="d1dca-105">Эта настройка выполняется с помощью стиля и шаблона, так что можно применить эта пользовательская кнопка легко к любой кнопке в приложении.</span><span class="sxs-lookup"><span data-stu-id="d1dca-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="d1dca-106">На следующем рисунке настраиваемая кнопка вы создадите.</span><span class="sxs-lookup"><span data-stu-id="d1dca-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="d1dca-107">![Настраиваемая кнопка, которая будет создан](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="d1dca-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="d1dca-108">Векторная графика, составляющих внешний вид кнопки создаются с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1dca-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="d1dca-109">— похож на HTML, но является более эффективные и расширяемые.</span><span class="sxs-lookup"><span data-stu-id="d1dca-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="d1dca-110">можно вводить вручную с помощью Microsoft Visual Studio или Блокнот, или можно использовать это средство визуального проектирования, таких как Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="d1dca-110">can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="d1dca-111">Expression Blend работает путем создания основного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] кода, поэтому оба метода создают одинаковую графику.</span><span class="sxs-lookup"><span data-stu-id="d1dca-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1dca-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d1dca-112">In This Section</span></span>  
 [<span data-ttu-id="d1dca-113">Создание кнопки с помощью Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="d1dca-113">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="d1dca-114">В этой статье демонстрируется создание кнопки с помощью пользовательского поведения с помощью средства конструктора Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="d1dca-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="d1dca-115">Создание кнопки с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="d1dca-115">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="d1dca-116">Демонстрирует создание кнопки с помощью пользовательского поведения с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1dca-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d1dca-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d1dca-117">Related Sections</span></span>  
 [<span data-ttu-id="d1dca-118">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d1dca-118">Styling and Templating</span></span>](styling-and-templating.md)  
 <span data-ttu-id="d1dca-119">Описывает, как стили и шаблоны могут использоваться для определения внешнего вида и поведения элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d1dca-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="d1dca-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d1dca-120">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="d1dca-121">Описывает, как объекты могут быть анимированы с помощью [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] анимации и системы.</span><span class="sxs-lookup"><span data-stu-id="d1dca-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="d1dca-122">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="d1dca-122">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="d1dca-123">В этой статье описывается использование объектов кисть для закрашивания сплошным цветом, линейным градиентом и радиальным градиентом.</span><span class="sxs-lookup"><span data-stu-id="d1dca-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="d1dca-124">Общие сведения об эффектах для точечных рисунков</span><span class="sxs-lookup"><span data-stu-id="d1dca-124">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="d1dca-125">Описывает эффекты точечного рисунка, поддерживаемые [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и способы их применения.</span><span class="sxs-lookup"><span data-stu-id="d1dca-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
