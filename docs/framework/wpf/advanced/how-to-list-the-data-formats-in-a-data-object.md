---
title: "Практическое руководство. Перечисление форматов данных в объекте данных | Microsoft Docs"
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
  - "форматы данных [WPF], список"
  - "DataFormats - класс [WPF]"
  - "перетаскивание [WPF], перечисление форматов данных"
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Перечисление форматов данных в объекте данных
В следующем примере показано, как использовать перегрузки метода <xref:System.Windows.DataObject.GetFormats%2A> для получения массива строк, обозначающих каждый доступный в объекте данных формат данных.  
  
## Пример  
  
### Описание  
 В следующем примере кода перегрузка <xref:System.Windows.DataObject.GetFormats%2A> используется для получения массива строк, обозначающих все форматы данных, доступные в объекте данных \(как собственные, так и автоматически преобразуемые\).  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## Пример  
  
### Описание  
 В следующем примере перегрузка <xref:System.Windows.DataObject.GetFormats%2A> используется для получения массива строк, обозначающих только форматы данных, доступные в объекте данных \(фильтруются автоматически преобразуемые форматы данных\).  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## См. также  
 <xref:System.Windows.IDataObject>   
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)