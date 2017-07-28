---
title: "Данные и объекты данных | Microsoft Docs"
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
  - "передача данных [WPF], перетаскивание"
  - "DataFormats - класс [WPF]"
  - "DataObject - класс [WPF]"
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Данные и объекты данных
Данные, которые передаются как часть операции перетаскивания, хранятся в объекте данных.  Концептуально объект данных состоит из одной или нескольких пар, перечисленных ниже.  
  
-   Объект <xref:System.Object>, который содержит фактические данные.  
  
-   Соответствующий идентификатор формата данных.  
  
 Сами данные могут состоять из всего, что может быть представлено как базовый <xref:System.Object>.  Соответствующий формат данных является строкой или типом <xref:System.Type>, который предоставляет подсказку, в каком формате представлены данные.  Объекты данных поддерживают размещение нескольких пар "данные\-формат данных"; это позволяет одному объекту данных предоставлять данные в нескольких форматах.  
  
<a name="Data_and_Data_Objects"></a>   
## Объекты данных  
 Все объекты данных должны реализовывать интерфейс <xref:System.Windows.IDataObject>, предоставляющий следующий стандартный набор методов для включения и упрощения передачи данных.  
  
|Метод|Сводка|  
|-----------|------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Извлекает объект данных в указанном формате данных.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Проверяет, доступны ли данные в указанном формате, или возможность их преобразования в указанный формат.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Возвращает список форматов, в которых данные хранятся в этом объекте данных или в которые их можно преобразовать.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Сохраняет указанные данные в объекте данных.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет базовую реализацию интерфейса <xref:System.Windows.IDataObject> в классе <xref:System.Windows.DataObject>.  Для многих распространенных сценариев передачи данных достаточно автоматически инициализируемого класса <xref:System.Windows.DataObject>.  
  
 Имеется несколько предварительно определенных форматов, таких как bitmap, CSV, file, HTML, RTF, string, text, и audio.  Сведения о предопределенных форматах данных, предоставляемых системой [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе с описанием класса <xref:System.Windows.DataFormats>.  
  
 Данные объекты обычно включают средства для автоматического преобразования данных, хранящихся в одном формате, в другой формат во время извлечения данных; их обычно называют средствами автоматического преобразования.  При запросе форматов данных, доступных в объекте данных, с помощью фильтрации можно отделить автоматически преобразуемые форматы данных от собственных форматов данных, вызвав метод <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> или <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> и задав для параметра `autoConvert` значение `false`.  При добавлении данных к объекту данных с помощью метода <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> автоматическое преобразование данных может быть запрещено путем задания значения `false` для параметра `autoConvert`.  
  
<a name="Working_with_Data_Objects"></a>   
## Работа с объектами данных  
 В этом разделе описаны общие методы создания и работы с объектами данных.  
  
### Создание новых объектов данных  
 Класс <xref:System.Windows.DataObject> предоставляет несколько перегруженных конструкторов, облегчающих заполнение нового экземпляра <xref:System.Windows.DataObject> одной парой "данные\-формат данных".  
  
 В следующем примере создается новый объект данных и используется один из перегруженных конструкторов <xref:System.Windows.DataObject.%23ctor%2A>\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) для инициализации объекта данных строкой и указанным форматом данных.  В этом случае формат данных определяется строкой. Класс <xref:System.Windows.DataFormats> предоставляет набор строк предопределенных типов.  Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Дополнительные примеры кода, создающего объект данных см. в разделе [Создание объекта данных](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### Хранение данных в нескольких форматах  
 В одном объекте данных могут храниться данные в нескольких форматах.  Использование нескольких форматов данных внутри одного объекта делает объект данных более доступным для различных приемников, в отличие от представления данных в одном формате.  Обратите внимание, что в общем случае источник перетаскивания должен знать о форматах данных, которые потенциально поддерживаются приемником.  
  
 В следующем примере показано использование метода <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> для добавления данных в нескольких форматах в объект данных.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### Запрос к объекту данных для получения доступных форматов  
 Поскольку один объект данных может содержать произвольное число форматов данных, объекты данных включают средства для получения списка доступных форматов данных.  
  
 В следующем примере кода используется перегрузка <xref:System.Windows.DataObject.GetFormats%2A> для получения массива строк, обозначающих все форматы данных, доступные в объекте данных \(как собственные, так и автоматически преобразуемые\).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Дополнительные примеры кода, которые запрашивают доступные форматы данных у объекта данных см. в разделе [Перечисление форматов данных в объекте данных](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Примеры запросов объектов данных на наличие определенного формата см. в разделе [Определение присутствия формата данных в объекте данных](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### Извлечение данных из объекта данных  
 Для извлечения данных в определенном формате из объекта данных необходимо просто вызвать один из методов <xref:System.Windows.DataObject.GetData%2A> и задать необходимый формат данных.  Один из методов <xref:System.Windows.DataObject.GetDataPresent%2A> можно использовать для проверки наличия определенного формата данных.  Метод <xref:System.Windows.DataObject.GetData%2A> возвращает данные объекта <xref:System.Object>. В зависимости от формата данных, этот объект может быть приведен к контейнеру определенного типа.  
  
 В следующем примере кода используется перегрузка <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> для проверки доступности указанного формата данных \(собственного или автоматически преобразованного\).  Если указанный формат доступен, в примере извлекаются данные с помощью метода <xref:System.Windows.DataObject.GetData%28System.String%29>.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Дополнительные примеры кода, которые извлекают данные из объекта данных, см. в разделе [Извлечение данных в определенном формате данных](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### Удаление данных из объекта данных  
 Данные не могут быть удалены напрямую из объекта данных.  Для эффективного удаления данных из объекта данных выполните следующие действия.  
  
1.  Создайте новый объект данных, который будет содержать только данные, которые требуется сохранить.  
  
2.  Скопируйте необходимые данные из старых объектов данных в новый объект данных \(с помощью команды "Копировать"\).  Чтобы скопировать данные, следует использовать один из методов <xref:System.Windows.DataObject.GetData%2A> для извлечения <xref:System.Object>, содержащего фрагмент данных, и один из методов <xref:System.Windows.DataObject.SetData%2A> для добавления данных в новый объект данных.  
  
3.  Замените старый объект данных новым.  
  
> [!NOTE]
>  Методы <xref:System.Windows.DataObject.SetData%2A> только добавляют данные к объекту данных. Они не заменяют данные даже при их совпадении с данными и форматом данных в предыдущем вызове.  Двукратный вызов метода <xref:System.Windows.DataObject.SetData%2A> для одной пары "данные\-формат данных" приведет к повторяющемуся отображению данных и формата данных в объекте.