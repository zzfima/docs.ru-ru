---
title: Справочник по схеме контрактов данных
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: af183fa02ea3ec98f316979198624351d9b25f21
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963369"
---
# <a name="data-contract-schema-reference"></a>Справочник по схеме контрактов данных

В данном разделе описывается подмножество схемы XML (XSD), используемое <xref:System.Runtime.Serialization.DataContractSerializer> для описания типов среды CLR, применяемых для сериализации XML.

## <a name="datacontractserializer-mappings"></a>DataContractSerializer - сопоставления

`DataContractSerializer` сопоставляет типы CLR с XSD при экспорте метаданных из службы Windows Communication Foundation (WCF) с помощью конечной точки метаданных или [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Дополнительные сведения см. в разделе [сериализатор контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md).

`DataContractSerializer` также сопоставляет типы XSD типам среды CLR, когда для доступа к документам WSDL или XSD и создания контрактов данных для служб или клиентов используется Svcutil.exe.

Сопоставление типам CLR с помощью `DataContractSerializer`может выполняться только для экземпляров схемы XML, удовлетворяющих требованиям, описанным в данном документе.

### <a name="support-levels"></a>Уровни поддержки

`DataContractSerializer` обеспечивает следующие уровни поддержки для данной функции схемы XML:

- **Поддерживается**. Существует явное сопоставление этой функции типам и (или) атрибутам CLR с помощью `DataContractSerializer`.

- **Пропускается**. Эта функция используется в схемах, импортируемых `DataContractSerializer`, но не влияет на создание кода.

- **Запрещено**. `DataContractSerializer` не поддерживает импорт схемы с использованием данной функции. Например, при доступе Svcutil.exe к WSDL посредством схемы, использующей данную функцию, доступ осуществляется с помощью <xref:System.Xml.Serialization.XmlSerializer> . Это выполняется по умолчанию.

## <a name="general-information"></a>Общие сведения

- Пространство имен схемы описывается в разделе [Схема XML](https://www.w3.org/2001/XMLSchema). В этом документе используется префикс «xs».

- Атрибуты с пространством имен, отличным от пространства имен схемы, игнорируются.

- Любые заметки (за исключением описанных в данном документе) игнорируются.

### <a name="xsschema-attributes"></a>\<xs: schema >: Attributes

|Атрибут|DataContract|
|---------------|------------------|
|`attributeFormDefault`|Пропускается.|
|`blockDefault`|Пропускается.|
|`elementFormDefault`|Должен иметь полное имя. Для того чтобы схема поддерживалась `DataContractSerializer`, все элементы должны иметь полное имя. Это можно сделать, задав для xs:schema/@elementFormDefault значение "квалифицировано" или установив для xs:element/@form значение "квалифицировано" для каждого отдельного объявления элемента.|
|`finalDefault`|Пропускается.|
|`Id`|Пропускается.|
|`targetNamespace`|Поддерживается и сопоставляется пространству имен контракта данных. Если данный атрибут не определен, используется пустое пространство имен. Не может быть зарезервированным `http://schemas.microsoft.com/2003/10/Serialization/`пространства имен.|
|`version`|Пропускается.|

### <a name="xsschema-contents"></a>\<xs: schema >: содержимое

|Содержание|Схема|
|--------------|------------|
|`include`|Поддерживается. `DataContractSerializer` поддерживает xs:include и xs:import. Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` . В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.|
|`redefine`|Запрещено. Использование `xs:redefine` запрещено `DataContractSerializer` по соображениям безопасности: для `x:redefine` требуется следовать `schemaLocation` . В некоторых случаях Svcutil.exe, использующее DataContract, ограничивает применение `schemaLocation`.|
|`import`|Поддерживается. `DataContractSerializer` поддерживает `xs:include` и `xs:import`. Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` . В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.|
|`simpleType`|Поддерживается. См. раздел `xs:simpleType` .|
|`complexType`|Поддерживается, сопоставляется контрактам данных. См. раздел `xs:complexType` .|
|`group`|Пропускается. `DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`. Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.|
|`attributeGroup`|Пропускается. `DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`. Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.|
|`element`|Поддерживается. См. «Объявление глобального элемента».|
|`attribute`|Пропускается. `DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`. Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.|
|`notation`|Пропускается.|

## <a name="complex-types--xscomplextype"></a>Сложные типы — \<xs: complexType >

### <a name="general-information"></a>Общие сведения

Каждый сложный тип \<xs: complexType > сопоставляется с контрактом данных.

### <a name="xscomplextype-attributes"></a>\<xs: complexType >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`abstract`|По умолчанию должен иметь значение false.|
|`block`|Запрещено.|
|`final`|Пропускается.|
|`id`|Пропускается.|
|`mixed`|По умолчанию должен иметь значение false.|
|`name`|Поддерживается и сопоставляется имени контракта данных. Если в имени имеются точки, выполняется попытка сопоставить тип внутреннему типу. Например, сложный тип с именем `A.B` сопоставляется контракту данных, который является внутренним типом для типа с именем контракта данных `A`, но только в том случае, если данный контракт данных существует. Может существовать более одного уровня вложения: например, `A.B.C` может быть внутренним типом, но только при условии, что и `A` , и `A.B` существуют.|

### <a name="xscomplextype-contents"></a>\<xs: complexType >: содержимое

|Содержание|Схема|
|--------------|------------|
|`simpleContent`|Расширения запрещены.<br /><br /> Ограничение разрешено только из `anySimpleType`.|
|`complexContent`|Поддерживается. См. «Наследование».|
|`group`|Запрещено.|
|`all`|Запрещено.|
|`choice`|Запрещено|
|`sequence`|Поддерживается, сопоставляется членам данных контракта данных.|
|`attribute`|Запрещено, даже если use="prohibited" (существует одно исключение). Только необязательные атрибуты из стандартного пространства имен сериализации поддерживаются. Они не сопоставляются членам данных в модели программирования контракта данных. В настоящее время только один подобный атрибут имеет значение; он рассматривается в разделе ISerializable. Другие атрибуты игнорируются.|
|`attributeGroup`|Запрещено. В выпуске WCF v1 `DataContractSerializer` не учитывает наличие `attributeGroup` внутри `xs:complexType`.|
|`anyAttribute`|Запрещено.|
|(пусто)|Сопоставляется с контрактом данных, не имеющем элементов данных.|

### <a name="xssequence-in-a-complex-type-attributes"></a>\<xs: Sequence > в сложном типе: атрибуты

|Атрибут|Схема|
|---------------|------------|
|`id`|Пропускается.|
|`maxOccurs`|По умолчанию должен иметь значение 1.|
|`minOccurs`|По умолчанию должен иметь значение 1.|

### <a name="xssequence-in-a-complex-type-contents"></a>\<xs: Sequence > в сложном типе: содержимое

|Содержание|Схема|
|--------------|------------|
|`element`|Каждый экземпляр сопоставляется с элементом данных.|
|`group`|Запрещено.|
|`choice`|Запрещено.|
|`sequence`|Запрещено.|
|`any`|Запрещено.|
|(пусто)|Сопоставляется с контрактом данных, не имеющем элементов данных.|

## <a name="elements--xselement"></a>Elements — \<xs: element >

### <a name="general-information"></a>Общие сведения

`<xs:element>` может использоваться в следующих случаях.

- Он может использоваться в `<xs:sequence>`, описывающей член данных обычного контракта данных (не коллекции). В этом случае атрибут `maxOccurs` должен быть равен 1. (Значение 0 недопустимо).

- Он может использоваться в `<xs:sequence>`, описывающей член данных контракта данных коллекции. В этом случае атрибут `maxOccurs` должен иметь значение больше 1 или unbounded.

- Он может использоваться в `<xs:schema>` в качестве объявления глобального элемента.

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a>\<xs: element > с maxOccurs = 1 в \<xs: Sequence > (элементы данных)

|Атрибут|Схема|
|---------------|------------|
|`ref`|Запрещено.|
|`name`|Поддерживается, сопоставляется с именем элемента данных.|
|`type`|Поддерживается, сопоставляется типу члена данных. Дополнительные сведения см. в разделе «Сопоставление тип-примитив». Если не задан (и элемент не содержит анонимный тип), предполагается `xs:anyType` .|
|`block`|Пропускается.|
|`default`|Запрещено.|
|`fixed`|Запрещено.|
|`form`|Должен иметь полное имя. Этот атрибут может быть задан через `elementFormDefault` в `xs:schema`.|
|`id`|Пропускается.|
|`maxOccurs`|1|
|`minOccurs`|Сопоставляется со свойством <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> элемента данных (`IsRequired` имеет значение true, когда `minOccurs` имеет значение 1).|
|`nillable`|Влияет на сопоставление типов. См. "Сопоставление тип-примитив".|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a>\<xs: element > с maxOccurs > 1 в \<xs: Sequence > (Collections)

- Сопоставляется <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.

- В типах коллекции только один xs:element допустим в xs:sequence.

 Коллекции могут быть следующих типов:

- Обычные коллекции (например, массивы).

- Коллекции-словари (сопоставляющие одно значение другому; например, <xref:System.Collections.Hashtable>).

- Единственное отличие между словарем и массивом типа пара ключ/значение заключается в создаваемой модели программирования. Существует механизм заметки схемы, который можно использовать чтобы указать, что данный тип является коллекцией-словарем.

Правила для атрибутов `ref`, `block`, `default`, `fixed`, `form`и `id` те же, что и в случае типов, не являющихся коллекциями. Другие атрибуты приведены в следующей таблице.

|Атрибут|Схема|
|---------------|------------|
|`name`|Поддерживается, сопоставляется свойству <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> в атрибуте `CollectionDataContractAttribute` .|
|`type`|Поддерживается, сопоставляется типу, хранящемуся в коллекции.|
|`maxOccurs`|Больше, чем 1 или unbounded. Для схемы контроллера домена следует использовать unbounded.|
|`minOccurs`|Пропускается.|
|`nillable`|Влияет на сопоставление типов. Этот атрибут игнорируется в случае коллекций-словарей.|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a>\<xs: element > в объявлении глобального элемента \<xs: schema >

- Объявление глобального элемента, имеющего то же имя и пространство имен, что и тип в схеме, или определяющего анонимный тип внутри себя, означает связь с типом.

- Экспорт схемы: связанные объявления глобальных элементов создаются для каждого создаваемого типа, как простого, так и сложного.

- Десериализация/сериализация: связанные объявления глобальных элементов используются в качестве корневых элементов данного типа.

- Импорт схемы: связанные объявления глобальных элементов не требуются и игнорируются, если они соответствуют следующим правилам (если только они не определяют типы).

|Атрибут|Схема|
|---------------|------------|
|`abstract`|Должен иметь значение false для связанных объявлений глобальных элементов.|
|`block`|Запрещено в связанных объявлениях глобальных элементов.|
|`default`|Запрещено в связанных объявлениях глобальных элементов.|
|`final`|Должен иметь значение false для связанных объявлений глобальных элементов.|
|`fixed`|Запрещено в связанных объявлениях глобальных элементов.|
|`id`|Пропускается.|
|`name`|Поддерживается. См. определение связанных объявлений глобальных элементов.|
|`nillable`|Должен иметь значение true для связанных объявлений глобальных элементов.|
|`substitutionGroup`|Запрещено в связанных объявлениях глобальных элементов.|
|`type`|Поддерживается и должен соответствовать связанному типу связанных объявлений глобальных элементов (если только элемент не содержит анонимный тип).|

### <a name="xselement-contents"></a>\<xs: element >: содержимое

|Содержание|Схема|
|--------------|------------|
|`simpleType`|Поддерживается.*|
|`complexType`|Поддерживается.*|
|`unique`|Пропускается.|
|`key`|Пропускается.|
|`keyref`|Пропускается.|
|(пусто)|Поддерживается.|

\* при использовании сопоставления `simpleType` и `complexType,` для анонимных типов такое же, как и для неанонимных типов, за исключением того, что нет анонимных контрактов данных, поэтому создается именованный контракт данных с созданным именем, производным от имени элемента. Ниже перечислены правила для анонимных типов.

- Сведения о реализации WCF: Если имя `xs:element` не содержит точек, то анонимный тип сопоставляется внутреннему типу внешнего типа контракта данных. Если имя содержит точки, итоговый тип контракта данных является независимым (не внутренним типом).

- Создаваемое имя контракта данных внутреннего типа - это имя контракта данных внешнего типа, за которым следует точка, имя элемента и строка Type.

- Если контракт данных с таким именем уже существует, уникальное имя создается путем добавления "1", "2", "3" и т. д., пока не будет создано уникальное имя.

## <a name="simple-types---xssimpletype"></a>Простые типы — \<xs: simpleType >

### <a name="xssimpletype-attributes"></a>\<xs: simpleType >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`final`|Пропускается.|
|`id`|Пропускается.|
|`name`|Поддерживается, сопоставляется имени контракта данных.|

### <a name="xssimpletype-contents"></a>\<xs: simpleType >: содержимое

|Содержание|Схема|
|--------------|------------|
|`restriction`|Поддерживается. Сопоставляется контрактам данных перечислений. Если этот атрибут не соответствует шаблону перечисления, он игнорируется. См. раздел «Ограничения `xs:simpleType` ».|
|`list`|Поддерживается. Сопоставляется контрактам данных перечислений флагов. См. раздел "Списки `xs:simpleType` ".|
|`union`|Запрещено.|

### <a name="xsrestriction"></a>\<xs: restriction >

- Ограничения сложных типов поддерживаются только для base="`xs:anyType`".

- Ограничения простых типов `xs:string` , не имеющие никаких других аспектов ограничения, кроме `xs:enumeration` , сопоставляются контрактам данных перечисления.

- Все другие ограничения простых типов сопоставляются типам, которые они ограничивают. Например, ограничение `xs:int` сопоставляется с целым числом так же, как и `xs:int` . Дополнительные сведения о сопоставлении типов-примитивов см. в разделе Сопоставление типов и примитивов.

### <a name="xsrestriction-attributes"></a>\<xs: restriction >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`base`|Должен быть поддерживаемым простым типом или `xs:anyType`.|
|`id`|Пропускается.|

### <a name="xsrestriction-for-all-other-cases-contents"></a>\<xs: restriction > для всех остальных случаев: содержимое

|Содержание|Схема|
|--------------|------------|
|`simpleType`|Если существует, должен быть образован от поддерживаемого примитивного типа.|
|`minExclusive`|Пропускается.|
|`minInclusive`|Пропускается.|
|`maxExclusive`|Пропускается.|
|`maxInclusive`|Пропускается.|
|`totalDigits`|Пропускается.|
|`fractionDigits`|Пропускается.|
|`length`|Пропускается.|
|`minLength`|Пропускается.|
|`maxLength`|Пропускается.|
|`enumeration`|Пропускается.|
|`whiteSpace`|Пропускается.|
|`pattern`|Пропускается.|
|(пусто)|Поддерживается.|

## <a name="enumeration"></a>Перечисление

### <a name="xsrestriction-for-enumerations-attributes"></a>\<xs: ограничение > для перечислений: атрибуты

|Атрибут|Схема|
|---------------|------------|
|`base`|Если существует, должен быть `xs:string`.|
|`id`|Пропускается.|

### <a name="xsrestriction-for-enumerations-contents"></a>\<xs: ограничение > для перечислений: содержимое

|Содержание|Схема|
|--------------|------------|
|`simpleType`|Если существует, должен быть ограничением перечисления, поддерживаемым контрактом данных (этот раздел).|
|`minExclusive`|Пропускается.|
|`minInclusive`|Пропускается.|
|`maxExclusive`|Пропускается.|
|`maxInclusive`|Пропускается.|
|`totalDigits`|Пропускается.|
|`fractionDigits`|Пропускается.|
|`length`|Запрещено.|
|`minLength`|Запрещено.|
|`maxLength`|Запрещено.|
|`enumeration`|Поддерживается. Перечисление id не учитывается, а value сопоставляется с именем значения в контракте данных перечисления.|
|`whiteSpace`|Запрещено.|
|`pattern`|Запрещено.|
|(пусто)|Поддерживается, сопоставляется пустому типу перечисления.|

 В следующем коде показан класс перечисления C#.

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

`DataContractSerializer`сопоставляет этот класс следующей схеме. Если значения перечисления начинаются с 1, блоки `xs:annotation` не создаются.

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### <a name="xslist"></a>\<xs:list>

`DataContractSerializer` сопоставляет типы перечисления, отмеченные `System.FlagsAttribute` , `xs:list` , образованному из `xs:string`. Никакие другие виды `xs:list` не поддерживаются.

### <a name="xslist-attributes"></a>\<xs: List >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`itemType`|Запрещено.|
|`id`|Пропускается.|

### <a name="xslist-contents"></a>\<xs: List >: содержимое

|Содержание|Схема|
|--------------|------------|
|`simpleType`|Должен быть ограничением из `xs:string` , использующей аспект `xs:enumeration` .|

Если значение перечисления не является членом последовательности степеней 2 (по умолчанию для флагов), значение помещается в элемент `xs:annotation/xs:appInfo/ser:EnumerationValue` .

В следующем коде показана установка флагов для типа перечисления.

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

Этот тип сопоставляется следующей схеме.

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a>Наследование

### <a name="general-rules"></a>Основные правила

Контракт данных может наследовать от другого контракта данных. Такие контракты данных сопоставляются базовым и образуются типами расширения с помощью конструктора схемы XML `<xs:extension>` .

Контракт данных не может наследовать от контракта данных коллекции.

В следующем коде показан пример контракта данных.

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

Этот контракт данных сопоставляется следующему объявлению типа схемы XML.

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a>\<xs: complexContent >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`id`|Пропускается.|
|`mixed`|Должен иметь значение false.|

### <a name="xscomplexcontent-contents"></a>\<xs: complexContent >: содержимое

|Содержание|Схема|
|--------------|------------|
|`restriction`|Запрещено, за исключением случая, когда base="`xs:anyType`". Последнее эквивалентно помещению содержимого `xs:restriction` прямо под контейнер `xs:complexContent`.|
|`extension`|Поддерживается. Сопоставляется наследованию контракта данных.|

### <a name="xsextension-in-xscomplexcontent-attributes"></a>\<xs: Extension > в \<xs: complexContent >: Attributes

|Атрибут|Схема|
|---------------|------------|
|`id`|Пропускается.|
|`base`|Поддерживается. Сопоставляется базовому типу контракта данных, от которого наследует этот тип.|

### <a name="xsextension-in-xscomplexcontent-contents"></a>\<xs: Extension > в \<xs: complexContent >: содержимое

Применяются те же правила, что и для содержимого `<xs:complexType>` .

Если дается `<xs:sequence>` , ее элементы сопоставляются дополнительным членам данных, присутствующим в производном контракте данных.

Если производный тип содержит элемент с тем же именем, что и элемент базового типа, дублирующееся объявление элемента сопоставляется члену данных с создаваемым уникальным именем. Положительные целые числа добавляются к имени члена данных («member1», «member2» и т. д.) до тех пор, пока не будет найдено уникальное имя. И наоборот:

- Если производный контракт данных имеет член данных с тем же именем и типом, что и член данных в базовом контракте данных, `DataContractSerializer` создает соответствующий элемент в производном типе.

- Если производный контракт данных имеет член данных с тем же именем, что и член данных в базовом контракте данных, но другой тип, `DataContractSerializer` импортирует схему с элементом типа `xs:anyType` как в базовый тип, так и в объявления производного типа. Исходное имя типа сохраняется в `xs:annotations/xs:appInfo/ser:ActualType/@Name`.

В обоих случаях может возникнуть схема с неоднозначной моделью содержимого, которая зависит от порядка соответствующих членов данных.

## <a name="typeprimitive-mapping"></a>Сопоставление тип-примитив

`DataContractSerializer` использует следующие сопоставления для примитивных типов схемы XML.

|Тип XSD|Тип .NET|
|--------------|---------------|
|`anyType`|<xref:System.Object>.|
|`anySimpleType`|<xref:System.String>.|
|`duration`|<xref:System.TimeSpan>.|
|`dateTime`|<xref:System.DateTime>.|
|`dateTimeOffset`|<xref:System.DateTime> и <xref:System.TimeSpan> для смещения. См. «Сериализация DateTimeOffset» ниже.|
|`time`|<xref:System.String>.|
|`date`|<xref:System.String>.|
|`gYearMonth`|<xref:System.String>.|
|`gYear`|<xref:System.String>.|
|`gMonthDay`|<xref:System.String>.|
|`gDay`|<xref:System.String>.|
|`gMonth`|<xref:System.String>.|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|Массив<xref:System.Byte> .|
|`hexBinary`|<xref:System.String>.|
|`float`|<xref:System.Single>.|
|`double`|<xref:System.Double>.|
|`anyURI`|<xref:System.Uri>.|
|`QName`|<xref:System.Xml.XmlQualifiedName>.|
|`string`|<xref:System.String>.|
|`normalizedString`|<xref:System.String>.|
|`token`|<xref:System.String>.|
|`language`|<xref:System.String>.|
|`Name`|<xref:System.String>.|
|`NCName`|<xref:System.String>.|
|`ID`|<xref:System.String>.|
|`IDREF`|<xref:System.String>.|
|`IDREFS`|<xref:System.String>.|
|`ENTITY`|<xref:System.String>.|
|`ENTITIES`|<xref:System.String>.|
|`NMTOKEN`|<xref:System.String>.|
|`NMTOKENS`|<xref:System.String>.|
|`decimal`|<xref:System.Decimal>.|
|`integer`|<xref:System.Int64>.|
|`nonPositiveInteger`|<xref:System.Int64>.|
|`negativeInteger`|<xref:System.Int64>.|
|`long`|<xref:System.Int64>.|
|`int`|<xref:System.Int32>.|
|`short`|<xref:System.Int16>.|
|`Byte`|<xref:System.SByte>.|
|`nonNegativeInteger`|<xref:System.Int64>.|
|`unsignedLong`|<xref:System.UInt64>.|
|`unsignedInt`|<xref:System.UInt32>.|
|`unsignedShort`|<xref:System.UInt16>.|
|`unsignedByte`|<xref:System.Byte>.|
|`positiveInteger`|<xref:System.Int64>.|

## <a name="iserializable-types-mapping"></a>Сопоставление типов ISerializable

В .NET Framework версии 1,0 <xref:System.Runtime.Serialization.ISerializable> было представлено как общий механизм сериализации объектов для сохранения или обмена данными. Существует множество типов .NET Framework, которые реализуют `ISerializable` и могут передаваться между приложениями. <xref:System.Runtime.Serialization.DataContractSerializer> поддерживает классы `ISerializable` . `DataContractSerializer` сопоставляет типы схемы реализации `ISerializable` , отличающиеся только полным именем типа (QName) и фактически являющиеся коллекциями свойств. Например, `DataContractSerializer` сопоставляет <xref:System.Exception> со следующим типом XSD в пространстве имен `http://schemas.datacontract.org/2004/07/System`.

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

Необязательный атрибут `ser:FactoryType` , объявленный в схеме сериализации контракта данных ссылается на класс фабрики, который может выполнить десериализацию типа. Класс фабрики может входить в коллекцию известных типов используемого экземпляра `DataContractSerializer` . Дополнительные сведения об известных типах см. в разделе [Data Contract известные типы](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).

## <a name="datacontract-serialization-schema"></a>DataContract - схема сериализации

Ряд схем, импортируемых `DataContractSerializer` , использует типы, элементы и атрибуты специального пространства имен сериализации контракта данных.

`http://schemas.microsoft.com/2003/10/Serialization`

Ниже приведен пример полного объявления схемы сериализации контракта данных.

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

Необходимо отметить следующее.

- `ser:char` введен для представления символов Юникода типа <xref:System.Char>.

- `valuespace``xs:duration` сокращается до упорядоченного набора, чтобы можно было выполнить его сопоставление <xref:System.TimeSpan>.

- `FactoryType` используется в схемах, экспортируемых из типов, унаследованных от <xref:System.Runtime.Serialization.ISerializable>.

## <a name="importing-non-datacontract-schemas"></a>Импорт схем, отличных от DataContract

В`DataContractSerializer` имеется функция `ImportXmlTypes` , которая выполняет импорт схем, не соответствующих профилю XSD `DataContractSerializer` (см. свойство <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ). Если задать этому параметру значение `true` , типы схемы, не удовлетворяющие требованиям, будут приняты и сопоставлены следующей реализации; <xref:System.Xml.Serialization.IXmlSerializable> упакует массив <xref:System.Xml.XmlNode> (отличается только имя класса).

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a>DateTimeOffset - сериализация

<xref:System.DateTimeOffset> не обрабатывается как примитивный тип. Вместо этого он сериализуется как сложный элемент с двумя частями. Первая часть представляет дату и время, а вторая - смещение даты и времени. В следующем примере кода показано значение DateTimeOffset.

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

Схема выглядит следующим образом.

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>См. также:

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
