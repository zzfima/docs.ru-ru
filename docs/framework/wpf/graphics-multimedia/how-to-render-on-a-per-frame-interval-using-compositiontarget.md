---
title: "Практическое руководство. Визуализация каждого кадра с помощью CompositionTarget | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CompositionTarget - объекты, покадровая отрисовка"
  - "покадровая отрисовка с помощью объектов CompositionTarget"
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Визуализация каждого кадра с помощью CompositionTarget
Подсистема анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество возможностей для создания покадровой анимации.  Однако существуют сценарии применения, в которых необходим детальный контроль над покадровой отрисовкой.  Объект <xref:System.Windows.Media.CompositionTarget> предоставляет возможность создания пользовательской анимации на основе покадрового обратного вызова.  
  
 <xref:System.Windows.Media.CompositionTarget> является статическим классом, представляющим поверхность отображения, на которой отрисовывается приложение.  Событие <xref:System.Windows.Media.CompositionTarget.Rendering> возникает каждый раз при рисовании сцены приложения.  Частота кадров отрисовки задает количество отрисовок сцены в секунду.  
  
> [!NOTE]
>  Полный пример кода с использованием <xref:System.Windows.Media.CompositionTarget> см. в разделе [Пример использования CompositionTarget](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## Пример  
 Событие <xref:System.Windows.Media.CompositionTarget.Rendering> активируется во время процесса отрисовки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В следующем примере показана регистрация делегата <xref:System.EventHandler> в статическом методе <xref:System.Windows.Media.CompositionTarget.Rendering> для <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 Можно использовать собственный метод обработчика событий отрисовки для создания пользовательского графического содержимого.  Этот метод обработчика событий вызывается один раз за кадр.  Каждый раз, когда [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] маршалирует сохраненные данные отрисовки в [визуальном дереве](GTMT) через граф сцены, вызывается метод обработчика событий.  Кроме того, метод обработчика событий вызывается в случае, если изменения [визуального дерева](GTMT) принудительно обновляют граф сцены.  Обратите внимание, что метод обработчика событий вызывается после вычисления макета.  Однако можно изменить макет в методе обработчика событий, что означает повторное вычисление макета перед отрисовкой.  
  
 В следующем примере показано, как можно предоставить пользовательское рисование в методе обработчика событий <xref:System.Windows.Media.CompositionTarget>.  В этом случае цвет фона <xref:System.Windows.Controls.Canvas> рисуется значением цвета на основе координат указателя мыши.  Перемещение указателя мыши внутри <xref:System.Windows.Controls.Canvas> изменяет цвет его фона.  Кроме того, вычисляется средняя частота кадров на основе текущего значения прошедшего времени и общего числа визуализированных кадров.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Можно обнаружить, что пользовательское рисование выполняется с разными скоростями на разных компьютерах.  Это обусловлено тем, что пользовательское рисование зависит от частоты кадров.  В зависимости от используемой системы и рабочей нагрузки на эту систему число вызовов события <xref:System.Windows.Media.CompositionTarget.Rendering> в секунду может варьировать.  Сведения об определении аппаратных возможностей и производительности графического устройства, на котором выполняется приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе [Уровни графической отрисовки](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Добавление или удаление делегата отрисовки <xref:System.EventHandler> во время срабатывания события будет отложено до завершения срабатывания события.  Это согласуется с порядком обработки событий на основе <xref:System.MulticastDelegate> в общеязыковой среде выполнения \(CLR\).  Также обратите внимание на то, что какой\-либо определенный порядок вызова событий отрисовки не гарантируется.  Если имеется несколько делегатов <xref:System.EventHandler>, зависимых от определенного порядка, следует вручную зарегистрировать одно событие <xref:System.Windows.Media.CompositionTarget.Rendering> и мультиплексировать делегаты в правильном порядке.  
  
## См. также  
 <xref:System.Windows.Media.CompositionTarget>   
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)