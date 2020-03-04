---
title: Правила сериализации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serialization, guidelines
- binary serialization, guidelines
ms.assetid: ebbeddff-179d-443f-bf08-9c373199a73a
ms.openlocfilehash: 067f32a026e3354e6c4256602ed17fd7d7bde0b8
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159797"
---
# <a name="serialization-guidelines"></a>Правила сериализации
В настоящем документе перечислены рекомендации, которые следует учитывать при разработке сериализуемого API.  

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
 Платформа .NET предусматривает три основные технологии сериализации, оптимизированные для различных сценариев. В следующей таблице описаны эти технологии, а также связанные с ними основные типы .NET.  
  
|Технология|Соответствующие классы|Примечания|  
|----------------|----------------------|-----------|  
|Сериализация контрактов данных|<xref:System.Runtime.Serialization.DataContractAttribute><br /><br /> <xref:System.Runtime.Serialization.DataMemberAttribute><br /><br /> <xref:System.Runtime.Serialization.DataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.NetDataContractSerializer><br /><br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer><br /><br /> <xref:System.Runtime.Serialization.ISerializable>|Общее сохранение<br /><br /> Веб-службы<br /><br /> JSON|  
|Сериализация XML|<xref:System.Xml.Serialization.XmlSerializer>|Формат XML <br />с полным доступом|  
|Сериализация времени выполнения (двоичная и SOAP-сериализация)|<xref:System.SerializableAttribute><br /><br /> <xref:System.Runtime.Serialization.ISerializable><br /><br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter><br /><br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|Удаленное взаимодействие .NET|  
  
 При разработке новых типов необходимо выбрать технологии, которые должны поддерживать эти типы (если применимо). Ниже приведены рекомендации, которые помогут сделать этот выбор и описано, как реализовать такую поддержку. Эти рекомендации не следует воспринимать как указание для выбора технологии сериализации для использования в реализации приложения или библиотеки. Они не связаны напрямую с разработкой API, поэтому их полное описание не может быть приведено в рамках данного раздела.  
  
## <a name="guidelines"></a>Рекомендации  
  
- Разработка новых типов ДОЛЖНА производиться с учетом сериализации.  
  
     Ее необходимо принимать во внимание при разработке всех типов, поскольку программе может потребоваться сохранение или передача экземпляра типа.  
  
### <a name="choosing-the-right-serialization-technology-to-support"></a>Правильный выбор сериализации для поддержки  
 Любой тип может как поддерживать одну или несколько технологий сериализации, так и не поддерживать ни одной.  
  
- Если экземпляры типа необходимо сохранять или использовать в веб-службах, РЕКОМЕНДУЕТСЯ выбрать поддержку *сериализации контракта данных*.  
  
- Если требуется дополнительный контроль над XML-форматом, создаваемым при сериализации типа, РЕКОМЕНДУЕТСЯ выбрать поддержку *XML-сериализации* вместо сериализации контракта данных или в дополнение к ней.  
  
     Поддержка этой технологии может потребоваться в определенных сценариях взаимодействий, где необходимо использование конструкций XML, неподдерживаемых при сериализации контракта данных, например при создании XML-атрибута.  
  
- Если экземпляры типа должны передаваться за пределы границ архитектуры удаленного взаимодействия .NET, РЕКОМЕНДУЕТСЯ выбрать поддержку *сериализации среды выполнения*.  
  
- НЕ рекомендуется выбирать сериализацию среды выполнения или XML-сериализацию для использования общих преимуществ, обеспечиваемых сохранением. Вместо этого рекомендуется использовать сериализацию контракта данных  
  
