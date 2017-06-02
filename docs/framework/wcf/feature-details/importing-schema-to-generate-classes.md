---
title: "Импорт схемы для создания классов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, импорт и экспорт схемы"
  - "класс XsdDataContractImporter"
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Импорт схемы для создания классов
Для создания классов из схемы, которые могут использоваться в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], используйте <xref:System.Runtime.Serialization.XsdDataContractImporter> класса. В данном разделе описывается процесс и параметры импорта.  
  
## <a name="the-import-process"></a>Процесс импорта  
 Процесс импорта схемы начинается с <xref:System.Xml.Schema.XmlSchemaSet> и создает <xref:System.CodeDom.CodeCompileUnit>.  
  
 Класс `XmlSchemaSet` является частью объектной модели схемы (SOM) платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], представляющей набор документов схемы на языке определения схемы XML (XSD). Для создания `XmlSchemaSet` из набора документов XSD, десериализуйте каждый документ в <xref:System.Xml.Schema.XmlSchema> объекта (с помощью <xref:System.Xml.Serialization.XmlSerializer>) и добавьте эти объекты нового `XmlSchemaSet`.  
  
 Класс `CodeCompileUnit` является частью документной объектной модели кода (CodeDOM) платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], представляющей код [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] абстрактным способом. Чтобы создать фактический код из `CodeCompileUnit`, используйте подкласс <xref:System.CodeDom.Compiler.CodeDomProvider> класса, такие как <xref:Microsoft.CSharp.CSharpCodeProvider> или <xref:Microsoft.VisualBasic.VBCodeProvider> класса.  
  
#### <a name="to-import-a-schema"></a>Процедура импорта схемы  
  
1.  Создайте экземпляр <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2.  Необязательный. Передайте объект `CodeCompileUnit` в конструктор. Типы, созданные во время импорта схемы, добавляются в этот экземпляр класса `CodeCompileUnit` вместо создания нового пустого экземпляра класса `CodeCompileUnit`.  
  
3.  Необязательный. Вызовите один из <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> методы. Метод определяет, является ли данная схема действительной схемой контракта данных и можно ли ее импортировать. Метод `CanImport` имеет те же перегрузки, что метод `Import` (см. следующий шаг).  
  
4.  Вызовите один из перегруженных `Import` методов, например, <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29> метод.  
  
     Простейшая перегрузка принимает объект `XmlSchemaSet` и импортирует все типы, включая анонимные, найденные в данном наборе схем. Другие перегрузки позволяют указывать тип XSD или список типов для импорта (в виде <xref:System.Xml.XmlQualifiedName> или коллекции `XmlQualifiedName` объекты). В этом случае импортируются только указанные типы. Перегрузка принимает <xref:System.Xml.Schema.XmlSchemaElement> , импортирующий определенный элемент из объекта `XmlSchemaSet`, и его связанный тип (будь то анонимный или нет). Эта перегрузка возвращает объект `XmlQualifiedName`, представляющий имя контракта данных типа, созданного для этого элемента.  
  
     При нескольких вызовах метода `Import` в один и тот же объект `CodeCompileUnit` добавляется несколько типов. Тип не создается в объекте `CodeCompileUnit`, если он уже имеется в нем. Вызовите метод `Import` несколько раз для одного и того же объекта `XsdDataContractImporter` вместо использования нескольких объектов `XsdDataContractImporter`. Этот метод рекомендуется использовать, чтобы избежать создания повторяющихся типов.  
  
    > [!NOTE]
    >  В случае сбоя при импорте объект `CodeCompileUnit` будет находиться в непредсказуемом состоянии. Использование объекта `CodeCompileUnit`, возникшего после сбоя импорта, может привести к образованию уязвимых мест в системе безопасности.  
  
5.  Доступ `CodeCompileUnit` через <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> свойство.  
  
