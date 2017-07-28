---
title: "Сбор рукописных данных | Microsoft Docs"
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
  - "прием цифрового рукописного ввода"
  - "DefaultDrawingAttributes - свойство"
  - "цифровой рукописный ввод, прием"
  - "DrawingAttributes - свойство"
  - "рукописный ввод, прием"
  - "InkCanvas - элемент"
  - "свойства, DefaultDrawingAttributes"
  - "свойства, DrawingAttributes"
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Сбор рукописных данных
Платформа [Windows Presentation Foundation \(WPF\)](../../../../docs/framework/wpf/index.md) выполняет сбор цифровых рукописных данных в качестве основной части своих функциональных возможностей.  В этом разделе обсуждаются методы сбора рукописных данных в приложении [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
## Предварительные требования  
 Чтобы использовать следующие примеры, необходимо сначала установить [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].  Также следует понимать порядок написания приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения о начале работы с приложением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Использование элемента InkCanvas  
 Элемент <xref:System.Windows.Controls.InkCanvas> предоставляет простой способ сбора рукописных данных в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Элемент <xref:System.Windows.Controls.InkCanvas> похож на объект <xref:Microsoft.Ink.InkOverlay> из [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] и более ранних версий.  
  
 Используйте элемент <xref:System.Windows.Controls.InkCanvas> для получения и отображения ввода рукописных данных.  Обычно ввод рукописных данных осуществляется с использованием пера, которое взаимодействует с дигитайзером для создания рукописных штрихов.  Кроме того, в качестве пера можно использовать мышь.  Созданные штрихи представлены как объекты <xref:System.Windows.Ink.Stroke>, и ими можно управлять программно или путем ввода данных пользователем.  Объект <xref:System.Windows.Controls.InkCanvas> позволяет пользователям выбирать, изменять или удалять существующие объекты <xref:System.Windows.Ink.Stroke>.  
  
 Используя язык XAML, можно настроить коллекцию рукописных данных так же легко, как добавить элемент `InkCanvas` к дереву.  В следующем примере добавляется объект <xref:System.Windows.Controls.InkCanvas> в проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию, созданный в среде [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 Элемент `InkCanvas` также может содержать дочерние элементы, что позволяет добавлять рукописные примечания практически к любому типу элемента XAML.  Например, чтобы добавить возможности рукописного ввода в текстовый элемент, просто сделайте его дочерним объекта <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 Добавить поддержку определения изображения с рукописными данными довольно просто.  
  
 [!code-xml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### Режимы InkCollection  
 Объект <xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку различных режимов ввода с помощью свойства <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.  
  
### Управление рукописными данными  
 Объект <xref:System.Windows.Controls.InkCanvas> обеспечивает поддержку многих операций редактирования рукописных данных.  Например, <xref:System.Windows.Controls.InkCanvas> поддерживает ластик на другом конце пера без дополнительного кода, необходимого для добавления этой функциональной возможности к элементу.  
  
#### Выбранное  
 Установка режима выбора сводится к простой установке для свойства <xref:System.Windows.Controls.InkCanvasEditingMode> значения **Select**.  Следующий код устанавливает режим редактирования на основе значения объекта <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### DrawingAttributes  
 Используйте свойство <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> для изменения внешнего вида рукописных штрихов.  Например, член <xref:System.Windows.Ink.DrawingAttributes.Color%2A> объекта <xref:System.Windows.Ink.DrawingAttributes> задает цвет отображаемого объекта <xref:System.Windows.Ink.Stroke>.  В следующем примере цвет выбранных штрихов меняется на красный.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### DefaultDrawingAttributes  
 Свойство <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> предоставляет доступ к таким свойствам, как высота, ширина и цвет штрихов, создаваемых в объекте <xref:System.Windows.Controls.InkCanvas>.  После первого изменения свойства <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> все следующие штрихи, введенные в объект <xref:System.Windows.Controls.InkCanvas>, будут формироваться с новыми значениями этого свойства.  
  
 Дополнительно к изменению <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> в файле кода программной части можно использовать синтаксис XAML для указания свойств <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>.  Следующий код XAML демонстрирует установку свойства <xref:System.Windows.Ink.DrawingAttributes.Color%2A>.  Чтобы использовать этот код, создайте новый проект [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с именем HelloInkCanvas в Visual Studio 2005.  Замените код в файле Window1.xaml на следующий код.  
  
 [!code-xml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 Затем добавьте следующие обработчики событий кнопки к файлу фонового кода внутри класса Window1.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 После копирования этого кода нажмите клавишу **F5** в Microsoft Visual Studio 2005 для запуска программы в отладчике.  
  
 Обратите внимание, как элемент управления <xref:System.Windows.Controls.StackPanel> размещает кнопки в верхней части объекта <xref:System.Windows.Controls.InkCanvas>.  При попытке рукописного ввода данных поверх кнопок элемент управления <xref:System.Windows.Controls.InkCanvas> собирает и отображает рукописные данные позади кнопок.  Это происходит потому, что в отличие от дочерних элементов, кнопки имеют общий родительский объект <xref:System.Windows.Controls.InkCanvas>.  Кроме того, кнопки находятся выше по z\-координате, поэтому рукописный текст отображается позади.  
  
## См. также  
 <xref:System.Windows.Ink.DrawingAttributes>   
 <xref:System.Windows.InkCanvas.DefaultDrawingAttributes%2A>   
 <xref:System.Windows.Ink>