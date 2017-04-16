---
title: "Как создать объект данных | Microsoft Docs"
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
  - "объекты данных [WPF], создание"
  - "DataObject - класс [WPF], создание"
  - "перетаскивание [WPF], создание объектов данных"
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Как создать объект данных
Далее приведены примеры различных способов создания объекта данных с помощью конструкторов, предоставленных классом <xref:System.Windows.DataObject>.  
  
## Пример  
  
### Описание  
 В следующем примере код создает новый объект данных и использует один из перегруженных конструкторов \(<xref:System.Windows.DataObject.%23ctor%28System.Object%29>\) для инициализации объекта данных со строкой.  В этом случае, соответствующий формат данных определяется автоматически, согласно типу хранимых данных, и их автоматическое преобразование разрешено по умолчанию.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### Описание  
 Следующий кода примера является сжатой версией кода, который приведен выше.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## Пример  
  
### Описание  
 В следующем примере код создает новый объект данных и использует один из перегруженных конструкторов \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) для инициализации объекта данных со строкой и заданным форматом данных.  В этом случае, формат данных определяется строкой. Класс <xref:System.Windows.DataFormats> предоставляет набор строк предопределенных типов.  Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### Описание  
 Следующий кода примера является сжатой версией кода, который приведен выше.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## Пример  
  
### Описание  
 В следующем примере код создает новый объект данных и использует один из перегруженных конструкторов \(<xref:System.Windows.DataObject.%23ctor%2A>\) для инициализации объекта данных со строкой и заданным форматом данных.  В этом случае, формат данных задается параметром <xref:System.Type>.  Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### Описание  
 Следующий кода примера является сжатой версией кода, который приведен выше.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## Пример  
  
### Описание  
 В следующем примере код создает новый объект данных и использует один из перегруженных конструкторов \(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>\) для инициализации объекта данных со строкой и заданным форматом данных.  В этом случае, формат данных определяется строкой. Класс <xref:System.Windows.DataFormats> предоставляет набор строк предопределенных типов.  Этот перегруженный конструктор позволяет вызывающему объекту определить, разрешено ли автоматическое преобразование.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### Описание  
 Следующий кода примера является сжатой версией кода, который приведен выше.  
  
### Код  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## См. также  
 <xref:System.Windows.IDataObject>