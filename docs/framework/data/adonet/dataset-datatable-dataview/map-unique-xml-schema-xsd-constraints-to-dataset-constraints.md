---
title: Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 650cd6b8b8149529f115f22a11d19178fbd6d302
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108229"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="7aac3-102">Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="7aac3-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="7aac3-103">В схеме языка определения схемы XML **уникальный** элемент указывает на элемент или атрибут ограничение уникальности.</span><span class="sxs-lookup"><span data-stu-id="7aac3-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="7aac3-104">В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.</span><span class="sxs-lookup"><span data-stu-id="7aac3-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="7aac3-105">В следующей таблице описываются **msdata** атрибуты, которые можно указать в **уникальный** элемент.</span><span class="sxs-lookup"><span data-stu-id="7aac3-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="7aac3-106">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="7aac3-106">Attribute name</span></span>|<span data-ttu-id="7aac3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7aac3-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7aac3-108">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="7aac3-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="7aac3-109">Если этот атрибут указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="7aac3-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="7aac3-110">В противном случае **имя** атрибут содержит значение имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="7aac3-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="7aac3-111">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="7aac3-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="7aac3-112">Если `PrimaryKey="true"` присутствует в **уникальный** , ограничение unique создается элемент с **IsPrimaryKey** свойство значение **true**.</span><span class="sxs-lookup"><span data-stu-id="7aac3-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="7aac3-113">В следующем примере показано схему XML, который использует **уникальный** элемента, чтобы указать ограничение уникальности.</span><span class="sxs-lookup"><span data-stu-id="7aac3-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="7aac3-114">**Уникальный** элемент схемы указывает, что для всех **клиентов** элементы в документе экземпляра, значение **CustomerID** дочернего элемента должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="7aac3-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="7aac3-115">В стандартных **набора данных**, процесс сопоставления считывает эту схему и формирует следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="7aac3-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="7aac3-116">Процесс сопоставления также налагает ограничение уникальности на **CustomerID** столбца, как показано в следующем примере **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="7aac3-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="7aac3-117">(Для простоты показаны только значимые свойства.)</span><span class="sxs-lookup"><span data-stu-id="7aac3-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="7aac3-118">В **набора данных** сформированном **IsPrimaryKey** свойству **False** для ограничения уникальности.</span><span class="sxs-lookup"><span data-stu-id="7aac3-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="7aac3-119">**Уникальный** для столбца указывает, что **CustomerID** значения столбца должны быть уникальными (они могут быть ссылкой на null, в соответствии с **AllowDBNull** свойство столбца).</span><span class="sxs-lookup"><span data-stu-id="7aac3-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="7aac3-120">Если изменения схемы и задания необязательному **msdata: PrimaryKey** значение для атрибута **True**, создается ограничение уникальности для таблицы.</span><span class="sxs-lookup"><span data-stu-id="7aac3-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="7aac3-121">**AllowDBNull** столбца задано значение **False**и **IsPrimaryKey** набора ограничений-значение **True**, в результате чего **CustomerID** столбец столбцом первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="7aac3-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="7aac3-122">Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="7aac3-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="7aac3-123">В следующем примере показано, как указать, что сочетание **CustomerID** и **CompanyName** значения должны быть уникальными для всех **клиентов** в любом экземпляре путем Добавить новую **xs: field** элемента в схеме.</span><span class="sxs-lookup"><span data-stu-id="7aac3-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="7aac3-124">Это ограничение, которое создается в результате **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="7aac3-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="7aac3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7aac3-125">See also</span></span>

- [<span data-ttu-id="7aac3-126">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="7aac3-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="7aac3-127">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="7aac3-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="7aac3-128">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7aac3-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
