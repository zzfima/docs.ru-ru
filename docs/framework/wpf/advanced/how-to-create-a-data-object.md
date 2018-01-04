---
title: "Как создать объект данных"
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
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a>Как создать объект данных
Следующие примеры демонстрируют различные способы создания объекта данных с помощью конструкторов, предоставляемые <xref:System.Windows.DataObject> класса.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) для инициализации объекта данных со строкой.  В этом случае соответствующий формат данных определяется автоматически в соответствии с типом хранимых данных, и по умолчанию разрешено автоматическое преобразование сохраненных данных.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a>Описание:  
 Следующий пример кода представляет собой сжатую версию приведенного выше кода.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) для инициализации объекта данных со строкой и указанного формата данных.  В этом случае формат данных задается строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предопределенных типов. Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a>Описание:  
 Следующий пример кода представляет собой сжатую версию приведенного выше кода.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%2A>) для инициализации объекта данных со строкой и указанного формата данных.  В этом случае формат данных задается <xref:System.Type> параметра.  Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a>Описание:  
 Следующий пример кода представляет собой сжатую версию приведенного выше кода.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) для инициализации объекта данных со строкой и указанного формата данных.  В этом случае формат данных задается строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предопределенных типов. Этот перегруженный конструктор позволяет вызывающему объекту укажите, разрешено ли автоматическое преобразование.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a>Описание:  
 Следующий пример кода представляет собой сжатую версию приведенного выше кода.  
  
### <a name="code"></a>Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.IDataObject>