### <a name="import-options-customizing-the-generated-types"></a>Параметры импорта. Настройка созданных типов  
 Можно задать <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> свойство <xref:System.Runtime.Serialization.XsdDataContractImporter> к экземпляру <xref:System.Runtime.Serialization.ImportOptions> класс для управления различными аспектами процесса импорта. Некоторые параметры непосредственно влияют на созданные типы.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Управление уровнем доступа (GenerateInternal или коммутатор /internal)  
 Это соответствует **/ internal** переключиться [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Как правило, открытые типы создаются из схемы с закрытыми полями и соответствующими свойствами открытых членов данных. Чтобы вместо этого создать внутренние типы, присвойте <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> свойства `true`.  
  
 В следующем примере показано схема, преобразованная во внутренний класс после <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> свойству`true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Управление пространствами имен (Namespaces или коммутатор /namespace)  
 Это соответствует **/Namespace** переключиться `Svcutil.exe` средство.  
  
 Как правило, создаются типы, созданные из схемы в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] пространства имен, в каждом из пространств имен XSD соответствует определенному [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] пространства имен в соответствии с сопоставлением, описанным в [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Это сопоставление, можно настроить <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> свойства <xref:System.Collections.Generic.Dictionary%602>.\</TKey, TValue> Если пространство имен XSD найдено в словаре, соответствующее пространство имен [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] также берется из словаря.  
  
 Например, рассмотрим следующую схему.  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#10](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  -->  
  
 В следующем примере используется свойство `Namespaces` для сопоставления пространства имен "http://schemas.contoso.com/carSchema" и "Contoso.Cars".  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Добавление SerializableAttribute (GenerateSerializable или коммутатор /serializable)  
 Это соответствует **/ serializable** переключиться `Svcutil.exe` средство.  
  
 Иногда очень важно для типов, созданных из схемы для использования с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модулях сериализации среды выполнения (например, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> классы). Это полезно при использовании типов для удаленного взаимодействия [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Чтобы включить этот параметр, необходимо применить <xref:System.SerializableAttribute> к созданным типам помимо обычного атрибута <xref:System.Runtime.Serialization.DataContractAttribute> атрибута. Этот атрибут создается автоматически, если параметр импорта `GenerateSerializable` имеет значение `true`.  
  
 В следующем примере показан класс `Vehicle`, при создании которого параметр импорта `GenerateSerializable` был установлен на значение `true`.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Добавление поддержки привязки данных (EnableDataBinding или коммутатор /enableDataBinding)  
 Это соответствует **/enabledatabinding** переключиться в средстве Svcutil.exe.  
  
 Иногда возникает необходимость привязать созданные из схемы типы к компонентам графического пользовательского интерфейса, чтобы при каждом обновлении экземпляров этих типов автоматически обновлялся пользовательский интерфейс. `XsdDataContractImporter` Можно создавать типы, реализующие <xref:System.ComponentModel.INotifyPropertyChanged> интерфейса таким образом, что любое изменение свойства запускает событие. При создании типов для использования в среде программирования пользовательского интерфейса клиента, который поддерживает этот интерфейс (например, [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]), установите <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> свойства `true` для включения этой функции.  
  
 В следующем примере показан `Vehicle` класс, созданный с помощью <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> значение `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Параметры импорта. Выбор типов коллекции  
 Коллекции элементов представляют два специальных шаблона в формате XML: список элементов и ассоциации между двумя элементами. Ниже представлен пример списка строк.  
  
 <!-- TODO: review snippet reference [!code[C_SchemaImportExport#11](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  -->  
  
 Ниже приведен пример ассоциации между строкой и целым числом (`city name` и `population`).  
  
 <!-- TODO: review snippet reference [!code[C_SchemaImportExport#12](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  -->  
  
> [!NOTE]
>  Любая ассоциация может также считаться списком. Например, указанную выше ассоциацию можно рассматривать как список сложных объектов `city` с двумя полями (полем строки и целочисленным полем). Оба шаблона имеют представление в схеме XSD. Список и ассоциацию невозможно различить, поэтому такие шаблоны всегда обрабатываются как списки, если в схеме отсутствует специальная заметка, характерная для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В заметке указывается, что данный шаблон представляет ассоциацию. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
 Как правило, список импортируется как контракт данных коллекции, наследуемый от универсального списка, или как массив [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в зависимости от того, используется ли в схеме стандартный шаблон именования коллекций. Это описывается более подробно в [типы коллекций в контрактах данных](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md). Обычно ассоциации импортируются либо как <xref:System.Collections.Generic.Dictionary%602> или контракта данных коллекции, который является производным от объекта словаря.\</TKey, TValue> Например, рассмотрим следующую схему.  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#13](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  -->  
  
 Импорт выполняется следующим образом (вместо свойств для удобочитаемости показаны поля.)  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Можно настроить типы коллекций, созданные для таких шаблонов схемы. Например, может потребоваться создать коллекции, наследуемые от <xref:System.ComponentModel.BindingList%601> вместо <xref:System.Collections.Generic.List%601> класс для привязки типа к списку и его автоматически обновляться при изменении содержимого коллекции. Чтобы сделать это, задайте <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> свойство <xref:System.Runtime.Serialization.ImportOptions> класс к списку типов коллекций, для использования (в дальнейшем называемых ссылочных типов). При импорте какой-либо коллекции выполняется сканирование этого списка ссылочных типов коллекций и используется наиболее подходящая коллекция, если таковая найдена. Ассоциации сопоставляются только с типами, реализующими универсальный или неуниверсальный <xref:System.Collections.IDictionary> интерфейс, хотя списки сопоставляются с любым поддерживаемым типом коллекции.  
  
 Например если <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> свойству <xref:System.ComponentModel.BindingList%601>, `people` в предыдущем примере создается следующим образом.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Закрытый универсальный интерфейс считается наиболее подходящим. Например если типы `BindingList(Of Integer)` и <xref:System.Collections.ArrayList> передаются в коллекцию ссылочных типов, любые списки целых чисел, найденные в схеме, импортируются как `BindingList(Of Integer)`. Любые другие списки, например `List(Of String)`, импортируются как `ArrayList`.  
  
 Если тип, реализующий универсальный интерфейс `IDictionary`, добавляется в коллекцию ссылочных типов, параметры этого типа должны быть либо полностью открытыми, либо полностью закрытыми.  
  
 Дубликаты не разрешены. Например, нельзя добавить и `List(Of Integer)`, и `Collection(Of Integer)` в ссылочные типы. Это делает невозможным определение типа, который следует использовать при обнаружении списка целых чисел в схеме. Дубликаты обнаруживаются, только если в схеме есть тип, указывающий на проблему дубликатов. Например, если импортируемая схема не содержит список целых чисел, допускается иметь оба типа: `List(Of Integer)` и `Collection(Of Integer)` в коллекции ссылочных типов, но ни тот, ни другой не будут действовать.  
  
 Механизм ссылочных типов коллекций работает одинаково хорошо как для коллекций сложных типов (включая коллекции других коллекций), так и для коллекций примитивов.  
  
 `ReferencedCollectionTypes` Соответствует **/collectionType** переключиться в средстве SvcUtil.exe. Обратите внимание, что для ссылки на несколько типов коллекций, **/collectionType** коммутатор должен быть указан несколько раз. Если тип не существует в библиотеке MsCorLib.dll, его необходимо также задать ссылку на сборку с помощью **/reference** переключения.  
  
#### <a name="import-options-referencing-existing-types"></a>Параметры импорта. Ссылка на существующие типы  
 Иногда типы в схеме соответствуют существующим типам [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], и нет необходимости создавать эти типы с нуля. (Сведения, представленные в данном разделе, применимы только к типам, не являющимся коллекциями. Дополнительные сведения о типах коллекций см. в предыдущем разделе.)  
  
 Например, имеется стандартный корпоративный тип контракта данных "Person", который всегда необходимо использовать при представлении лица. Всякий раз при использовании этого типа некоторыми службами и при отображении его схемы в метаданных службы может возникать необходимость в повторном использовании существующего типа `Person` при импорте этой схемы вместо создания нового типа для каждой службы.  
  
 Для этого передайте список [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] типов, которые вы хотите повторно использовать в коллекцию <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> свойство возвращает на <xref:System.Runtime.Serialization.ImportOptions> класса. Если какой-либо из этих типов имеет имя контракта данных и пространство имен, соответствующие имени и пространству имен типа схемы, выполняется структурное сравнение. Если обнаружено, что типы имеют как соответствующие имена, так и соответствующие структуры, вместо создания нового типа существующий тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] используется повторно. Если соответствует только имя, но не структура, вызывается исключение. Обратите внимание, при создании ссылок на типы управление версиями не допускается (например, добавление новых необязательных членов данных). Структуры должны совпадать полностью.  
  
 Допустимо добавлять несколько типов с одинаковым именем контракта данных и пространством имен в коллекцию ссылочных типов, если никакие типы схемы не импортируются с этим именем и пространством имен. Это позволит быстро добавлять все типы в сборке в коллекцию, не задумываясь о возможных проблемах с дубликатами для типов, которые в настоящий момент отсутствуют в схеме.  
  
 `ReferencedTypes` Соответствует **/reference** переключиться в определенных режимах работы средства Svcutil.exe.  
  
> [!NOTE]
>  При использовании Svcutil.exe или (в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]) **Add Service Reference** автоматически ссылается на средства, все типы в библиотеке MsCorLib.dll.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Параметры импорта. Импорт схемы, отличной от DataContract, в виде типов IXmlSerializable  
 <xref:System.Runtime.Serialization.XsdDataContractImporter> поддерживает ограниченное подмножество схемы. При наличии неподдерживаемых конструкций схемы (например, атрибутов XML) попытка импорта заканчивается с ошибкой, и возникает исключение. Однако задание <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> свойства `true` расширяет диапазон поддерживаемых схем. Если задано значение `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> создает типы, реализующие <xref:System.Xml.Serialization.IXmlSerializable> интерфейса. Это обеспечивает прямой доступ к XML-представлению этих типов.  
  
##### <a name="design-considerations"></a>Вопросы проектирования  
  
-   Возможно, будет трудно работать со слабо типизированным XML-представлением напрямую. Рекомендуется использовать альтернативный модуль сериализации, такой как <xref:System.Xml.Serialization.XmlSerializer>для работы со схемой, не совместимой с данными контракты строго типизированным образом. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Использование класса XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).  
  
-   Некоторые конструкции схемы невозможно импортировать с <xref:System.Runtime.Serialization.XsdDataContractImporter> , даже когда <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> свойству `true`. Также рекомендуется использовать <xref:System.Xml.Serialization.XmlSerializer> для таких случаев.  
  
-   Точные конструкции схемы, поддерживаемые одновременно при <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> — `true` или `false` описаны в [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
-   Схемы для созданных <xref:System.Xml.Serialization.IXmlSerializable> типы, не сохраняются при импорте и экспорте точность. Это значит, что при экспорте схемы из созданных типов и импорте в виде классов исходная схема не возвращается.  
  
 Можно объединить <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> вариант с <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> описанные выше. Для типов, которые должны создаваться как <xref:System.Xml.Serialization.IXmlSerializable> реализации, структурная проверка пропускается при использовании <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> функции.  
  
 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> параметр соответствует **/importXmlTypes** переключитесь в средстве Svcutil.exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Работа с созданными типами IXmlSerializable  
 Созданный `IXmlSerializable` типы содержат закрытое поле с именем «nodesField», который возвращает массив <xref:System.Xml.XmlNode> объектов. При десериализации экземпляра такого типа доступ к данным XML можно получить непосредственно через это поле с помощью документной объектной модели XML. При сериализации экземпляра этого типа можно настроить это поле на требуемые данные XML, и он будет сериализован.  
  
 Это возможно благодаря реализации `IXmlSerializable`. В созданном `IXmlSerializable` типа, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> реализация вызывает <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> метод <xref:System.Runtime.Serialization.XmlSerializableServices> класса. Метод является вспомогательным методом, преобразующим данные XML, предоставленные с помощью <xref:System.Xml.XmlReader> в массив <xref:System.Xml.XmlNode> объектов. <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> реализации выполняет противоположные действия и преобразовывает массив `XmlNode` объектов в последовательность <xref:System.Xml.XmlWriter> вызовов. Это достигается с помощью <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A> метод.  
  
 Процесс экспорта схемы можно выполнить в созданных классах `IXmlSerializable`. Как уже говорилось ранее, исходная схема не возвращается. Вместо этого возвращается стандартный тип XSD "anyType", который является подстановочным знаком для любого типа XSD.  
  
 Это достигается путем применения <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> атрибут в созданный `IXmlSerializable` классы и определения метода, вызывающего <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> метод для создания типа «anyType».  
  
> [!NOTE]
>  <xref:System.Runtime.Serialization.XmlSerializableServices> типа существует только для поддержки этой конкретной функции. Не рекомендуется использовать его для других целей.  
  
#### <a name="import-options-advanced-options"></a>Параметры импорта. Дополнительные параметры  
 Ниже представлены дополнительные параметры импорта.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> свойство. Укажите <xref:System.CodeDom.Compiler.CodeDomProvider> , используемый для создания кода для созданных классов. Механизм импорта пытается избежать функций, <xref:System.CodeDom.Compiler.CodeDomProvider> не поддерживает. Например, в языке J# не поддерживаются универсальные шаблоны. Если указать поставщика кода J# в этом свойстве, универсальные типы не создается в средство импорта <xref:System.CodeDom.CodeCompileUnit>. Если <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> не задано, полный набор [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] использовать функции без ограничений.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> свойство. <xref:System.Runtime.Serialization.IDataContractSurrogate> с помощью этого свойства можно указать реализацию. <xref:System.Runtime.Serialization.IDataContractSurrogate> настраивается процесс импорта. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Суррогаты контрактов данных](../../../../docs/framework/wcf/extending/data-contract-surrogates.md). По умолчанию суррогат не используется.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 <xref:System.Runtime.Serialization.ImportOptions>   
 [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [Суррогаты контрактов данных](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)   
 [Импорт и Экспорт схемы](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)   
 [Экспорт схем из классов](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)   
 [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)