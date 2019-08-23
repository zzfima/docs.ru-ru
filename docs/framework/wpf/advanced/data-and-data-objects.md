---
title: Данные и объекты данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: 4b948a64a14df7ea79b54b810f734056d57ef406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964862"
---
# <a name="data-and-data-objects"></a>Данные и объекты данных
Данные, передаваемые в рамках операции перетаскивания, сохраняются в объекте данных.  По сути, объект данных состоит из одной или нескольких следующих пар.  
  
- Объект <xref:System.Object> , содержащий фактические данные.  
  
- Соответствующий идентификатор формата данных.  
  
 Сами данные могут состоять из любого объекта, который можно представить в виде <xref:System.Object>основы.  Соответствующий формат данных — это строка или <xref:System.Type> , которая предоставляет подсказку о том, в каком формате находятся данные.  Объекты данных поддерживают размещение нескольких пар данных и форматов данных; Это позволяет одному объекту данных предоставлять данные в нескольких форматах.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Объекты данных  
 Все объекты данных должны реализовывать <xref:System.Windows.IDataObject> интерфейс, который предоставляет следующий стандартный набор методов, которые позволяют и упрощают перенос данных.  
  
|Метод|Сводка|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Извлекает объект данных в указанном формате данных.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Проверяет, доступны ли данные в указанном формате или их можно преобразовать в.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Возвращает список форматов, в которых хранятся данные в этом объекте данных, или их можно преобразовать в.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Сохраняет указанные данные в этом объекте данных.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет базовую реализацию <xref:System.Windows.IDataObject> <xref:System.Windows.DataObject> в классе. Класс акции <xref:System.Windows.DataObject> достаточно для многих распространенных сценариев обмена данными.  
  
 Существует несколько предварительно определенных форматов, таких как точечный рисунок, CSV, файл, HTML, RTF, строка, текст и звук. Сведения о предварительно определенных форматах данных, предоставляемых с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе Справочник по <xref:System.Windows.DataFormats> классам.  
  
 Объекты данных обычно включают в себя средство для автоматического преобразования данных, хранящихся в одном формате, в другой формат при извлечении данных. Это средство называется автоматическое преобразование. При запросе форматов данных, доступных в объекте данных, автоматическое преобразование форматов данных <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> может быть отфильтровано из собственных форматов данных путем вызова метода или <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> с указанием `autoConvert` параметра в виде `false`.  При добавлении данных в объект данных с помощью <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> метода автоматическое преобразование данных может быть запрещено путем `autoConvert` присвоения параметру `false`значения.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Работа с объектами данных  
 В этом разделе описываются распространенные методы создания объектов данных и работы с ними.  
  
### <a name="creating-new-data-objects"></a>Создание новых объектов данных  
 Класс предоставляет несколько перегруженных конструкторов, которые упрощают заполнение нового <xref:System.Windows.DataObject> экземпляра одной парой данных и формата данных. <xref:System.Windows.DataObject>  
  
 В следующем примере кода создается новый объект данных и используется один из перегруженных конструкторов <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) для инициализации объекта данных строкой и указанным форматом данных.  В этом случае формат данных задается строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предварительно определенных типов. Автоматическое преобразование сохраненных данных по умолчанию разрешено.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Дополнительные примеры кода, который создает объект данных, см. [в разделе Создание объекта данных](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Хранение данных в нескольких форматах  
 Один объект данных может хранить данные в нескольких форматах.   Стратегическое использование нескольких форматов данных в одном объекте данных потенциально делает объект данных более широко большим, чем в случае, если может быть представлен только один формат данных.  Обратите внимание, что в общем случае источник перетаскивания должен быть независимым от форматов данных, которые могут быть потреблены потенциальными целями перетаскивания.  
  
 В следующем примере показано, как использовать <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> метод для добавления данных в объект данных в нескольких форматах.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Запрос к объекту данных для доступных форматов  
 Поскольку один объект данных может содержать произвольное число форматов данных, объекты данных включают средства для получения списка доступных форматов данных.  
  
 В следующем примере кода <xref:System.Windows.DataObject.GetFormats%2A> перегрузка используется для получения массива строк, обозначающих все форматы данных, доступные в объекте данных (как в собственном коде, так и с помощью автоматического преобразования).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Дополнительные примеры кода, который запрашивает объект данных для доступных форматов данных, см. в разделе [Вывод списка форматов данных в объекте данных](how-to-list-the-data-formats-in-a-data-object.md).  Примеры запроса объекта данных на наличие определенного формата данных см. [в разделе Определение наличия формата данных в объекте данных](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Получение данных из объекта данных  
 Извлечение данных из объекта данных в определенном формате просто подразумевает вызов одного из <xref:System.Windows.DataObject.GetData%2A> методов и указание требуемого формата данных.  Один из <xref:System.Windows.DataObject.GetDataPresent%2A> методов можно использовать для проверки наличия определенного формата данных.  <xref:System.Windows.DataObject.GetData%2A>Возвращает данные в <xref:System.Object>; в зависимости от формата данных этот объект можно привести к контейнеру определенного типа.  
  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузка для проверки доступности указанного формата данных (собственного или с помощью автоматического преобразования). Если указанный формат доступен, в примере данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29> метода.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Дополнительные примеры кода, получающего данные из объекта данных, см. [в разделе Получение данных в определенном формате данных](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Удаление данных из объекта данных  
 Данные нельзя удалить непосредственно из объекта данных.  Чтобы эффективно удалить данные из объекта данных, выполните следующие действия.  
  
1. Создайте новый объект данных, который будет содержать только те данные, которые необходимо хранить.  
  
2. Скопируйте нужные данные из старого объекта данных в новый объект данных.  Чтобы скопировать данные, используйте один из <xref:System.Windows.DataObject.GetData%2A> методов для получения объекта <xref:System.Object> , содержащего необработанные данные, а <xref:System.Windows.DataObject.SetData%2A> затем используйте один из методов для добавления данных в новый объект данных.  
  
3. Замените старый объект данных новым.  
  
> [!NOTE]
> <xref:System.Windows.DataObject.SetData%2A> Методы добавляют данные только в объект данных; они не заменяют данные, даже если данные и формат данных точно совпадают с предыдущим вызовом. Вызов <xref:System.Windows.DataObject.SetData%2A> дважды для одних и тех же данных и формата данных приведет к тому, что формат данных и данных будет представлен дважды в объекте данных.
