---
title: Общие сведения об эффектах для точечных рисунков
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 4a5e73f21d4ce4988f56c139d13038dca902b5b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186991"
---
# <a name="bitmap-effects-overview"></a>Общие сведения об эффектах для точечных рисунков
Эффекты Bitmap позволяют дизайнерам и разработчикам применять визуальные эффекты к содержимому Windows Presentation Foundation (WPF). Например, эффекты bitmap позволяют <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> легко применить эффект или эффект размытия к изображению или кнопке.  
  
> [!IMPORTANT]
> В системе .NET 4 или <xref:System.Windows.Media.Effects.BitmapEffect> позже класс устарел. Если вы попытаетесь использовать <xref:System.Windows.Media.Effects.BitmapEffect> класс, вы получите устаревшее исключение. Неустаревшей альтернативой классу <xref:System.Windows.Media.Effects.BitmapEffect> является <xref:System.Windows.Media.Effects.Effect> класс. В большинстве <xref:System.Windows.Media.Effects.Effect> случаев класс значительно быстрее.  

<a name="wpf_effects"></a>
## <a name="wpf-bitmap-effects"></a>Растровые эффекты WPF  
 Эффекты Bitmap (объект)<xref:System.Windows.Media.Effects.BitmapEffect> — это простые операции обработки пикселей. Эффект биткарты принимает <xref:System.Windows.Media.Imaging.BitmapSource> сятворный и <xref:System.Windows.Media.Imaging.BitmapSource> производит новый после применения эффекта, например, тень размытия или падения. Каждый эффект биткарты предоставляет свойства, которые могут <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> контролировать <xref:System.Windows.Media.Effects.BlurBitmapEffect>свойства фильтрации, такие как .  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]В особом случае, в, эффекты могут <xref:System.Windows.Media.Visual> быть установлены <xref:System.Windows.Controls.Button> в качестве свойств на живых объектах, таких как или <xref:System.Windows.Controls.TextBox>. Обработка пикселей применяется и отображается во время выполнения. В этом случае, во время рендеринга, <xref:System.Windows.Media.Visual> a <xref:System.Windows.Media.Imaging.BitmapSource> автоматически преобразуется в эквивалент <xref:System.Windows.Media.Effects.BitmapEffect>и подается в качестве ввода в . Вывод заменяет <xref:System.Windows.Media.Visual> поведение рендеринга по умолчанию объекта. Вот почему <xref:System.Windows.Media.Effects.BitmapEffect> объекты заставляют визуальные эффекты визуализировать в программном обеспечении только т.е. отсутствие аппаратного ускорения визуальных эффектов при применении эффектов.  
  
- <xref:System.Windows.Media.Effects.BlurBitmapEffect>имитирует объект, который отображается вне фокуса.  
  
- <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>создает ореол цвета по периметру объекта.  
  
- <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>создает тень за объектом.  
  
- <xref:System.Windows.Media.Effects.BevelBitmapEffect>создает скобы, которая поднимает поверхность изображения в соответствии с указанной кривой.  
  
- <xref:System.Windows.Media.Effects.EmbossBitmapEffect>создает отображение <xref:System.Windows.Media.Visual> удара, чтобы создать впечатление глубины и текстуры от искусственного источника света.  
  
> [!NOTE]
> Эффекты битовой карты WPF отображаются в программном режиме. Любой объект, который применяет эффект, будет также отрисован в программном режиме. Производительность наиболее снижается при использовании растровых эффектов на больших визуальных объектах или при анимации свойств растрового эффекта. Это не означает, что не следует вовсе использовать растровые эффекты, но следует соблюдать осторожность и выполнять тщательное тестирование, чтобы убедиться, что пользователи получат то, что вы ожидаете.  
  
> [!NOTE]
> Эффекты битной карты WPF не поддерживают частичное исполнение доверительного контора. Для использования растровых эффектов приложение должно иметь разрешения полного доверия.  
  
<a name="applyeffects"></a>
## <a name="how-to-apply-an-effect"></a>Применение эффекта  
 <xref:System.Windows.Media.Effects.BitmapEffect>является собственностью <xref:System.Windows.Media.Visual>на . Поэтому применение эффектов к Визуальным <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Image>эффектам, таким как , , <xref:System.Windows.Media.DrawingVisual>или <xref:System.Windows.UIElement>, так же просто, как установка свойства. <xref:System.Windows.UIElement.BitmapEffect%2A>может быть установлен <xref:System.Windows.Media.Effects.BitmapEffect> на один объект или несколько <xref:System.Windows.Media.Effects.BitmapEffectGroup> эффектов могут быть прикованы с помощью объекта.  
  
 Следующий пример демонстрирует, как <xref:System.Windows.Media.Effects.BitmapEffect> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]применять in .  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 Следующий пример показывает, как <xref:System.Windows.Media.Effects.BitmapEffect> применять код.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
> <xref:System.Windows.Media.Effects.BitmapEffect> При нанесении на контейнер макета, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Canvas>например или на визуальное дерево элемента или визуального, включая все его элементы.  
  
<a name="customeffects"></a>
## <a name="creating-custom-effects"></a>Создание пользовательских эффектов  
 WPF также предоставляет неуправляемые интерфейсы для создания пользовательских эффектов, которые могут быть использованы в управляемых приложениях WPF. Дополнительные справочные материалы для создания пользовательских растровых эффектов см. в разделе [Неуправляемые растровые эффекты WPF](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Effects.BitmapEffectGroup>
- <xref:System.Windows.Media.Effects.BitmapEffectInput>
- <xref:System.Windows.Media.Effects.BitmapEffectCollection>
- [Неуправляемые растровые эффекты WPF](https://docs.microsoft.com/previous-versions/windows/desktop/wibe/-wibe-lh)
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Безопасность](../security-wpf.md)
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
