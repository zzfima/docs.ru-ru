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
ms.openlocfilehash: ff596dc7428c9d105a27999f216d33e735e35a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540323"
---
# <a name="data-and-data-objects"></a>Данные и объекты данных
Данные, которые передаются как часть операции перетаскивания и вставки хранятся в объект данных.  Концептуально объект данных состоит из одной или нескольких из следующих пар:  
  
-   <xref:System.Object> , Содержит фактические данные.  
  
-   Соответствующий идентификатор формата данных.  
  
 Сами данные могут состоять из всего, что может быть представлено как базовый <xref:System.Object>.  Соответствующий формат данных является строкой или <xref:System.Type> , предоставляющий возможности подсказку о формате.  Объекты данных поддерживают размещение нескольких пар данных и формата; Это позволяет один объект данных для предоставления данных в нескольких форматах.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Объекты данных  
 Все объекты данных должны реализовывать <xref:System.Windows.IDataObject> интерфейс, который предоставляет следующий стандартный набор методов для включения и упрощения передачи данных.  
  
|Метод|Сводка|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Извлекает объект данных в указанном формате.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Проверяет наличие данных в, или можно преобразовать в указанный формат.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Возвращает список форматов, которые хранятся в данные в этом объекте данных или можно преобразовать.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Сохраняет указанные данные в этом объекте данных.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Предоставляет базовую реализацию <xref:System.Windows.IDataObject> в <xref:System.Windows.DataObject> класса. Акции <xref:System.Windows.DataObject> класса является достаточным для многих распространенных сценариев передачи данных.  
  
 Существует несколько предварительно определенных форматов, например растрового изображения, CSV, файл, HTML, RTF, строки, текст и аудио. Сведения о предопределенных форматах данных предоставлены [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе <xref:System.Windows.DataFormats> класс справочном разделе.  
  
 Объекты данных обычно включают средства для автоматического преобразования данных, хранящихся в одном формате, в другой формат при извлечении данных. Эта функция позволяет называть автоматического преобразования. При запросе форматы данных, доступные в объекте данных, автоматически преобразуемые форматы данных могут быть отфильтрованы из собственные форматы данных путем вызова <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> или <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> метод и указывая `autoConvert` параметр как `false`.  При добавлении данных в объект данных с <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> метод автоматическое преобразование данных может быть запрещено, задав `autoConvert` параметр `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Работа с объектами данных  
 В этом разделе описаны общие методы для создания и работы с объектами данных.  
  
### <a name="creating-new-data-objects"></a>Создание новых объектов данных  
 <xref:System.Windows.DataObject> Класс предоставляет несколько перегруженных конструкторов, облегчающих заполнение нового <xref:System.Windows.DataObject> экземпляра с парой формат одного данных.  
  
 В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) для инициализации объекта данных со строкой и указанного формата данных.  В этом случае формат данных определяется строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предопределенных типов. По умолчанию разрешено автоматическое преобразование сохраненных данных.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Дополнительные примеры кода, создающего объект данных см. в разделе [создать объект данных](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Хранение данных в нескольких форматах  
 Один объект данных может сохранять данные в нескольких форматах.   Стратегического использования данных в нескольких форматах в один объект данных потенциально делает объект данных к использованию для более широкого мест перетаскивания, чем если только может быть представлен только один формат данных.  Обратите внимание, что, как правило, источником перетаскивания должны быть независимыми о форматах данных, которые могут использоваться потенциальных перетаскивания.  
  
 В следующем примере показано, как использовать <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> метод для добавления данных в объект данных в нескольких форматах.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Опрашивается объект данных для доступных форматов  
 Так как один объект данных может содержать произвольное число форматов данных, объекты данных включают средства для получения списка доступных форматов данных.  
  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetFormats%2A> перегрузку, чтобы получить массив строк, обозначающих все форматы данных, доступные в объекте данных (собственный и с автоматическим преобразованием).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Дополнительные примеры кода, который запрашивает объект данных для доступных форматов данных см. в разделе [перечисление форматов данных в объекте данных](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Примеры запросов объектов данных на наличие определенного формата см. в разделе [определить, если формат данных, присутствует в объекте данных](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Извлечение данных из объекта данных  
 Извлечение данных из объекта данных в определенном формате просто вызвать один из <xref:System.Windows.DataObject.GetData%2A> методы и указав требуемый формат данных.  Один из <xref:System.Windows.DataObject.GetDataPresent%2A> методы можно использовать для проверки на наличие определенного формата данных.  <xref:System.Windows.DataObject.GetData%2A> Возвращает данные в <xref:System.Object>; в зависимости от формата данных, этот объект может быть приведен к контейнеру определенного типа.  
  
 В следующем примере кода используется <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> перегрузку, чтобы определить доступность указанного формата данных (встроенный или с автоматическим преобразованием). Если указанный формат доступен, данные извлекаются с помощью <xref:System.Windows.DataObject.GetData%28System.String%29> метод.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Дополнительные примеры кода, который извлекает данные из объекта данных см. в разделе [извлечения данных в определенном формате данных](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Удаление данных из объекта данных  
 Невозможно непосредственно удалять данные из объекта данных.  Для эффективного удаления данных из объекта данных, выполните следующие действия.  
  
1.  Создайте новый объект данных, который будет содержать только данные, которые требуется сохранить.  
  
2.  «Копировать» необходимые данные из старых объектов данных в новый объект данных.  Чтобы скопировать данные, используйте один из <xref:System.Windows.DataObject.GetData%2A> методы для получения <xref:System.Object> , содержащий необработанные данные и затем использовать одну из <xref:System.Windows.DataObject.SetData%2A> методы для добавления данных в новый объект данных.  
  
3.  Замените старый объект данных новым.  
  
> [!NOTE]
>  <xref:System.Windows.DataObject.SetData%2A> Методы только добавить данные к объекту данных; они не заменять данные, даже если данные и формат данных одинаковы, как в предыдущем вызове. Вызов <xref:System.Windows.DataObject.SetData%2A> дважды для тем же данным и данным формат приведет к их присутствия дважды в объекте данных формат данных или данных.
