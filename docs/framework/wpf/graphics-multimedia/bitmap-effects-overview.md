---
title: Обзор эффектов точечных рисунков
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5c304363efe7d0e9bd9e14ff916f8d852ab3a8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636020"
---
# <a name="bitmap-effects-overview"></a>Обзор эффектов точечных рисунков
Растровые эффекты позволяют дизайнерам и разработчикам применять визуальные эффекты к содержимому, отображаемому в Windows Presentation Foundation (WPF). Например, растровые эффекты позволяют легко применить эффект <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> или эффект размытия к изображению или кнопке.  
  
> [!IMPORTANT]
> В .NET Framework 4 или более поздней версии класс <xref:System.Windows.Media.Effects.BitmapEffect> устарел. Если вы попытаетесь использовать класс <xref:System.Windows.Media.Effects.BitmapEffect>, будет выдано соответствующее исключение. Современной альтернативой для класса <xref:System.Windows.Media.Effects.BitmapEffect> является класс <xref:System.Windows.Media.Effects.Effect>. В большинстве случаев класс <xref:System.Windows.Media.Effects.Effect> работает значительно быстрее.  

<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>Растровые эффекты WPF  
 Эффекты для точечных рисунков (объект <xref:System.Windows.Media.Effects.BitmapEffect>) — это простые операции обработки пикселей. Такой эффект принимает в качестве входных данных <xref:System.Windows.Media.Imaging.BitmapSource> и выдает новый объект <xref:System.Windows.Media.Imaging.BitmapSource> после применения эффекта, например размытия или тени. Каждый эффект предоставляет свойства, которые могут управлять свойствами фильтра, например <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> у <xref:System.Windows.Media.Effects.BlurBitmapEffect>.  
  
 Как особый случай, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] эффекты могут задаваться как свойства объектов <xref:System.Windows.Media.Visual>, отображаемых в реальном времени, например <xref:System.Windows.Controls.Button> или <xref:System.Windows.Controls.TextBox>. Обработка пикселей применяется и отображается во время выполнения. В этом случае во время отрисовки <xref:System.Windows.Media.Visual> автоматически преобразуется в эквивалентный объект <xref:System.Windows.Media.Imaging.BitmapSource> и передается в качестве входных данных в <xref:System.Windows.Media.Effects.BitmapEffect>. Выходные данные заменяют поведение отрисовки по умолчанию для объекта <xref:System.Windows.Media.Visual>. По этой причине объекты <xref:System.Windows.Media.Effects.BitmapEffect> заставляют визуальные элементы использовать только программный режим отрисовки, т. е. без аппаратного ускорения, при применении к ним эффектов.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect> имитирует объект, который отображается не в фокусе.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> создает цветное свечение по периметру объекта.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> создает тень позади объекта.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect> создает рельеф, поднимающий поверхность изображения в соответствии с указанной кривой.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect> создает отображение элементов рельефа <xref:System.Windows.Media.Visual>, дающее впечатление глубины и текстуры освещения от искусственного источника света.  
  
> [!NOTE]
> Растровые эффекты WPF подготавливаются к просмотру в программном режиме. Любой объект, который применяет эффект, будет также отрисован в программном режиме. Производительность наиболее снижается при использовании растровых эффектов на больших визуальных объектах или при анимации свойств растрового эффекта. Это не означает, что не следует вовсе использовать растровые эффекты, но следует соблюдать осторожность и выполнять тщательное тестирование, чтобы убедиться, что пользователи получат то, что вы ожидаете.  
  
> [!NOTE]
> Растровые эффекты WPF не поддерживают выполнение с частичным доверием. Для использования растровых эффектов приложение должно иметь разрешения полного доверия.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>Применение эффекта  
 <xref:System.Windows.Media.Effects.BitmapEffect> является свойством <xref:System.Windows.Media.Visual>. Поэтому применение эффектов к визуальным элементам, например <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual> или <xref:System.Windows.UIElement>, так же просто, как задание свойства. <xref:System.Windows.UIElement.BitmapEffect%2A> можно присвоить единственный объект <xref:System.Windows.Media.Effects.BitmapEffect>, или можно объединить несколько эффектов в цепочку с помощью объекта <xref:System.Windows.Media.Effects.BitmapEffectGroup>.  
  
 В следующем примере показано, как применить <xref:System.Windows.Media.Effects.BitmapEffect> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 В следующем примере показано, как применить <xref:System.Windows.Media.Effects.BitmapEffect> в коде.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> Когда <xref:System.Windows.Media.Effects.BitmapEffect> применяется к контейнеру макета, например <xref:System.Windows.Controls.DockPanel> или <xref:System.Windows.Controls.Canvas>, эффект применяется к визуальному дереву элемента или визуального элемента, включая все его дочерние элементы.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>Создание пользовательских эффектов  
 WPF также предоставляет неуправляемые интерфейсы для создания пользовательских эффектов, которые могут использоваться в управляемых приложениях WPF. Дополнительные справочные материалы для создания пользовательских растровых эффектов см. в разделе [Неуправляемые растровые эффекты WPF](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Неуправляемый растровый результат WPF](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Security](../security-wpf.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
