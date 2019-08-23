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
ms.openlocfilehash: 8864204ccdd1e860cc910dfe8baa2f25edfb2fcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956982"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Практическое руководство. Визуализация каждого кадра с помощью CompositionTarget
Подсистема анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество возможностей для создания анимации на основе кадров. Однако существуют сценарии приложений, в которых необходим детальный контроль отрисовки каждого кадра. <xref:System.Windows.Media.CompositionTarget> Объект предоставляет возможность создавать пользовательские анимации на основе покадрового обратного вызова.  
  
 <xref:System.Windows.Media.CompositionTarget>— Это статический класс, представляющий поверхность отображения, на которой рисуется приложение. <xref:System.Windows.Media.CompositionTarget.Rendering> Событие возникает каждый раз при прорисовке сцены приложения. Частота кадров отрисовки — это количество отрисовок сцены за секунду.  
  
> [!NOTE]
> Полный пример кода с помощью <xref:System.Windows.Media.CompositionTarget>см. в разделе [Использование примера CompositionTarget](https://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Пример  
 Событие срабатывает во время процесса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]отрисовки <xref:System.Windows.Media.CompositionTarget.Rendering> . В следующем примере показано, как зарегистрировать <xref:System.EventHandler> делегат для статического <xref:System.Windows.Media.CompositionTarget.Rendering> метода в <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Можно использовать собственный метод обработчика событий отрисовки для создания пользовательского графического содержимого. Метод обработчика событий вызывается один раз для каждого кадра. Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выполняет маршалинг сохраненных данных отрисовки в визуальном дереве через граф сцены композиции, вызывается метод обработчика событий. Кроме того, если изменения в визуальном дереве принудительно обновляют граф сцены композиции, метод обработчика событий также вызывается. Обратите внимание, что метод обработчика событий вызывается после вычисления макета. Однако можно изменить макет в методе обработчика событий, что означает повторное вычисление макета перед отрисовкой.  
  
 В следующем примере показано, как можно предоставить пользовательское рисование в <xref:System.Windows.Media.CompositionTarget> методе обработчика событий. В этом случае цвет <xref:System.Windows.Controls.Canvas> фона изображения рисуется с помощью значения цвета, основанного на координатной положении мыши. Если навести указатель мыши внутри <xref:System.Windows.Controls.Canvas>, изменяется цвет фона. Кроме того вычисляется средняя частота кадров, на основе текущего значения прошедшего времени и общего числа отрисованных кадров.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Может оказаться, что пользовательское рисование выполняется на разных компьютерах с разной скоростью. Это потому, что пользовательское рисование не является независимым от частоты кадров. В зависимости от используемой системы и рабочей нагрузки этой системы <xref:System.Windows.Media.CompositionTarget.Rendering> событие может называться разное число раз в секунду. Дополнительные сведения об определении возможностей графического оборудования и производительности для устройства, которое запускает приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Уровни отрисовки графики](../advanced/graphics-rendering-tiers.md).  
  
 Добавление или удаление делегата <xref:System.EventHandler> отрисовки во время срабатывания события будет отложено до тех пор, пока не завершится срабатывание события. Это согласуется с тем, <xref:System.MulticastDelegate>как события на основе обрабатываются в среде CLR. Также обратите внимание, что порядок вызова событий отрисовки не гарантируется. При наличии нескольких <xref:System.EventHandler> делегатов, зависящих от определенного порядка, следует зарегистрировать одно <xref:System.Windows.Media.CompositionTarget.Rendering> событие и мультиплексировать делегаты в правильном порядке.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.CompositionTarget>
- [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md)
