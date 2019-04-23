---
title: Создание кода в LINQ to SQL
ms.date: 03/30/2017
ms.assetid: ddcbdaa1-e7fa-4d85-a379-313b49965c07
ms.openlocfilehash: 6565655cdb3222a8c9fa7e7759bac09d57ee269b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321592"
---
# <a name="code-generation-in-linq-to-sql"></a>Создание кода в LINQ to SQL
Создание кода, представляющего базу данных, можно выполнить с помощью конструктора [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] или программы командной строки SQLMetal. В любом случае полный процесс создания кода включает три этапа.  
  
1. *Средство извлечения DBML* извлекает сведения о схеме из базы данных и перекомпилирует эти сведения в XML-файл DBML.  
  
2. Файл DBML сканируется *средством проверки DBML* наличие ошибок.  
  
3. Если ошибки не обнаружены, файл передается в генератор кода.  
  
 Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md). Разработчики, использующие Visual Studio можно также использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для создания кода. См. в разделе [средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
## <a name="dbml-extractor"></a>Средство извлечения DBML  
 Средство извлечения DBML является [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] компонент, который принимает метаданные базы данных в качестве входных данных и создает выходной файл DBML.  
  
## <a name="code-generator"></a>Генератор кода  
 Генератор кода находится [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] компонент, который преобразует файл DBML в файлы Visual Basic, C#, или файлы сопоставления XML.  
  
## <a name="xml-schema-definition-file"></a>Файл определения схемы XML  
 Файл DBML должен быть проверен на соответствие следующему XSD-файлу определению схемы.  
  
 Следует отличать этот файл определения схемы от файла определения схемы, который используется для проверки файла внешних сопоставлений. Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)).  
  
> [!NOTE]
>  Пользователи Visual Studio будет также найти этот файл XSD в диалоговом окне схем XML называется «DbmlSchema.xsd». Чтобы правильно использовать XSD-файл для проверки DBML-файла, см. в разделе [как: Проверка внешние файлы сопоставлений и DBML-](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).  
  
```  
?<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/dbml/2007" xmlns="http://schemas.microsoft.com/linqtosql/dbml/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Connection" type="Connection" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="EntityNamespace" type="xs:string" use="optional" />  
    <xs:attribute name="ContextNamespace" type="xs:string" use="optional" />  
    <xs:attribute name="Class" type="xs:string" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="ClassModifier" use="optional" />  
    <xs:attribute name="BaseType" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
    <xs:attribute name="ExternalMapping" type="xs:boolean" use="optional" />  
    <xs:attribute name="Serialization" type="SerializationMode" use="optional" />  
    <xs:attribute name="EntityBase" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:all>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
      <xs:element name="InsertFunction" type="TableFunction" minOccurs="0" maxOccurs="1" />  
      <xs:element name="UpdateFunction" type="TableFunction" minOccurs="0" maxOccurs="1" />  
      <xs:element name="DeleteFunction" type="TableFunction" minOccurs="0" maxOccurs="1" />  
    </xs:all>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="MemberModifier" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="IdRef" type="xs:IDREF" use="optional" />  
    <xs:attribute name="Id" type="xs:ID" use="optional" />  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="ClassModifier" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="MemberModifier" use="optional" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsReadOnly" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDelayLoaded" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="MemberModifier" use="optional" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="Cardinality" type="Cardinality" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Id" type="xs:ID" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="optional" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
    <xs:attribute name="Modifier" type="MemberModifier" use="optional" />  
    <xs:attribute name="HasMultipleResults" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="TableFunction">  
    <xs:sequence>  
      <xs:element name="Argument" type="TableFunctionParameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Return" type="TableFunctionReturn" minOccurs="0" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="FunctionId" type="xs:IDREF" use="required" />  
    <xs:attribute name="AccessModifier" type="AccessModifier" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Parameter" type="xs:string" use="optional" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="TableFunctionParameter">  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Version" type="Version" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="TableFunctionReturn">  
    <xs:attribute name="Member" type="xs:string" use="required" />  
  </xs:complexType>  
  <xs:complexType name="Connection">  
    <xs:attribute name="Provider" type="xs:string" use="required" />  
    <xs:attribute name="Mode" type="ConnectionMode" use="optional" />  
    <xs:attribute name="ConnectionString" type="xs:string" use="optional" />  
    <xs:attribute name="SettingsObjectName" type="xs:string" use="optional" />  
    <xs:attribute name="SettingsPropertyName" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="ConnectionMode">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ConnectionString" />  
      <xs:enumeration value="AppSettings" />  
      <xs:enumeration value="WebSettings" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AccessModifier">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Public" />  
      <xs:enumeration value="Internal" />  
      <xs:enumeration value="Protected" />  
      <xs:enumeration value="ProtectedInternal" />  
      <xs:enumeration value="Private" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="SerializationMode">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="None" />  
      <xs:enumeration value="Unidirectional" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="Version">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Current" />  
      <xs:enumeration value="Original" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ClassModifier">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Sealed" />  
      <xs:enumeration value="Abstract" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="MemberModifier">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Virtual" />  
      <xs:enumeration value="Override" />  
      <xs:enumeration value="New" />  
      <xs:enumeration value="NewVirtual" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="Cardinality">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="One" />  
      <xs:enumeration value="Many" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="sample-dbml-file"></a>Образец DBML-файла  
 Следующий код является фрагментом DBML-файла, созданного из образца базы данных Northwind. Полностью файл можно сформировать средством SQLMetal с **/XML** параметр. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<Database Name="northwnd" Class="Northwnd" xmlns="http://schemas.microsoft.com/dsltools/DLinqML">  
  
  <Table Name="Customers">  
    <Type Name="Customer">  
      <Column Name="CustomerID" Type="System.String" DbType="NChar(5) NOT NULL" IsPrimaryKey="True" CanBeNull="False" />  
      <Column Name="CompanyName" Type="System.String" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Type="System.String" DbType="NVarChar(30)" CanBeNull="True" />  
      <Column Name="ContactTitle" Type="System.String" DbType="NVarChar(30)" CanBeNull="True" />  
      <Column Name="Address" Type="System.String" DbType="NVarChar(60)" CanBeNull="True" />  
      <Column Name="City" Type="System.String" DbType="NVarChar(15)" CanBeNull="True" />  
      <Column Name="Region" Type="System.String" DbType="NVarChar(15)" CanBeNull="True" />  
      <Column Name="PostalCode" Type="System.String" DbType="NVarChar(10)" CanBeNull="True" />  
      <Column Name="Country" Type="System.String" DbType="NVarChar(15)" CanBeNull="True" />  
      <Column Name="Phone" Type="System.String" DbType="NVarChar(24)" CanBeNull="True" />  
      <Column Name="Fax" Type="System.String" DbType="NVarChar(24)" CanBeNull="True" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" ThisKey="CustomerID" OtherKey="CustomerID" OtherTable="CustomerCustomerDemo" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" ThisKey="CustomerID" OtherKey="CustomerID" OtherTable="Orders" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>См. также

- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Внешнее сопоставление](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [Практическое руководство. Создание модели объектов в виде внешнего файла](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
