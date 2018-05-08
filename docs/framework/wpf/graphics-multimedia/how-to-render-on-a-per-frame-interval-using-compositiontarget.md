---
title: Практическое руководство. Визуализация каждого кадра с помощью CompositionTarget
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: 7c080c6deca63eacdf0e1123f4ca8bbb495ed9ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Практическое руководство. Визуализация каждого кадра с помощью CompositionTarget
Подсистема анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество возможностей для создания анимации на основе кадров. Однако существуют сценарии приложений, в которых необходим детальный контроль отрисовки каждого кадра. <xref:System.Windows.Media.CompositionTarget> Объект предоставляет возможность создания пользовательской анимации на основе покадрового обратного вызова.  
  
 <xref:System.Windows.Media.CompositionTarget> является статическим классом, который представляет поверхность отображения, на котором рисуется приложения. <xref:System.Windows.Media.CompositionTarget.Rendering> Событие возникает каждый раз при рисовании сцены приложения. Частота кадров отрисовки — это количество отрисовок сцены за секунду.  
  
> [!NOTE]
>  Для примера полный исходный код с помощью <xref:System.Windows.Media.CompositionTarget>, в разделе [использование образца элементу CompositionTarget](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.CompositionTarget.Rendering> Событие запускается во время [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] процессе подготовки к просмотру. В следующем примере показано, как вы регистрируете <xref:System.EventHandler> делегатом статического <xref:System.Windows.Media.CompositionTarget.Rendering> метод <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Можно использовать собственный метод обработчика событий отрисовки для создания пользовательского графического содержимого. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через граф сцены композиции, вызывается метод обработчика событий. Кроме того, если изменения в визуальном дереве принудительно обновляют граф сцены композиции, метод обработчика событий также вызывается. Обратите внимание, что метод обработчика событий вызывается после вычисления макета. Однако можно изменить макет в методе обработчика событий, что означает повторное вычисление макета перед отрисовкой.  
  
 В следующем примере показано как можно предоставить пользовательское рисование <xref:System.Windows.Media.CompositionTarget> метод обработчика событий. В данном случае цвет фона <xref:System.Windows.Controls.Canvas> нарисован с помощью значения цветов на основе координат положения указателя мыши. При перемещении указателя мыши внутри <xref:System.Windows.Controls.Canvas>, ее изменения цвета фона. Кроме того вычисляется средняя частота кадров, на основе текущего значения прошедшего времени и общего числа отрисованных кадров.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Может оказаться, что пользовательское рисование выполняется на разных компьютерах с разной скоростью. Это потому, что пользовательское рисование не является независимым от частоты кадров. В зависимости от используемой системы и рабочей нагрузки этой системы <xref:System.Windows.Media.CompositionTarget.Rendering> событий может быть вызван Разное количество раз в секунду. Дополнительные сведения об определении возможностей графического оборудования и производительности для устройства, которое запускает приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Уровни отрисовки графики](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Добавление или удаление визуализации <xref:System.EventHandler> делегата во время срабатывания события будет отложено до момента завершения события обработки. Это согласуется с тем, как <xref:System.MulticastDelegate>-событий на основе обрабатываются в Common Language Runtime (CLR). Также обратите внимание, что порядок вызова событий отрисовки не гарантируется. Если имеется несколько <xref:System.EventHandler> делегатов, которые зависят от определенного порядка, следует зарегистрировать один <xref:System.Windows.Media.CompositionTarget.Rendering> событий и мультиплексировать делегаты в правильном порядке.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.CompositionTarget>  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
