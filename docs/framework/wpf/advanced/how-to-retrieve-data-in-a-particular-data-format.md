---
title: "Практическое руководство. Получение данных в определенном формате данных | Microsoft Docs"
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
  - "DataFormats - класс [WPF], извлечение данных"
  - "DataObject - класс [WPF], извлечение данных"
  - "перетаскивание [WPF], извлечение данных"
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Получение данных в определенном формате данных
В следующих примерах показано, как можно извлечь данные из объекта в указанном формате данных.  
  
## Пример  
  
### Описание  
 В следующем примере кода используется перегрузка метода <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> для первой проверки доступности указанного формата данных \(изначально или с автоматическим преобразованием\); если указанный формат доступен, данные извлекаются с помощью метода <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## Пример  
  
### Описание  
 В следующем примере кода используется перегрузка метода <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> для первой проверки доступности указанного формата данных изначально\( фильтруются форматы с автоматическим преобразованием\); если указанный формат доступен, данные извлекаются с помощью метода <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## См. также  
 <xref:System.Windows.IDataObject>   
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)