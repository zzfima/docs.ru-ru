---
title: Средство первого контакта
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: ef19843d6c8a9de0b926dd8512f5a58a5966e1bf
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846185"
---
# <a name="contract-first-tool"></a>Средство первого контакта
Контракты службы часто приходится создавать из существующих служб. В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] классы контрактов данных можно создавать автоматически из существующих служб с помощью средства разработки на основе контракта. Для использования данного средства файл определения схемы XML (XSD) необходимо загрузить локально. Программа не может импортировать удаленные контракты данных через HTTP.

 Средство первого контакта интегрирован в Visual Studio 2012 как задачу сборки. Файлы кода, формируемые задачей сборки, создаются при каждой сборке проекта, поэтому в проекте сразу же отражаются изменения в базовом контракте службы.

 Типы схем, которые может импортировать средство разработки на основе контракта:

```xml
<xsd:complexType>
<xsd:simpleType>
```

 Простые типы не создаются, если они являются примитивами, например `Int16` или `String`, сложные типы не создаются, если они имеют тип `Collection`. Типы также не создаются, если они являются частью другого `xsd:complexType`. Во всех этих случаях данные типы ссылаются на существующие в проекте типы.

## <a name="adding-a-data-contract-to-a-project"></a>Добавление в проект контракта данных
 Перед использованием средства на основе контракта в проект следует добавить контракт службы (XSD). В качестве наглядного примера будет использоваться следующий контракт. Это определение службы является небольшим подмножеством контракта службы, используемого API поиска службы Bing.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="ServiceSchema"
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"
    elementFormDefault="qualified"
    xmlns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
>
  <xs:complexType name="SearchRequest">
    <xs:sequence>
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="WebSearchOption">
    <xs:restriction base="xs:string">
      <xs:enumeration value="DisableHostCollapsing" />
      <xs:enumeration value="DisableQueryAlterations" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

 Чтобы добавить приведенный выше контракт службы в проект, щелкните правой кнопкой мыши проект и выберите **Add New...** . Выберите определение схемы на панели WCF диалогового окна «Шаблоны» и присвойте новому файлу имя SampleContract.xsd. Скопируйте и вставьте приведенный выше код в новый файл.

