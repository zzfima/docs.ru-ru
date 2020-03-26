---
title: Средство первого контакта
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: 36e1a3e19f802ca5b74cf50f5bcd57c167e31e33
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291708"
---
# <a name="contract-first-tool"></a>Средство первого контакта
Контракты службы часто приходится создавать из существующих служб. В .NET Framework 4.5 и позже классы контрактов данных могут быть созданы автоматически из существующих служб с помощью инструмента «первый контракт». Для использования данного средства файл определения схемы XML (XSD) необходимо загрузить локально. Программа не может импортировать удаленные контракты данных через HTTP.

 Первый инструмент контракта интегрирован в Visual Studio 2012 в качестве задачи сборки. Файлы кода, формируемые задачей сборки, создаются при каждой сборке проекта, поэтому в проекте сразу же отражаются изменения в базовом контракте службы.

 Типы схем, которые может импортировать средство разработки на основе контракта:

```xml
<xsd:complexType>
 <xsd:simpleType>
 </xsd:simpleType>
</xsd:complexType>
```

 Простые типы не создаются, если они являются примитивами, например `Int16` или `String`, сложные типы не создаются, если они имеют тип `Collection`. Типы также не создаются, если они являются частью другого `xsd:complexType`. Во всех этих случаях данные типы ссылаются на существующие в проекте типы.

## <a name="adding-a-data-contract-to-a-project"></a>Добавление в проект контракта данных
 Перед использованием средства на основе контракта в проект следует добавить контракт службы (XSD). В качестве наглядного примера будет использоваться следующий контракт. Это определение службы представляет собой небольшой подмножество контракта на обслуживание, используемого API поиска Bing.

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

 Чтобы добавить вышеупомянутый сервисный контракт к проекту, нажмите правой кнопкой мыши проекта и выберите **Добавить новые ...**. Выберите определение схемы на панели WCF диалогового окна «Шаблоны» и присвойте новому файлу имя SampleContract.xsd. Скопируйте и вставьте приведенный выше код в новый файл.

## <a name="configuring-contract-first-options"></a>Настройка параметров на основе контракта
 Параметры, первые из которой по контракту могут быть настроены в меню Properties проекта WCF. Для обеспечения разработки с участием контракта выберите **Enable XSD** в качестве флажка языка определения типа на странице WCF окна свойств проекта.

 ![Скриншот WCF Options с включенной разработкой контракта.](./media/contract-first-tool/contract-first-options.png)

 Чтобы настроить дополнительные свойства, нажмите кнопку «Дополнительно».

 ![Расширенный контракт код Настройки диалогового окна.](./media/contract-first-tool/advanced-contract-settings.png)

 Для создания кода на основе контракта можно установить следующие дополнительные параметры. Можно задать параметры только сразу для всех файлов в проекте. В настоящий момент нельзя задавать параметры для отдельных файлов.

- **Режим Serializer**: Этот параметр определяет, какой сериализатор используется для чтения файлов контракта службы. При выборе **XML Serializer** параметры **типов коллекций** и **повторного использования** отключены. Эти опции применяются только к **Serializer data Contract.**

- **Повторное использование Типов**: Этот параметр определяет, какие библиотеки используются для повторного использования ввода. Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **Тип коллекции**: Этот параметр определяет полностью квалифицированный или сборочный тип, который будет использоваться для типа данных о сборе. Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **Тип словаря**: Этот параметр определяет полностью квалифицированный или сборочный тип, который будет использоваться для типа данных словаря.

- **EnableDataBinding**: Эта настройка определяет, <xref:System.ComponentModel.INotifyPropertyChanged> следует ли реализовать интерфейс на всех типах данных для реализации связывания данных.

- **ExcludedTypes**:Этот параметр определяет список полностью квалифицированных или сборочных типов, которые будут исключены из ссылки сборок. Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **GenerateInternalTypes**: Этот параметр определяет, следует ли создавать классы, которые помечены как внутренние. Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **GenerateSerializableTypes**: Этот параметр определяет, следует <xref:System.SerializableAttribute> ли генерировать классы с атрибутом. Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **ImportXMLTypes**: Этот параметр определяет, следует ли настроить серийный <xref:System.SerializableAttribute> контракт с <xref:System.Runtime.Serialization.DataContractAttribute> данными, чтобы применить атрибут к классам без атрибута.  Эта настройка применяется только в том случае, если **режим Serializer** установлен на **Serializer Data Contract Serializer.**

- **SupportFx35TypedDataSets**: Эта настройка определяет, следует ли предоставлять дополнительную функциональность для наборов набранных данных, созданных для .NET Framework 3.5. Когда **режим Serializer** будет установлен на <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> **XML Serializer,** расширение будет добавлено импортеру схемы XML, когда это значение будет установлено true. При установке **режима Serializer** на **Serializer Data Contract**тип <xref:System.DateTimeOffset> будет исключен из ссылок, когда <xref:System.DateTimeOffset> это значение будет установлено на ложное, так что a всегда генерируется для старых фреймворковых версий.

- **InputXsdFiles**: Эта настройка определяет список входных файлов. Каждый файл должен содержать допустимую схему XML.

- **Язык**: Этот параметр определяет язык генерируемого кода контракта. Параметр должен быть распознаваемым методом <xref:System.CodeDom.Compiler.CodeDomProvider>.

- **NamespaceMappings**: Эта настройка определяет отображение от XSD Целевые Именные пространства до названий CLR. В каждом сопоставлении необходимо использовать следующий формат:

    ```xml
    "Schema Namespace, CLR Namespace"
    ```

     Сериализатор XML принимает только одно сопоставление в следующем формате:

    ```xml
    "*, CLR Namespace"
    ```

- **ВыходНая директива**: Эта настройка определяет каталог, где будут создаваться файлы кода.

 Параметры будут использоваться при построении проекта для создания типов контракта службы из файлов контракта службы.

## <a name="using-contract-first-development"></a>Разработка на основе контракта
 После добавления сервисного контракта к проекту и подтверждения параметров сборки, постройте проект, нажав **F6.** Типы, определенные в контракте службы, становятся доступными для использования в проекте.

 Для использования типов, определенных в контракте службы, добавьте ссылку на `ContractTypes` в текущем пространстве имен.

```csharp
using MyProjectNamespace.ContractTypes;
```

 Типы, определенные в сервисном контракте, будут разрешимы в проекте, как показано ниже:

 ![SearchRequest класс, показывающий в IntelliSense после ввода первых нескольких букв.](./media/contract-first-tool/service-contract-types.png)

 Типы, созданные с помощью средства, помещаются в файл GeneratedXSDTypes.cs. Файл создается в \<каталоге проекта>/obj/build\<configuration>/XSDGeneratedCode/каталог по умолчанию. Схема образца в начале этой статьи преобразуется следующим образом:

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
