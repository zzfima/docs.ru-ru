---
title: "Сериализация и десериализация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3d71814c-bda7-424b-85b7-15084ff9377a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a73fa30f1ebae805abd6f3e7e397d005d5b7130d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serialization-and-deserialization"></a>Сериализация и десериализация
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] включает новый модуль сериализации - <xref:System.Runtime.Serialization.DataContractSerializer>. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> преобразует объекты [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в формат XML и обратно. В данном разделе объясняется, как работает сериализатор.  
  
 При сериализации объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] сериализатор поддерживает различные модели программирования сериализации, включая новую модель *контракта данных* . Полный список поддерживаемых типов см. в разделе [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Вводные сведения о контрактах данных см. в разделе [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 При десериализации XML-кода сериализатор использует классы <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter> . Благодаря поддержке классов <xref:System.Xml.XmlDictionaryReader> и <xref:System.Xml.XmlDictionaryWriter> в некоторых случаях сериализатор может создавать оптимизированный XML-код, например при использовании двоичного XML-формата [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также включает сопровождающий сериализатор - <xref:System.Runtime.Serialization.NetDataContractSerializer>. Сериализатор <xref:System.Runtime.Serialization.NetDataContractSerializer> аналогичен сериализаторам <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> в том, что он отображает имена типов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] как часть сериализованных данных. Он применяется при совместном использовании одних и тех же типов на концах сериализации и десериализации. Оба сериализатора ( <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.NetDataContractSerializer> ) являются производными от общего базового класса <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
> [!WARNING]
>  Класс <xref:System.Runtime.Serialization.DataContractSerializer> сериализует строки, содержащие управляющие символы с шестнадцатеричным значением меньше 20 в виде сущностей XML. Это может вызвать проблемы с клиентом не WCF при отправке в службу WCF таких данных.  
  
## <a name="creating-a-datacontractserializer-instance"></a>Создание экземпляра DataContractSerializer  
 Создание экземпляра <xref:System.Runtime.Serialization.DataContractSerializer> является важным этапом. После создания экземпляра невозможно менять какие-либо настройки.  
  
### <a name="specifying-the-root-type"></a>Задание корневого типа  
 *Корневой тип* - это тип, экземпляры которого сериализуются и десериализуются. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> имеет множество перегрузок конструктора, однако хотя бы корневой тип должен предоставляться с использованием параметра `type` .  
  
 Сериализатор, созданный для определенного корневого типа, невозможно использовать для сериализации (или десериализации) другого типа, если только он не наследуется от корневого типа. В следующем примере показаны два класса.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#1)]
 [!code-vb[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#1)]  
  
 Этот код создает экземпляр `DataContractSerializer` , который можно использовать только для сериализации и десериализации экземпляров класса `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#2)]
 [!code-vb[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#2)]  
  
### <a name="specifying-known-types"></a>Задание известных типов  
 Если в сериализуемых типах, которые еще не были обработаны с помощью атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute> или какого-либо другого механизма, применяется полиморфизм, то конструктору сериализатора с помощью параметра `knownTypes` необходимо передать список возможных известных типов. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] об известных типах см. в разделе [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 В следующем примере продемонстрирован класс `LibraryPatron`, который включает коллекцию указанного типа `LibraryItem`. Второй класс определяет тип `LibraryItem` . Третий и четвертый классы (`Book` и `Newspaper`) наследуются от класса `LibraryItem` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#3)]  
 [!code-vb[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#3)]  
  
 В следующем примере кода демонстрируется создание экземпляра сериализатора с использованием параметра `knownTypes` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#4)]
 [!code-vb[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#4)]  
  
### <a name="specifying-the-default-root-name-and-namespace"></a>Задание корневого имени и пространства имен по умолчанию  
 Как правило, при сериализации объекта имя и пространство имен по умолчанию внешнего элемента XML определяются в соответствии с именем и пространством имен контракта данных. Имена всех внутренних элементов определяются на основе имен членов данных, а их пространство имен представляет собой пространство имен контракта данных. В следующем примере задаются значения имени `Name` и пространства имен `Namespace` в конструкторах классов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#5)]
 [!code-vb[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#5)]  
  
 В ходе сериализации экземпляра класса `Person` создается XML-код, подобный следующему.  
  
```xml  
<PersonContract xmlns="http://schemas.contoso.com">  
  <AddressMember>  
    <StreetMember>123 Main Street</StreetMember>  
   </AddressMember>  
</PersonContract>  
```  
  
 Однако можно настроить имя и пространство имен корневого элемента по умолчанию, передав значения параметров `rootName` и `rootNamespace` конструктору <xref:System.Runtime.Serialization.DataContractSerializer> . Обратите внимание, что пространство имен `rootNamespace` не влияет на пространство имен содержащихся в нем элементов, которые соответствуют членам данных. Оно влияет только на пространство имен внешнего элемента.  
  
 Эти значения могут быть переданы в виде строк или экземпляров класса <xref:System.Xml.XmlDictionaryString> , что позволяет их оптимизировать с использованием двоичного XML-формата.  
  
### <a name="setting-the-maximum-objects-quota"></a>Задание максимальной квоты объекта  
 Некоторые перегрузки конструктора `DataContractSerializer` имеют параметр `maxItemsInObjectGraph` . Этот параметр определяет максимальное число объектов, которые сериализатор сериализует или десериализует за один вызов метода <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . (Этот метод всегда считывает один корневой объект, но в элементах данных этого объекта могут иметься другие объекты. Эти объекты, в свою очередь, могут иметь в своем составе другие объекты и т. д.) Значение по умолчанию — 65536. Обратите внимание, что при сериализации или десериализации массивов каждая запись массива считается отдельным объектом. Также обратите внимание, что некоторые объекты могут иметь большое представление в памяти, поэтому одной этой квоты может быть недостаточно для предотвращения атак типа "отказ в обслуживании". [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). При необходимости увеличить квоту по сравнению со значением по умолчанию следует увеличить ее как на стороне отправки (сериализации), так и на стороне получения (десериализации), так как квота действует как при считывании, так и при записи данных.  
  
### <a name="round-trips"></a>Циклы обработки  
 *Цикл обработки* совершается, когда объект десериализуется и повторно сериализуется за одну операцию. Таким образом, он перемещается от XML-кода к экземпляру объекта, а затем возвращается в поток XML.  
  
 Некоторые перегрузки конструктора `DataContractSerializer` имеют параметр `ignoreExtensionDataObject` , для которого по умолчанию задано значение `false` . В этом режиме по умолчанию данные можно без потерь отправлять в цикл обработки от новой версии контракта данных через старую версию обратно к новой при условии, что контракт данных реализует интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject> . Предположим, например, что версия 1 контракта данных `Person` содержит члены данных `Name` и `PhoneNumber`, а версия 2 добавляет член `Nickname`. Если реализуется объект `IExtensibleDataObject` , то при отправке информации из версии 2 в версию 1 данные `Nickname` сохраняются, а затем снова выдаются при повторной сериализации данных, поэтому данные не теряются при прохождении цикла обработки. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Контракты данных, совместимые с любыми будущими](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md) и [управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).  
  
#### <a name="security-and-schema-validity-concerns-with-round-trips"></a>Проблемы безопасности и допустимости схемы в циклах обработки  
 Циклы обработки влияют на безопасность. Например, десериализация и сохранение больших объемов лишних данных могут представлять угрозу безопасности. Проблемы безопасности при повторной выдаче этих данных обусловлены невозможностью провести проверку, особенно если в процессе задействованы цифровые сигнатуры. Например, в вышеприведенном сценарии конечная точка версии 1 могла бы подписать значение `Nickname` , которое содержит вредоносные данные. Наконец, могут возникнуть проблемы с допустимостью схемы: конечная точка может всегда выдавать только данные, которые строго соответствуют ее заявленному контракту, и не поддерживать других значений. В предыдущем примере в контракте конечной точки версии 1 говорится, что точка выдает только данные `Name` и `PhoneNumber`, а при использовании проверки допустимости схемы выдача дополнительного значения `Nickname` приводит к сбою проверки.  
  
#### <a name="enabling-and-disabling-round-trips"></a>Включение и отключение циклов обработки  
 Для отключения циклов обработки не реализуйте интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject> . Если невозможно управлять типами, для достижения такого же эффекта необходимо задать параметру `ignoreExtensionDataObject` значение `true` .  
  
### <a name="object-graph-preservation"></a>Сохранение графа объекта  
 Как правило, удостоверение объекта не имеет значения для сериализатора, как показано в следующем примере кода.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#6)]
 [!code-vb[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#6)]  
  
 В следующем примере кода демонстрируется создание заказа на покупку.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#7)]
 [!code-vb[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#7)]  
  
 Обратите внимание, что полям `billTo` и `shipTo` задан один и тот же экземпляр объекта. Однако созданный XML-код дублирует повторяющуюся информацию и по внешнему виду аналогичен следующему XML-коду.  
  
```xml  
<PurchaseOrder>  
  <billTo><street>123 Main St.</street></billTo>  
  <shipTo><street>123 Main St.</street></shipTo>  
</PurchaseOrder>  
```  
  
 Этот подход имеет следующие характеристики, которые могут оказаться нежелательными.  
  
-   Производительность. Репликация данных неэффективна.  
  
-   Циклические ссылки. Если объекты ссылаются на самих себя (даже через другие объекты), сериализация результатов репликации приводит к бесконечному циклу. (В этом случае сериализатор создает исключение <xref:System.Runtime.Serialization.SerializationException> .)  
  
-   Семантика. Иногда очень важно сохранить отнесение двух ссылок к одному и тому же объекту, а не к двум идентичным объектам.  
  
 По этим причинам некоторые перегрузки конструктора `DataContractSerializer` имеют параметр `preserveObjectReferences` (по умолчанию ему задано значение `false`). Если этому параметру задано значение `true`, используется специальный метод кодирования ссылок на объект, который поддерживается только [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] . Если задано значение `true`, пример XML-кода выглядит следующим образом.  
  
```xml  
<PurchaseOrder ser:id="1">  
  <billTo ser:id="2"><street ser:id="3">123 Main St.</street></billTo>  
  <shipTo ser:ref="2"/>  
</PurchaseOrder>  
```  
  
 Пространство имен "ser" относится к стандартному пространству имен сериализации http://schemas.microsoft.com/2003/10/Serialization/. Каждый блок данных сериализуется только один раз, ему присваивается идентификационный номер, и при использовании этих блоков в будущем создается ссылка на уже сериализованные данные.  
  
> [!IMPORTANT]
>  Если в контракте данных `XMLElement`присутствует и атрибут "id", и атрибут "ref", используется атрибут "ref", а атрибут "id" игнорируется.  
  
 Важно понимать существующие в этом режиме ограничения.  
  
-   XML-код, создаваемый сериализатором `DataContractSerializer` с помощью `preserveObjectReferences` с заданным значением `true` , не поддерживает возможность взаимодействия с какими-либо другими технологиями, доступ к нему может осуществлять только другой экземпляр `DataContractSerializer` , для `preserveObjectReferences` которого также задано значение `true`.  
  
-   Эта функция не обеспечивается поддержкой метаданных (схемы). Созданная схема действительна, только если `preserveObjectReferences` задано значение `false`.  
  
-   Эта функция может замедлить процесс сериализации и десериализации. Несмотря на отсутствие необходимости в репликации данных, в этом режиме необходимо выполнять дополнительные сравнения объектов.  
  
> [!CAUTION]
>  Если включен режим `preserveObjectReferences` , очень важно задать правильную квоту значению `maxItemsInObjectGraph` . Особенности обработки массивов в этом режиме позволяют злоумышленнику легко создавать небольшое вредоносное сообщение, которое приводит к расходованию больших объемов памяти, и препятствовать этому можно только заданием квоты `maxItemsInObjectGraph` .  
  
### <a name="specifying-a-data-contract-surrogate"></a>Задание суррогата контракта данных  
 Некоторые перегрузки конструктора `DataContractSerializer` имеют параметр `dataContractSurrogate` , для которого может быть задано значение `null`. В противном случае можно использовать этот параметр для задания *суррогата контракта данных*, представляющего собой тип, который реализует интерфейс <xref:System.Runtime.Serialization.IDataContractSurrogate> . Затем с помощью интерфейса можно настроить процесс сериализации и десериализации. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Суррогаты контракта данных](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).  
  
## <a name="serialization"></a>Сериализация  
 Следующая информация применима к любому классу, наследуемому от сериализатора <xref:System.Runtime.Serialization.XmlObjectSerializer>, включая классы <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.NetDataContractSerializer>  
  
### <a name="simple-serialization"></a>Простая сериализация  
 Основным способом сериализации объекта является его передача методу <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> . Существует три перегрузки, каждая из которых предназначена для записи в <xref:System.IO.Stream>, <xref:System.Xml.XmlWriter>или <xref:System.Xml.XmlDictionaryWriter>соответственно. При использовании перегрузки <xref:System.IO.Stream> на выходе получается XML-код в кодировке UTF-8. При использовании перегрузки <xref:System.Xml.XmlDictionaryWriter> сериализатор оптимизирует объекты на выходе для двоичного XML-формата.  
  
 При использовании <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> метода, сериализатор использует имя по умолчанию и пространство имен для программы-оболочки и записывает ее вместе с содержимым (см. предыдущий раздел «Задание по умолчанию корневого имени и пространства имен»).  
  
 Следующий пример демонстрирует запись с помощью <xref:System.Xml.XmlDictionaryWriter>.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#8)]
 [!code-vb[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#8)]  
  
 Это позволяет создать XML-код, подобный следующему.  
  
```xml  
<Person>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
### <a name="step-by-step-serialization"></a>Пошаговая сериализация  
 Для записи конечного элемента и содержимого объекта и закрытия программы-оболочки используйте методы <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A>, <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A>и <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> соответственно.  
  
> [!NOTE]
>  Перегрузок этих методов <xref:System.IO.Stream> нет.  
  
 Описанная здесь пошаговая сериализация, как правило, используется в двух случаях. Во-первых, чтобы вставлять содержимое, такое как атрибуты или комментарии, между `WriteStartObject` и `WriteObjectContent`, как показано в следующем примере.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#9)]
 [!code-vb[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#9)]  
  
 Это позволяет создать XML-код, подобный следующему.  
  
```xml  
<Person serializedBy="myCode">  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
 Во-вторых, пошаговая сериализация часто применяется, чтобы полностью избежать использования <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> и <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> и создать собственную пользовательскую программу-оболочку (или пропустить создание программы-оболочки в принципе), как показано в следующем примере кода.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#10)]
 [!code-vb[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#10)]  
  
 Это позволяет создать XML-код, подобный следующему.  
  
```xml  
<MyCustomWrapper>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</MyCustomWrapper>  
```  
  
> [!NOTE]
>  Использование пошаговой сериализации может привести к созданию XML-кода с недействительной схемой.  
  
## <a name="deserialization"></a>Десериализация  
 Следующая информация применима к любому классу, наследуемому от сериализатора <xref:System.Runtime.Serialization.XmlObjectSerializer>, включая классы <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.NetDataContractSerializer>  
  
 Основным способом десериализации объекта является вызов одной из перегрузок метода <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Существует три перегрузки, каждая из которых предназначена для считывания с помощью <xref:System.Xml.XmlDictionaryReader>, `XmlReader`или `Stream`соответственно. Обратите внимание, что перегрузка `Stream` создает текстовое средство чтения <xref:System.Xml.XmlDictionaryReader> , не защищенное никакими квотами, следовательно, его нужно использовать только для чтения надежных данных.  
  
 Также обратите внимание, что объект, возвращаемый методом `ReadObject` , должен быть приведен к соответствующему типу.  
  
 В следующем примере кода демонстрируется создание экземпляра сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> и средства чтения <xref:System.Xml.XmlDictionaryReader>, а также последующая десериализация экземпляра `Person` .  
  
 [!code-csharp[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#11)]
 [!code-vb[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#11)]  
  
 Прежде чем вызывать метод <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> , необходимо разместить средство чтения XML в программе-оболочке или не имеющем содержимого узле, который предшествует программе-оболочке. Это можно осуществить вызовом метода <xref:System.Xml.XmlReader.Read%2A> устройства чтения <xref:System.Xml.XmlReader> или производного метода и тестированием типа <xref:System.Xml.XmlReader.NodeType%2A>, как показано в следующем примере кода.  
  
 [!code-csharp[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#12)]
 [!code-vb[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#12)]  
  
 Обратите внимание, что до передачи устройства чтения методу `ReadObject`в этой программе-оболочке можно прочитать атрибуты.  
  
 При использовании одной из простых `ReadObject` перегрузок, десериализатор выполняет поиск по умолчанию имя и пространство имен в программе-оболочке (см. предыдущий раздел «Задание по умолчанию корневого имени и пространства имен») и выдает исключение при обнаружении неизвестно элемент. Предполагается, что в предыдущем примере используется программа-оболочка `<Person>` . Метод <xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> вызывается, чтобы убедиться, что средство чтения размещено в элементе, именованном как ожидается.  
  
 Можно отключить такую проверку имени программы-оболочки; некоторые перегрузки метода `ReadObject` используют логический параметр `verifyObjectName`, которому по умолчанию задано значение `true` . Если параметру задано значение `false`, имя и пространство имен программы-оболочки игнорируются. Эта функция полезна при чтении XML-кода, который был создан с использованием механизма пошаговой сериализации, описанной ранее.  
  
## <a name="using-the-netdatacontractserializer"></a>Использование NetDataContractSerializer  
 Основное различие между сериализаторами `DataContractSerializer` и <xref:System.Runtime.Serialization.NetDataContractSerializer> заключается в том, что `DataContractSerializer` использует имена контракта данных, а `NetDataContractSerializer` выводит полную сборку [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] и имена типов в сериализованном XML-коде. Это означает, что одни и те же типы должны совместно использоваться конечными точками сериализации и десериализации. Так как при использовании сериализатора `NetDataContractSerializer` всегда известны точные типы, которые должны быть десериализованы, механизм известных типов не требуется.  
  
 Однако в связи с этим могут возникнуть некоторые проблемы:  
  
-   Безопасность. Загружается любой тип, обнаруживаемый в десериализуемом XML-коде. Этим можно воспользоваться для принудительной загрузки вредоносных типов. Использование сериализатора `NetDataContractSerializer` с ненадежными данными возможно только при условии применения *связывателя сериализации* (с использованием свойства <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> или параметра конструктора). Связыватель позволяет загружать только надежные типы. Механизм связывателя аналогичен используемому типами в пространстве имен <xref:System.Runtime.Serialization> .  
  
-   Управление версиями. Использование полных имен типов и сборок в XML-коде строго ограничивает возможности управления версиями типов. При этом невозможно изменить имена типов, пространства имен, имена и версии сборок. Задание свойству <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> или параметру конструктора значения <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple> вместо значения по умолчанию <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Full> позволяет изменить версию сборки, но не универсальные типы параметров.  
  
-   Взаимодействие. Так как имена типов и сборок [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] включены в XML-код, никакие другие платформы, кроме [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , не могут получить доступ к получаемым данным.  
  
-   Производительность. Запись имен типов и сборок значительно увеличивает размер получаемого XML-кода.  
  
 Этот механизм аналогичен двоичной сериализации или сериализации SOAP, используемой удаленным взаимодействием [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (а именно, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>).  
  
 Сериализаторы `NetDataContractSerializer` и `DataContractSerializer`используются практически аналогично со следующими отличиями.  
  
-   Конструкторы не требуют указания корневого типа. Любой тип можно сериализовать с помощью одного и того же экземпляра сериализатора `NetDataContractSerializer`.  
  
-   Конструкторы не принимают список известных типов. Если имена типов сериализуются в XML-код, механизм известных типов не требуется.  
  
-   Конструкторы не принимают суррогаты контракта данных. Вместо этого они принимают параметр <xref:System.Runtime.Serialization.ISurrogateSelector> , называемый `surrogateSelector` (который сопоставляется со свойством <xref:System.Runtime.Serialization.NetDataContractSerializer.SurrogateSelector%2A> ). Это устаревший суррогатный механизм.  
  
-   Конструкторы принимают параметр стиля `assemblyFormat` , называемый <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> , который сопоставляется со свойством <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> . Как уже отмечалось ранее, эту особенность можно использовать для расширения возможностей сериализатора по управлению версиями. Этот подход аналогичен механизму <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> в двоичной сериализации или сериализации SOAP.  
  
-   Конструкторы принимают параметр <xref:System.Runtime.Serialization.StreamingContext> , называемый `context` , который сопоставляется со свойством <xref:System.Runtime.Serialization.NetDataContractSerializer.Context%2A> . Эту особенность можно использовать для передачи информации в сериализуемые типы. Данный подход аналогичен использованию механизма <xref:System.Runtime.Serialization.StreamingContext> в других классах <xref:System.Runtime.Serialization> .  
  
-   Методы <xref:System.Runtime.Serialization.NetDataContractSerializer.Serialize%2A> и <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize%2A> представляют собой псевдонимы для методов <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> и <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> . Они предоставляют более последовательную модель программирования с двоичной сериализацией или сериализацией SOAP.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Эти функции в разделе [двоичной сериализации](../../../../docs/standard/serialization/binary-serialization.md).  
  
 Форматы XML, используемые сериализаторами `NetDataContractSerializer` и `DataContractSerializer` , как правило, не совместимы. Следовательно, возможность сериализации с помощью одного из них и десериализации с помощью другого не поддерживается.  
  
 Обратите также внимание, что сериализатор `NetDataContractSerializer` не выдает полное имя типа и сборки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для каждого узла в графе объекта. Он выводит эту информацию, только если она неоднозначна. Таким образом, вывод данных осуществляется на уровне корневого объекта и для любых полиморфных случаев.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.NetDataContractSerializer>  
 <xref:System.Runtime.Serialization.XmlObjectSerializer>  
 [Двоичная сериализация](../../../../docs/standard/serialization/binary-serialization.md)  
 [Типы, поддерживаемые сериализатором контракта данных](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
