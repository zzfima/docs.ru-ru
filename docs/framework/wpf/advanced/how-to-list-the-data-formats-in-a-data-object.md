---
title: "Практическое руководство. Перечисление форматов данных в объекте данных"
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
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ef5657aefdf1c229b4f1749881cce1148435a8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a>Практическое руководство. Перечисление форматов данных в объекте данных
В следующих примерах показано использование <xref:System.Windows.DataObject.GetFormats%2A> перегруженных версий метода для получения массива строк, обозначающих каждого формата данных, который доступен в объект данных.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку, чтобы получить массив строк, обозначающих все форматы данных, доступные в объекте данных (собственный и автоматически преобразуемые).  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку, чтобы получить массив строк, обозначающих только форматы данных, доступные в объекте данных (фильтруются форматы данных автоматически преобразуемые).  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.IDataObject>  
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
