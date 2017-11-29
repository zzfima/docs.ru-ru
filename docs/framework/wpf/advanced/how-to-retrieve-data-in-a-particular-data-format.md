---
title: "Практическое руководство. Получение данных в определенном формате данных"
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
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e6513fd6d8d443b76059626c0e40991e35830c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a>Практическое руководство. Получение данных в определенном формате данных
В следующих примерах демонстрируется извлечение данных из объекта данных в указанном формате.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузку, чтобы сначала проверьте, если формат указанных данных доступен (изначально или с автоматическим преобразованием); Если указанный формат доступен, данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29> метод.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> перегрузку, чтобы сначала проверки доступности указанного формата данных изначально (фильтруются автоматически преобразуемые форматы); Если указанный формат доступен, данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29>метод.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.IDataObject>  
 [Общие сведения о перетаскивании](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
