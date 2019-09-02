---
title: Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 231f23ccf47f60b902fdd5c66b63fe1a750445f9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203417"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="553bc-102">Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="553bc-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="553bc-103">В схеме языка определения схемы XML (XSD) элемент **UNIQUE** указывает ограничение уникальности для элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="553bc-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="553bc-104">В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.</span><span class="sxs-lookup"><span data-stu-id="553bc-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="553bc-105">В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **UNIQUE** .</span><span class="sxs-lookup"><span data-stu-id="553bc-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="553bc-106">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="553bc-106">Attribute name</span></span>|<span data-ttu-id="553bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="553bc-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="553bc-108">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="553bc-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="553bc-109">Если этот атрибут указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="553bc-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="553bc-110">В противном случае атрибут **Name** предоставляет значение имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="553bc-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="553bc-111">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="553bc-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="553bc-112">Если `PrimaryKey="true"` имеется в элементе **UNIQUE** , то создается ограничение UNIQUE со свойством **IsPrimaryKey имеют значение** , установленным в **значение true**.</span><span class="sxs-lookup"><span data-stu-id="553bc-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="553bc-113">В следующем примере показана схема XML, использующая элемент **UNIQUE** для указания ограничения уникальности.</span><span class="sxs-lookup"><span data-stu-id="553bc-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="553bc-114">Элемент **UNIQUE** в схеме указывает, что для всех элементов **Customer** в экземпляре документа значение дочернего элемента **CustomerID** должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="553bc-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="553bc-115">При построении **набора данных**процесс сопоставления считывает эту схему и создает следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="553bc-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="553bc-116">Процесс сопоставления также создает ограничение UNIQUE для столбца **CustomerID** , как показано в следующем **наборе данных**.</span><span class="sxs-lookup"><span data-stu-id="553bc-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="553bc-117">(Для простоты показаны только значимые свойства.)</span><span class="sxs-lookup"><span data-stu-id="553bc-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="553bc-118">В созданном **наборе данных** свойству **IsPrimaryKey имеют значение** присваивается **значение false** для ограничения UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="553bc-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="553bc-119">Свойство **UNIQUE** в столбце указывает, что значения столбца **CustomerID** должны быть уникальными (но могут быть пустой ссылкой, как указано свойством **AllowDbNull** столбца).</span><span class="sxs-lookup"><span data-stu-id="553bc-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="553bc-120">Если изменить схему и задать для необязательного значения атрибута **msdata: PrimaryKey** значение **true**, в таблице будет создано ограничение UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="553bc-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="553bc-121">Свойство **AllowDbNull** column имеет значение **false**, а свойство **IsPrimaryKey имеют значение** ограничения имеет значение **true**, что делает столбец **CustomerID** первичным ключевым столбцом.</span><span class="sxs-lookup"><span data-stu-id="553bc-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="553bc-122">Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="553bc-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="553bc-123">В следующем примере показано, как указать, что сочетание значений **CustomerID** и **CompanyName** должно быть уникальным для всех **клиентов** в любом экземпляре путем добавления еще одного элемента **xs: field** в схему.</span><span class="sxs-lookup"><span data-stu-id="553bc-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="553bc-124">Это ограничение, создаваемое в результирующем наборе **данных**.</span><span class="sxs-lookup"><span data-stu-id="553bc-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="553bc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="553bc-125">See also</span></span>

- [<span data-ttu-id="553bc-126">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="553bc-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="553bc-127">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="553bc-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="553bc-128">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="553bc-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
