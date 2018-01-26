---
title: "Сбор рукописных данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbf55b5d84420a6aa7af06e94497a85a2b54a0c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-ink"></a>Сбор рукописных данных
Платформа [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) выполняет сбор цифровых рукописных фрагментов, что является одной из основных ее функций. В этом разделе обсуждаются методы сбора рукописных данных в [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы использовать следующие примеры, необходимо сначала установить [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Кроме того, необходимо иметь представление о создании приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения о начале работы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="using-the-inkcanvas-element"></a>Использование элемента InkCanvas  
 <xref:System.Windows.Controls.InkCanvas> Элемент предоставляет простой способ сбора рукописного ввода в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Controls.InkCanvas> Элемент аналогичен [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) объекта из [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] и более ранних версий.  
  
 Используйте <xref:System.Windows.Controls.InkCanvas> элемент для получения и отображения рукописного ввода. Рукописный ввод, как правило, осуществляется с помощью пера, которое взаимодействует с дигитайзером для создания рукописных штрихов. Кроме того, вместо пера можно использовать мышь. Созданные штрихи представляются в виде <xref:System.Windows.Ink.Stroke> объекты и их можно управлять программно или пользователем ввода данных. <xref:System.Windows.Controls.InkCanvas> Позволяет пользователям выбор, изменение или удаление существующего <xref:System.Windows.Ink.Stroke>.  
  
 С помощью XAML можно настроить сбор рукописных фрагментов, просто добавив элемент `InkCanvas` в дерево. В следующем примере добавляется <xref:System.Windows.Controls.InkCanvas> по умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] проект, созданный в [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 Элемент `InkCanvas` также может содержать дочерние элементы, что позволяет добавлять функции рукописных заметок практически в любые элементы XAML. Например, чтобы добавить возможности рукописного ввода в текстовый элемент, просто сделайте его дочернего элемента <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Добавление поддержки пометки изображений с помощью рукописного ввода выполняется так же просто.  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>Режимы InkCollection  
 <xref:System.Windows.Controls.InkCanvas> Обеспечивает поддержку различных режимов ввода с помощью его <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> свойство.  
  
### <a name="manipulating-ink"></a>Управление рукописным вводом  
 <xref:System.Windows.Controls.InkCanvas> Обеспечивает поддержку многих рукописного ввода операции редактирования. Например <xref:System.Windows.Controls.InkCanvas> поддерживает назад перо ластика без дополнительного кода, чтобы добавить функциональность в элемент.  
  
#### <a name="selection"></a>Выбранное  
 Установка режима выбора сводится параметр <xref:System.Windows.Controls.InkCanvasEditingMode> свойства **выберите**. В следующем примере задается на основе значения из режима редактирования <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 Используйте <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> свойство, чтобы изменить внешний вид штрихов рукописного ввода. Например <xref:System.Windows.Ink.DrawingAttributes.Color%2A> членом <xref:System.Windows.Ink.DrawingAttributes> задает цвет отображаемого объекта <xref:System.Windows.Ink.Stroke>. В следующем примере цвет выбранных штрихов изменяется на красный.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Свойство предоставляет доступ к свойствам, например высоту, ширину и цвет штрихов, создаваемой в <xref:System.Windows.Controls.InkCanvas>. После преобразования <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, все следующие штрихи, введенные в <xref:System.Windows.Controls.InkCanvas> подготавливаются к просмотру с новыми значениями свойства.  
  
 В дополнение к изменению <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> в файле кода, можно использовать синтаксис XAML для указания <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства. Следующий код XAML демонстрирует, как задать <xref:System.Windows.Ink.DrawingAttributes.Color%2A> свойства. Чтобы воспользоваться этим кодом, создайте новый проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с именем HelloInkCanvas в Visual Studio 2005. Замените код в файле Window1.xaml следующим кодом.  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 Затем добавьте следующие обработчики событий кнопки в файл кода программной части внутри класса Window1.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 После копирования этого кода нажмите клавишу **F5** в Microsoft Visual Studio 2005 для запуска программы в отладчике.  
  
 Обратите внимание как <xref:System.Windows.Controls.StackPanel> размещение кнопок на основе <xref:System.Windows.Controls.InkCanvas>. При попытке рукописного ввода данных поверх кнопок, <xref:System.Windows.Controls.InkCanvas> собирает и отображает рукописные данные позади кнопок. Это так, как кнопки имеют общий родительский <xref:System.Windows.Controls.InkCanvas> отличие от дочерних элементов. Кроме того, кнопки находятся выше в z-порядке, поэтому рукописные фрагменты отображаются позади них.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
