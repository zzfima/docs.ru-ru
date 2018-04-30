---
title: Общие сведения об эффектах для точечных рисунков
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 841c854b7bbe2042d3a7aebd74dfe9421e71be2b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="bitmap-effects-overview"></a>Общие сведения об эффектах для точечных рисунков
Эффекты точечного рисунка позволяют конструкторам и разработчикам применять визуальные эффекты к просмотру содержимого Windows Presentation Foundation (WPF). Например, растровых эффектов, которые позволяют применять легко <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> эффект или эффект размытия изображения или кнопки.  
  
> [!IMPORTANT]
>  В [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] или более поздней версии, <xref:System.Windows.Media.Effects.BitmapEffect> класс устарел. При попытке использовать <xref:System.Windows.Media.Effects.BitmapEffect> класса, будет вызвано исключение устарел. Поддерживаемый аналог для <xref:System.Windows.Media.Effects.BitmapEffect> класс <xref:System.Windows.Media.Effects.Effect> класса. В большинстве случаев <xref:System.Windows.Media.Effects.Effect> класс значительно быстрее.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Растровые эффекты WPF  
 Эффекты для точечных рисунков (<xref:System.Windows.Media.Effects.BitmapEffect> объекта) — это простой пикселей операции обработки. Эффект растрового изображения принимает <xref:System.Windows.Media.Imaging.BitmapSource> как входных данных и выдает новый <xref:System.Windows.Media.Imaging.BitmapSource> после применения эффекта, например тень размытия или drop. Каждый эффект точечного рисунка предоставляет свойства, которые могут управлять свойствами фильтрации, такими как <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> из <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Как особый случай в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], эффекты можно задать в качестве свойства на динамической <xref:System.Windows.Media.Visual> объекты, такие как <xref:System.Windows.Controls.Button> или <xref:System.Windows.Controls.TextBox>. Обработка пикселей применяется и отображается во время выполнения. В этом случае во время подготовки к просмотру <xref:System.Windows.Media.Visual> автоматически преобразуется в его <xref:System.Windows.Media.Imaging.BitmapSource> эквивалентные и отправляются в качестве входных данных для <xref:System.Windows.Media.Effects.BitmapEffect>. Выходные данные заменяют <xref:System.Windows.Media.Visual> поведение отрисовки по умолчанию для объекта. Именно поэтому <xref:System.Windows.Media.Effects.BitmapEffect> объектов принудительно визуальные элементы для отображения в программном обеспечении только т. е. без аппаратного ускорения на визуальные элементы, после применения эффектов.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> имитирует объекта, который отображается в фокусе out.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> Создает цветное свечение вокруг объекта.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> создает тень позади объекта.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> создает скос, который приподнимает поверхность изображения в соответствии с указанной кривой.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> Создает рельефа <xref:System.Windows.Media.Visual> впечатление глубины и текстуры с искусственным источником света.  
  
> [!NOTE]
>  Растровые эффекты [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] отрисовываются в программном режиме. Любой объект, который применяет эффект, будет также отрисован в программном режиме. Производительность наиболее снижается при использовании растровых эффектов на больших визуальных объектах или при анимации свойств растрового эффекта. Это не означает, что не следует вовсе использовать растровые эффекты, но следует соблюдать осторожность и выполнять тщательное тестирование, чтобы убедиться, что пользователи получат то, что вы ожидаете.  
  
> [!NOTE]
>  Растровые эффекты [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] не поддерживают выполнение при частичном доверии. Для использования растровых эффектов приложение должно иметь разрешения полного доверия.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Применение эффекта  
 <xref:System.Windows.Media.Effects.BitmapEffect> является свойством <xref:System.Windows.Media.Visual>. Поэтому применение эффектов визуальных элементов, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, или <xref:System.Windows.UIElement>, так же просто, как задать свойство. <xref:System.Windows.UIElement.BitmapEffect%2A> можно задать единое <xref:System.Windows.Media.Effects.BitmapEffect> объектов или нескольких эффектов могут быть соединены с помощью <xref:System.Windows.Media.Effects.BitmapEffectGroup> объекта.  
  
 Следующий пример демонстрирует способ применения <xref:System.Windows.Media.Effects.BitmapEffect> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Следующий пример демонстрирует способ применения <xref:System.Windows.Media.Effects.BitmapEffect> в коде.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  Когда <xref:System.Windows.Media.Effects.BitmapEffect> применяется в контейнере макета, такие как <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Canvas>, действие применяется к визуальному дереву элемента или visual c#, включая все его дочерние элементы.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Создание пользовательских эффектов  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] также предоставляет неуправляемые интерфейсы для создания пользовательских эффектов, которые можно использовать в управляемых приложениях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Дополнительные справочные материалы для создания пользовательских растровых эффектов см. в разделе [Неуправляемые растровые эффекты WPF](https://msdn.microsoft.com/library/ms735092.aspx).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [Эффект растрового изображения неуправляемый WPF](https://msdn.microsoft.com/library/ms735092.aspx)  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
