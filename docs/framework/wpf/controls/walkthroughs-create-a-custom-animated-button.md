---
title: "Пошаговые руководства: создание пользовательской анимированной кнопки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ece907b23772504990ef334f446d7b6072f5d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="4e381-102">Пошаговые руководства: создание пользовательской анимированной кнопки</span><span class="sxs-lookup"><span data-stu-id="4e381-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="4e381-103">Как и предполагает его имя, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] отлично подходит для создания презентаций взаимодействия для клиентов.</span><span class="sxs-lookup"><span data-stu-id="4e381-103">As its name suggests, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="4e381-104">В этих пошаговых руководствах показано, как настроить внешний вид и поведение кнопки (включая анимацию).</span><span class="sxs-lookup"><span data-stu-id="4e381-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="4e381-105">Эта настройка выполняется с помощью стилей и шаблонов, что можно применить эта пользовательская кнопка легко на все кнопки в приложении.</span><span class="sxs-lookup"><span data-stu-id="4e381-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="4e381-106">На следующем рисунке настраиваемая кнопка будет создан.</span><span class="sxs-lookup"><span data-stu-id="4e381-106">The following illustration shows the customized button that you will create.</span></span>  
  
 <span data-ttu-id="4e381-107">![Настраиваемая кнопка, которая будет создан](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="4e381-107">![The customized button that you will create](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>  
  
 <span data-ttu-id="4e381-108">Векторная графика, составляющие внешний вид кнопки создаются с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e381-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="4e381-109">аналогичен HTML но является более мощным и расширяемым.</span><span class="sxs-lookup"><span data-stu-id="4e381-109"> is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]<span data-ttu-id="4e381-110">можно вводить вручную с помощью Microsoft Visual Studio или Блокнот, или можно использовать средства визуального проектирования, такого как Microsoft Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="4e381-110"> can be typed in manually using Microsoft Visual Studio or Notepad, or you can use a visual design tool such as Microsoft Expression Blend.</span></span> <span data-ttu-id="4e381-111">Expression Blend работает путем создания основного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] кода, поэтому оба метода создают одинаковую графику.</span><span class="sxs-lookup"><span data-stu-id="4e381-111">Expression Blend works by creating underlying [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code, so both methods create the same graphics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e381-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4e381-112">In This Section</span></span>  
 [<span data-ttu-id="4e381-113">Создание кнопки с помощью Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="4e381-113">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 <span data-ttu-id="4e381-114">Демонстрирует создание кнопки с помощью пользовательского поведения с помощью средства конструктора Expression Blend.</span><span class="sxs-lookup"><span data-stu-id="4e381-114">Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>  
  
 [<span data-ttu-id="4e381-115">Создание кнопки с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="4e381-115">Create a Button by Using XAML</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 <span data-ttu-id="4e381-116">Демонстрирует создание кнопки с помощью пользовательского поведения с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e381-116">Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4e381-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4e381-117">Related Sections</span></span>  
 [<span data-ttu-id="4e381-118">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="4e381-118">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 <span data-ttu-id="4e381-119">Описывает, как стили и шаблоны могут использоваться для определения внешнего вида и поведения элементов управления.</span><span class="sxs-lookup"><span data-stu-id="4e381-119">Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>  
  
 [<span data-ttu-id="4e381-120">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="4e381-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 <span data-ttu-id="4e381-121">Описывает, как объекты могут быть анимированы с помощью [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] анимации и системы управления временем.</span><span class="sxs-lookup"><span data-stu-id="4e381-121">Describes how objects can be animated by using the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] animation and timing system.</span></span>  
  
 [<span data-ttu-id="4e381-122">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="4e381-122">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 <span data-ttu-id="4e381-123">Описание способов использования объектов кисти для рисования сплошным цветом, линейным градиентом и радиального градиента.</span><span class="sxs-lookup"><span data-stu-id="4e381-123">Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>  
  
 [<span data-ttu-id="4e381-124">Общие сведения об эффектах для точечных рисунков</span><span class="sxs-lookup"><span data-stu-id="4e381-124">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)  
 <span data-ttu-id="4e381-125">Описывает эффекты точечного рисунка, поддерживаемые [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и о способах их применения.</span><span class="sxs-lookup"><span data-stu-id="4e381-125">Describes the bitmap effects supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and explains how to apply them.</span></span>
