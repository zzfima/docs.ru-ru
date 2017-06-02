---
title: "Практическое руководство. Хранение данных в нескольких форматах в объекте данных | Microsoft Docs"
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
  - "DataFormats - класс [WPF], хранение в нескольких форматах"
  - "DataObject - класс [WPF], хранение в нескольких форматах"
  - "перетаскивание [WPF], хранение в нескольких форматах"
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Хранение данных в нескольких форматах в объекте данных
В следующем примере показано, как использовать метод <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> для добавления данных в нескольких форматах в объект данных.  
  
## Пример  
  
### Описание  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## См. также  
 <xref:System.Windows.IDataObject>   
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)