## <a name="configuring-contract-first-options"></a>Настройка параметров на основе контракта
 В меню "Свойства" проекта WCF можно настроить параметры на основе контракта. Чтобы включить разработку на основе контракта, выберите **включить XSD в качестве языка определения типов** флажок на странице WCF окна свойств проекта.

 ![Отображение параметров проекта WCF контракта&#45;первый](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")

 Чтобы настроить дополнительные свойства, нажмите кнопку «Дополнительно».

 ![Расширенный контракт&#45;первого свойства](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")

 Для создания кода на основе контракта можно установить следующие дополнительные параметры. Можно задать параметры только сразу для всех файлов в проекте. В настоящий момент нельзя задавать параметры для отдельных файлов.

-   **Режим сериализатора**: Этот параметр определяет, какой сериализатор используется для чтения файлов контракта службы. Когда **XML-сериализатор** выбран, **типы коллекций** и **повторно использовать типы** параметры отключены. Эти параметры применяются только к **сериализатор контракта данных**.

-   **Повторно использовать типы**: Этот параметр указывает, какие библиотеки используются для повторного использования типа. Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **Тип коллекции**: Этот параметр указывает тип полного или с указанием сборки для типа данных коллекции. Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **Тип словаря**: Этот параметр указывает тип полного или с указанием сборки для типа данных.

-   **EnableDataBinding**: Этот параметр указывает, следует ли реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс для всех типов данных, чтобы реализовать привязку данных.

-   **ExcludedTypes**: этот параметр определяет список типов полное или с указанием сборки должны быть исключены из ссылочных сборок. Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **GenerateInternalTypes**: Этот параметр указывает, следует ли создавать классы, помеченные как внутренние. Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **GenerateSerializableTypes**: Этот параметр указывает, следует ли создавать классы с <xref:System.SerializableAttribute> атрибута. Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **ImportXMLTypes**: Этот параметр указывает, следует ли настроить сериализатор контракта данных для применения <xref:System.SerializableAttribute> к классам без атрибута <xref:System.Runtime.Serialization.DataContractAttribute> атрибута.  Этот параметр применяется, только если **режим сериализатора** присваивается **сериализатор контракта данных**.

-   **SupportFx35TypedDataSets**: Этот параметр указывает, следует ли предоставлять дополнительные функциональные возможности для типизированных наборов данных, созданных для .NET Framework 3.5. Когда **режим сериализатора** присваивается **XML-сериализатор**, <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> расширения будут добавляться в средство импорта схемы XML, если это значение имеет значение True. При **режим сериализатора** имеет значение **сериализатор контракта данных**, тип <xref:System.DateTimeOffset> будут исключены из ссылок, если это значение имеет значение False, чтобы <xref:System.DateTimeOffset> всегда создается для предыдущих версий платформы.

-   **InputXsdFiles**: Этот параметр указывает список входных файлов. Каждый файл должен содержать допустимую схему XML.

-   **Язык**: Этот параметр указывает язык создаваемого кода контракта. Параметр должен быть распознаваемым методом <xref:System.CodeDom.Compiler.CodeDomProvider>.

-   **NamespaceMappings**: Этот параметр определяет сопоставление из целевого пространства имен XSD с пространствами имен CLR. В каждом сопоставлении необходимо использовать следующий формат:

    ```xml
    "<Schema Namespace>, <CLR Namespace>"
    ```

     Сериализатор XML принимает только одно сопоставление в следующем формате:

    ```xml
    "*, <CLR Namespace>"
    ```

-   **OutputDirectory**: Этот параметр задает каталог, где будут создаваться файлы кода.

 Параметры будут использоваться при построении проекта для создания типов контракта службы из файлов контракта службы.

## <a name="using-contract-first-development"></a>Разработка на основе контракта
 После добавления в проект контракта службы и подтверждения параметров сборки, постройте проект, нажав клавишу **F6**. Типы, определенные в контракте службы, становятся доступными для использования в проекте.

 Для использования типов, определенных в контракте службы, добавьте ссылку на `ContractTypes` в текущем пространстве имен.

```csharp
using MyProjectNamespace.ContractTypes;
```

 Типы, определенные в контракте службы, разрешаются для использования в проекте (как показано ниже).

 ![Использование типов, производных от контракта службы](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")

 Типы, созданные с помощью средства, помещаются в файл GeneratedXSDTypes.cs. Файл создается в \<каталог проекта > /obj/\<конфигурация построения >/xsdgeneratedcode / каталог по умолчанию. Образец схемы в начале этого раздела преобразуется следующим образом:

```csharp
//------------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by a tool.
//     Runtime Version:4.0.30319.17330
//
//     Changes to this file may cause incorrect behavior and will be lost if
//     the code is regenerated.
// </auto-generated>
//------------------------------------------------------------------------------

namespace TestXSD3.ContractTypes
{
    using System.Xml.Serialization;

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Diagnostics.DebuggerStepThroughAttribute()]
    [System.ComponentModel.DesignerCategoryAttribute("code")]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]
    public partial class SearchRequest
    {

        private string versionField;

        private string marketField;

        private string uILanguageField;

        private string queryField;

        private string appIdField;

        private double latitudeField;

        private bool latitudeFieldSpecified;

        private double longitudeField;

        private bool longitudeFieldSpecified;

        private double radiusField;

        private bool radiusFieldSpecified;

        public SearchRequest()
        {
            this.versionField = "2.2";
        }

        /// <remarks/>
        [System.ComponentModel.DefaultValueAttribute("2.2")]
        public string Version
        {
            get
            {
                return this.versionField;
            }
            set
            {
                this.versionField = value;
            }
        }

        /// <remarks/>
        public string Market
        {
            get
            {
                return this.marketField;
            }
            set
            {
                this.marketField = value;
            }
        }

        /// <remarks/>
        public string UILanguage
        {
            get
            {
                return this.uILanguageField;
            }
            set
            {
                this.uILanguageField = value;
            }
        }

        /// <remarks/>
        public string Query
        {
            get
            {
                return this.queryField;
            }
            set
            {
                this.queryField = value;
            }
        }

        /// <remarks/>
        public string AppId
        {
            get
            {
                return this.appIdField;
            }
            set
            {
                this.appIdField = value;
            }
        }

        /// <remarks/>
        public double Latitude
        {
            get
            {
                return this.latitudeField;
            }
            set
            {
                this.latitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LatitudeSpecified
        {
            get
            {
                return this.latitudeFieldSpecified;
            }
            set
            {
                this.latitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Longitude
        {
            get
            {
                return this.longitudeField;
            }
            set
            {
                this.longitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LongitudeSpecified
        {
            get
            {
                return this.longitudeFieldSpecified;
            }
            set
            {
                this.longitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Radius
        {
            get
            {
                return this.radiusField;
            }
            set
            {
                this.radiusField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool RadiusSpecified
        {
            get
            {
                return this.radiusFieldSpecified;
            }
            set
            {
                this.radiusFieldSpecified = value;
            }
        }
    }

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]
    public enum WebSearchOption
    {

        /// <remarks/>
        DisableHostCollapsing,

        /// <remarks/>
        DisableQueryAlterations,
    }
}
```

## <a name="errors-and-warnings"></a>Ошибки и предупреждения
 Ошибки и предупреждения, обнаруженные во время синтаксического анализа схемы XSD, появляются в виде ошибок и предупреждений сборки.

## <a name="interface-inheritance"></a>Наследование интерфейса
 С разработкой на основе контракта нельзя использовать наследование интерфейса. Это согласуется с тем, как интерфейсы действуют в других операциях. Чтобы использовать интерфейс, который наследует базовый интерфейс, используйте две отдельные конечные точки. Первая конечная точка использует унаследованный контракт, вторая реализует базовый интерфейс.
