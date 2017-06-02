---
title: "Хранение рукописных данных | Microsoft Docs"
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
  - "ISF - формат"
  - "рукописный ввод, хранение"
  - "ISF - формат"
  - "извлечение рукописных данных"
  - "хранение рукописных данных"
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Хранение рукописных данных
Методы <xref:System.Windows.Ink.StrokeCollection.Save%2A> предоставляют поддержку хранения рукописных данных в формате сериализованных рукописных данных \(ISF\).  Конструкторы класса <xref:System.Windows.Ink.StrokeCollection> обеспечивают поддержку чтения рукописных данных.  
  
## Хранение и извлечение рукописных данных  
 В этом разделе описываются способы хранения и получения рукописных данных в платформе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В следующем примере реализуется обработчик событий щелчка кнопки, который отображает диалоговое окно сохранения файла и сохраняет рукописные данные из <xref:System.Windows.Controls.InkCanvas> в файл.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 В следующем примере реализуется обработчик событий щелчка кнопки, который отображает диалоговое окно открытия файла и считывает рукописные данные из файла в <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## См. также  
 <xref:System.Windows.Controls.InkCanvas>   
 [Windows Presentation Foundation \(WPF\)](../../../../docs/framework/wpf/index.md)