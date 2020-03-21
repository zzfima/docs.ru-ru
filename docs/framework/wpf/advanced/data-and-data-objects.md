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
ms.openlocfilehash: 532c254f997da183b073ddc9e00b4364ecfcd739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186336"
---
# <a name="data-and-data-objects"></a>Данные и объекты данных
Данные, передаваемые в рамках операции перетаскивания и падения, хранятся в объекте данных.  Концептуально объект данных состоит из одной или нескольких из следующих пар:  
  
- Который <xref:System.Object> содержит фактические данные.  
  
- Соответствующий идентификатор формата данных.  
  
 Данные сами по себе могут состоять из <xref:System.Object>всего, что может быть представлено в качестве основы.  Соответствующий формат данных <xref:System.Type> представляет собой строку или дает подсказку о том, в каком формате находится данные.  Объекты данных поддерживают размещение нескольких пар формата данных/данных; это позволяет одному объекту данных предоставлять данные в нескольких форматах.  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>Объекты данных  
 Все объекты данных должны реализовать <xref:System.Windows.IDataObject> интерфейс, который обеспечивает следующий стандартный набор методов, которые позволяют и облегчают передачу данных.  
  
|Метод|Сводка|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Извлекает объект данных в указанном формате данных.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Проверяет, доступны ли данные в указанном формате, или возможность их преобразования в указанный формат.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Возвращает список форматов, в которых данные хранятся в этом объекте данных или в которые их можно преобразовать.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Сохраняет указанные данные в объекте данных.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]обеспечивает базовую <xref:System.Windows.IDataObject> реализацию <xref:System.Windows.DataObject> в классе. Класс <xref:System.Windows.DataObject> запасов достаточен для многих распространенных сценариев передачи данных.  
  
 Существует несколько предопределенных форматов, таких как bitmap, CSV, файл, HTML, RTF, строка, текст и звук. Для получения информации о заранее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]определенных <xref:System.Windows.DataFormats> форматах данных, с помощью, см.  
  
 Объекты данных обычно включают средство для автоматической преобразования данных, хранящихся в одном формате, в другой формат при извлечении данных; этот объект называется автоматической конвертатом. При запросе форматов данных, доступных в объекте данных, автоматически конвертируемые форматы данных <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> могут быть `autoConvert` отфильтрованы из родных форматов данных, позвонив `false` <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> или метод и указав параметр как.  При добавлении данных <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> к объекту данных с помощью `autoConvert` метода `false`автопреобразование данных может быть запрещено, установив параметр.  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>Работа с объектами данных  
 В этом разделе описаны общие методы создания и работы с объектами данных.  
  
### <a name="creating-new-data-objects"></a>Создание новых объектов данных  
 Класс <xref:System.Windows.DataObject> предоставляет несколько перегруженных конструкторов, которые <xref:System.Windows.DataObject> облегчают заполнение нового экземпляра одной парой формата данных/данных.  
  
 Следующий пример кода создает новый объект данных и использует <xref:System.Windows.DataObject.%23ctor%2A><xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>один из перегруженных конструкторов () для инициализации объекта данных со строкой и указанным форматом данных.  В этом случае формат данных определяется строкой; <xref:System.Windows.DataFormats> класс предоставляет набор заранее определенных строк типа. Авто-конверсия хранимых данных допускается по умолчанию.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Для получения дополнительных примеров кода, создающий объект данных, [см.](how-to-create-a-data-object.md)  
  
### <a name="storing-data-in-multiple-formats"></a>Хранение данных в нескольких форматах  
 Один объект данных способен хранить данные в нескольких форматах.   Стратегическое использование нескольких форматов данных в рамках одного объекта данных потенциально делает объект данных расходуемым более широким кругом целей падения, чем если бы можно было бы представить только один формат данных.  Обратите внимание, что, как правило, источник перетаскивания должен быть агностиком в форматах данных, которые могут быть расходуемыми потенциальными целями падения.  
  
 В следующем примере показано, как использовать <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> метод для добавления данных в объект данных в нескольких форматах.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Запрос объекта данных для доступных форматов  
 Поскольку один объект данных может содержать произвольное количество форматов данных, объекты данных включают объекты для поиска списка доступных форматов данных.  
  
 В следующем примере <xref:System.Windows.DataObject.GetFormats%2A> код использует перегрузку для получения массива строк, обозначающего все форматы данных, доступные в объекте данных (как родной, так и путем автоматического преобразования).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Дополнительные примеры кода, запрашиваемого объектом данных для доступных форматов данных, [см.](how-to-list-the-data-formats-in-a-data-object.md)  Примеры запроса объекта данных о наличии определенного формата данных [см.](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)  
  
### <a name="retrieving-data-from-a-data-object"></a>Извлечение данных из объекта данных  
 Извлечение данных с объекта данных в определенном <xref:System.Windows.DataObject.GetData%2A> формате просто включает вызов одного из методов и определение желаемого формата данных.  Один из <xref:System.Windows.DataObject.GetDataPresent%2A> методов может быть использован для проверки на наличие определенного формата данных.  <xref:System.Windows.DataObject.GetData%2A>возвращает данные <xref:System.Object>в ; в зависимости от формата данных, этот объект может быть отлит в контейнер для конкретного типа.  
  
 В следующем примере <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> код использует перегрузку для проверки наличия определенного формата данных (родного или автоматического преобразования). Если указанный формат доступен, пример извлекает <xref:System.Windows.DataObject.GetData%28System.String%29> данные с помощью метода.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Для получения дополнительных примеров кода, извлекаемого данные из объекта данных, [см.](how-to-retrieve-data-in-a-particular-data-format.md)  
  
### <a name="removing-data-from-a-data-object"></a>Удаление данных из объекта данных  
 Данные не могут быть удалены непосредственно из объекта данных.  Чтобы эффективно удалить данные из объекта данных, выполните следующие действия:  
  
1. Создайте новый объект данных, который будет содержать только те данные, которые вы хотите сохранить.  
  
2. "Копировать" желаемые данные из старого объекта данных новому объекту данных.  Чтобы скопировать данные, <xref:System.Windows.DataObject.GetData%2A> используйте один из <xref:System.Object> методов для извлечения необработанных данных, а затем используйте один из <xref:System.Windows.DataObject.SetData%2A> методов для добавления данных в новый объект данных.  
  
3. Замените старый объект данных новым.  
  
> [!NOTE]
> Методы <xref:System.Windows.DataObject.SetData%2A> только добавляют данные к объекту данных; они не заменяют данные, даже если данные и формат данных точно такие же, как предыдущий вызов. Вызов <xref:System.Windows.DataObject.SetData%2A> дважды для одних и тех же данных и формата данных приведет к тому, что формат данных/данных будет дважды присутствовать в объекте данных.
