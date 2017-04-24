---
title: "Общие сведения об эффектах для точечных рисунков | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "эффекты растровых изображений"
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Общие сведения об эффектах для точечных рисунков
Эффекты точечного рисунка позволяют конструкторам и разработчикам применять визуальные эффекты к отображаемому содержимому [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Например, растровые эффекты позволяют легко применить эффект <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> или эффект размытия к изображению или кнопке.  
  
> [!IMPORTANT]
>  В [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] и более поздних версиях класс <xref:System.Windows.Media.Effects.BitmapEffect> является устаревшим.  При попытке использовать класс <xref:System.Windows.Media.Effects.BitmapEffect> вызывается устаревшее исключение.  Неустаревшей альтернативой классу <xref:System.Windows.Media.Effects.BitmapEffect> является класс <xref:System.Windows.Media.Effects.Effect>.  В большинстве случаев класс <xref:System.Windows.Media.Effects.Effect> намного быстрее.  
  
   
  
<a name="wpf_effects"></a>   
## Эффекты точечного рисунка в WPF  
 Эффекты точечного рисунка \(объект <xref:System.Windows.Media.Effects.BitmapEffect>\) являются простыми операциями обработки пикселя.  Эффект точечного рисунка принимает <xref:System.Windows.Media.Imaging.BitmapSource> в качестве входных данных и создает новый <xref:System.Windows.Media.Imaging.BitmapSource> после применения эффекта, такого как размытой или отброшенной тени.  Каждый эффект точечного рисунка предоставляет свойства, которые могут управлять свойствами фильтрации, такими как <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> из <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 В качестве особого случая в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эффекты могут задаваться как свойства для объектов в режиме реального времени <xref:System.Windows.Media.Visual>, таких как <xref:System.Windows.Controls.Button> или <xref:System.Windows.Controls.TextBox>.  Обработка пикселя применяется и отображается во время выполнения.  В этом случае во время отрисовки, <xref:System.Windows.Media.Visual> автоматически преобразуется в свой эквивалент <xref:System.Windows.Media.Imaging.BitmapSource> и подается в качестве входных данных для <xref:System.Windows.Media.Effects.BitmapEffect>.  Выходные данные заменяют поведение при отрисовке по умолчанию <xref:System.Windows.Media.Visual> объекта.  Поэтому объекты <xref:System.Windows.Media.Effects.BitmapEffect> заставляют визуальные изображения отображаться только в программном обеспечении, т. е.  эффекты на визуальных изображениях применяются без аппаратного ускорения.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> имитирует просмотр объекта через расфокусированную лупу.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> создает цветное сияние вокруг объекта.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> создает тень позади объекта.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> создает скос, который приподнимает поверхность изображения в соответствии с указанной кривой.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> создает отображение элементов рельефа из <xref:System.Windows.Media.Visual> для создания впечатления текстуры и глубины от искусственного источника света.  
  
> [!NOTE]
>  Эффекты точечного рисунка [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] отображаются в режиме программного обеспечения.  Любой объект, который применяет эффект, будет отображен на программном уровне.  Производительность больше всего снижается при использовании эффектов точечного рисунка на большие свойства изображения или анимации эффекта Bitmap.  Нельзя сказать, что вам не следует использовать Bitmap\-эффекты таким образом во всех случаях, но следует соблюдать осторожность и тщательно проверять, чтобы убедиться, что ваши пользователи получат ожидаемую вами возможность.  
  
> [!NOTE]
>  Растровые эффекты [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] не поддерживают выполнение при частичном доверии.  Для использования растровых эффектов приложение должно иметь разрешения полного доверия.  
  
<a name="applyeffects"></a>   
## Практическое руководство. Применение эффекта  
 <xref:System.Windows.Media.Effects.BitmapEffect> является свойством <xref:System.Windows.Media.Visual>.  Поэтому применение эффектов к визуальным объектам <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual> и <xref:System.Windows.UIElement> так же просто, как присваивание значения свойству.  Эффект <xref:System.Windows.UIElement.BitmapEffect%2A> может применяться к одному объекту <xref:System.Windows.Media.Effects.BitmapEffect> или же несколько эффектов можно применить последовательно с помощью объекта <xref:System.Windows.Media.Effects.BitmapEffectGroup>.  
  
 В следующем примере демонстрируется применение <xref:System.Windows.Media.Effects.BitmapEffect> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 В следующем примере демонстрируется применение <xref:System.Windows.Media.Effects.BitmapEffect> в коде.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  При применении <xref:System.Windows.Media.Effects.BitmapEffect> к макету контейнера, такому как <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Canvas>, эффект применяется к визуальному дереву элемента или визуальному изображению, включающего все его дочерние элементы.  
  
<a name="customeffects"></a>   
## Создание пользовательских эффектов  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] также предоставляет неуправляемые интерфейсы для создания пользовательских эффектов, которые могут быть использованы в управляемых приложениях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Дополнительные справочные материалы для создания пользовательских растровых эффектов см. в документации [Неуправляемый растровый эффект в WPF](_wibe_lh).  
  
## См. также  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>   
 <xref:System.Windows.Media.Effects.BitmapEffectInput>   
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>   
 [Unmanaged WPF Bitmap Effect](_wibe_lh)   
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)