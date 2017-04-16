---
title: "Практическое руководство. Определение присутствия формата данных в объекте данных | Microsoft Docs"
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
  - "форматы данных [WPF], определение наличия"
  - "DataFormats - класс [WPF]"
  - "перетаскивание [WPF], наличие форматов данных"
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Определение присутствия формата данных в объекте данных
В следующих примерах показано использование различных перегрузок метода <xref:System.Windows.DataObject.GetDataPresent%2A> для определения того, находится ли конкретный формат данных в объекте данных.  
  
## Пример  
  
### Описание  
 В следующем примере кода используется перегрузка <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> для запроса на наличие определенного формата данных через дескриптор строки.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## Пример  
  
### Описание  
 В следующем примере кода используется перегрузка <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> для запроса на наличие определенного формата данных через тип.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## Пример  
  
### Описание  
 В приведенном ниже примере кода используется перегрузка <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> для запроса к данным по строке дескриптора с указанием того, как обрабатывать автоматически преобразуемые форматы данных.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## См. также  
 <xref:System.Windows.IDataObject>