#### <a name="supporting-data-contract-serialization"></a>Поддержка сериализации контракта данных  
 Типы могут поддерживать сериализацию контракта данных при применении <xref:System.Runtime.Serialization.DataContractAttribute> к типу и применении <xref:System.Runtime.Serialization.DataMemberAttribute> к элементам (полям и свойствам) типа.  
  
 [!code-csharp[SerializationGuidelines#1](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#1)]
 [!code-vb[SerializationGuidelines#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#1)]  
  
1. РЕКОМЕНДУЕТСЯ пометить элементы данных типа как открытые, если тип может быть использован в среде с частичным доверием. В среде с полным доверием сериализаторы контрактов данных могут выполнять сериализацию и десериализацию закрытых типов и элементов, но в среде с частичным доверием эти операции могут выполняться только для открытых элементов.  
  
2. НЕОБХОДИМО реализовать метод считывания и метод задания для всех свойств, имеющих атрибут Data-MemberAttribute. При использовании сериализаторов контрактов данных тип считается сериализуемым только при наличии обоих методов - считывания и задания. Если тип не будет использоваться в среде с частичным доверием, то один или несколько методов доступа к свойству могут быть закрытыми.  
  
     [!code-csharp[SerializationGuidelines#2](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#2)]
     [!code-vb[SerializationGuidelines#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#2)]  
  
3. РЕКОМЕНДУЕТСЯ для инициализации десериализованных экземпляров использовать обратные вызовы сериализации.  
  
     При десериализации объектов конструкторы не вызываются. Следовательно, любая логика, выполняемая при нормальном построении, должна быть реализована как один из *обратных вызовов сериализации*.  
  
     [!code-csharp[SerializationGuidelines#3](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#3)]
     [!code-vb[SerializationGuidelines#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#3)]  
  
     Атрибут <xref:System.Runtime.Serialization.OnDeserializedAttribute> является наиболее часто используемым атрибутом обратного вызова. Другими атрибутами в семействе являются <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute>и <xref:System.Runtime.Serialization.OnSerializedAttribute>. Их можно использовать для пометки обратных вызовов, которые выполняются перед десериализацией, перед сериализацией и после сериализации соответственно.  
  
4. РЕКОМЕНДУЕТСЯ использовать <xref:System.Runtime.Serialization.KnownTypeAttribute> для указания конкретных типов, которые должны использоваться при десериализации более сложного графа объекта.  
  
     Например, если тип десериализуемого элемента данных представлен абстрактным классом, то сериализатору потребуются сведения об *известном типе*, чтобы выбрать конкретный тип для создания экземпляров и присваивания элементу. Если известный тип не указан, то его необходимо явным образом передать сериализатору (это можно сделать, передав известные типы конструктору сериализатора) либо указать в файле конфигурации.  
  
     [!code-csharp[SerializationGuidelines#4](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#4)]
     [!code-vb[SerializationGuidelines#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#4)]  
  
     В тех случаях, когда список известных типов статически неизвестен (при компиляции класса **Person**), **KnownTypeAttribute** также может указывать на метод, возвращающий список известных типов во время выполнения.  
  
5. При создании и изменении сериализуемых типов РЕКОМЕНДУЕТСЯ обеспечивать прямую и обратную совместимость.  
  
     Необходимо помнить, что сериализуемые потоки будущих версий типа могут быть десериализованы в текущую версию типа и наоборот. Необходимо учитывать, что элементы данных, даже закрытые и внутренние, не могут изменять свои имена, типы и даже свой порядок в будущих версиях типов, если не предприняты специальные меры для сохранения контракта с помощью явных параметров в его атрибутах. При изменении сериализуемых типов проверьте совместимость сериализации. Попробуйте десериализовать новую версию в предыдущую и наоборот.  
  
6. РЕКОМЕНДУЕТСЯ реализовать интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>. Это даст возможность обеспечить цикл обработки значений между различными версиями типа.  
  
     Интерфейс дает сериализатору гарантию отсутствия потерь данных при выполнении циклов обработки значений. Свойство <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> сохраняет все данные из будущей версии типа, неизвестные в текущей версии. Если текущая версия затем сериализуется и десериализуется в более позднюю, то дополнительные данные будут доступны в сериализованном потоке благодаря значению свойства **ExtensionData**.  
  
     [!code-csharp[SerializationGuidelines#5](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#5)]
     [!code-vb[SerializationGuidelines#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#5)]  
  
     Дополнительные сведения о создании контрактов данных, обладающих прямой совместимостью, см. в разделе [Контракты данных, совместимые с любыми будущими изменениями](../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
#### <a name="supporting-xml-serialization"></a>Поддержка XML-сериализации  
 Сериализация контрактов данных является основной (задаваемой по умолчанию) технологией сериализации в .NET Framework, однако существуют сценарии сериализации, которые эта технология не поддерживает. Например, она не обеспечивает полный контроль над формой XML-кода, создаваемого или используемого сериализатором. Если необходим столь высокий уровень контроля, используйте *XML-сериализацию*, разработав типы для поддержки этой технологии сериализации.  
  
1. Необходимо ИЗБЕГАТЬ разработки типов специально для XML-сериализации, за исключением случаев, когда необходим контроль над формой создаваемого XML-кода. Эта технология сериализации была заменена сериализацией контракта данных, описанной в предыдущем разделе.  
  
     Другими словами, не следует применять атрибуты из пространства имен <xref:System.Xml.Serialization> к новым типам, если только этот тип не планируется использовать с XML-сериализацией. В следующем примере описано использование **System.Xml.Serialization** для управления формой создаваемого XML-кода.  
  
     [!code-csharp[SerializationGuidelines#6](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#6)]
     [!code-vb[SerializationGuidelines#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#6)]  
  
2. РЕКОМЕНДУЕТСЯ использовать реализацию интерфейса <xref:System.Xml.Serialization.IXmlSerializable>, если необходим более высокий уровень контроля над формой сериализуемого XML-кода, чем тот, который обеспечивается при применении атрибутов XML-сериализации. Два метода интерфейса, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> и <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, позволяют полностью управлять сериализованным XML-потоком. При этом обеспечивается возможность контроля над схемой XML, которая создается для типа путем применения атрибута <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>.  
  
#### <a name="supporting-runtime-serialization"></a>Поддержка сериализации во время выполнения  
 *Сериализация во время выполнения* представляет собой технологию, используемую при удаленном взаимодействии .NET. Если планируется передача типов с использованием удаленного взаимодействия .NET, то необходимо убедиться, что они поддерживают сериализацию во время выполнения.  
  
 Базовая поддержка *сериализации во время выполнения* может быть обеспечена с помощью атрибута <xref:System.SerializableAttribute>. При более сложных сценариях выполняется реализация простого *шаблона сериализации во время выполнения* (реализация <xref:System.Runtime.Serialization.ISerializable> и обеспечение конструктора сериализации).  
  
1. РЕКОМЕНДУЕТСЯ обеспечить для типов поддержку сериализации во время выполнения, если типы будут использоваться при удаленном взаимодействии .NET. Например, в пространстве имен <xref:System.AddIn> используется удаленное взаимодействие .NET и поэтому все типы, передаваемые между надстройками **System.AddIn**, должны поддерживать сериализацию во время выполнения.  
  
     [!code-csharp[SerializationGuidelines#7](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#7)]
     [!code-vb[SerializationGuidelines#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#7)]  
  
2. РЕКОМЕНДУЕТСЯ реализовать *шаблон сериализации во время выполнения*, если требуется полный контроль над процессом сериализации. Например, в том случае, когда необходимо преобразовать сериализуемые или десериализуемые данные.  
  
     Шаблон очень прост. Нужно всего лишь реализовать интерфейс <xref:System.Runtime.Serialization.ISerializable> и предусмотреть специальный конструктор, который будет использоваться при десериализации объекта.  
  
     [!code-csharp[SerializationGuidelines#8](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#8)]
     [!code-vb[SerializationGuidelines#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#8)]  
  
3. СДЕЛАЙТЕ конструктор сериализации защищенным и принимающим два параметра, типы и имена которых точно совпадают с показанными в этом образце.  
  
     [!code-csharp[SerializationGuidelines#9](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#9)]
     [!code-vb[SerializationGuidelines#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#9)]  
  
4. Члены ISerializable НЕОБХОДИМО реализовать явно.  
  
     [!code-csharp[SerializationGuidelines#10](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#10)]
     [!code-vb[SerializationGuidelines#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#10)]  
  
5. Примените требование ссылки для **ISerializable.GetObjectData** реализации. Это гарантирует, что доступ к элементу имеют только полностью доверенный сериализатор и ядро.  
  
     [!code-csharp[SerializationGuidelines#11](../../../samples/snippets/csharp/VS_Snippets_CFX/serializationguidelines/cs/source.cs#11)]
     [!code-vb[SerializationGuidelines#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/serializationguidelines/vb/source.vb#11)]  
  
## <a name="see-also"></a>См. также раздел

- [Использование контрактов данных](../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Сериализатор контракта данных](../../../docs/framework/wcf/feature-details/data-contract-serializer.md)
- [Типы, поддерживаемые сериализатором контракта данных](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Двоичная сериализация](binary-serialization.md)
- [Удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
- [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)
