---
title: Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150848"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="92c66-102">Сопоставление уникальных ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="92c66-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="92c66-103">В схеме определения XML Schema (XSD) **уникальный** элемент определяет ограничение уникальности элемента или атрибута.</span><span class="sxs-lookup"><span data-stu-id="92c66-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="92c66-104">В процессе преобразования схемы XML в реляционную схему наложенное на элемент или атрибут ограничение, гарантирующее уникальность, в XML-схеме сопоставляется с ограничением уникальности в объекте <xref:System.Data.DataTable> в соответствующем объекте <xref:System.Data.DataSet>, который формируется.</span><span class="sxs-lookup"><span data-stu-id="92c66-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="92c66-105">В следующей таблице излагаются атрибуты **msdata,** которые можно указать в **уникальном** элементе.</span><span class="sxs-lookup"><span data-stu-id="92c66-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="92c66-106">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="92c66-106">Attribute name</span></span>|<span data-ttu-id="92c66-107">Описание</span><span class="sxs-lookup"><span data-stu-id="92c66-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="92c66-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="92c66-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="92c66-109">Если этот атрибут указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="92c66-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="92c66-110">В противном случае атрибут **имени** предоставляет значение имени сограничения.</span><span class="sxs-lookup"><span data-stu-id="92c66-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="92c66-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="92c66-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="92c66-112">Если `PrimaryKey="true"` присутствует в **уникальном** элементе, создается уникальное ограничение с свойством **IsPrimaryKey,** установленным на **истину.**</span><span class="sxs-lookup"><span data-stu-id="92c66-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="92c66-113">В следующем примере показана схема XML, используюметодная **схема** для определения ограничения уникальности.</span><span class="sxs-lookup"><span data-stu-id="92c66-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="92c66-114">**Уникальный** элемент в схеме определяет, что для всех элементов **Заказчика** в экземпляре документа значение элемента child **CustomerID** должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="92c66-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="92c66-115">При создании **DataSet**процесс отображения считывает эту схему и генерирует следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="92c66-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="92c66-116">Процесс отображения также создает уникальное ограничение на столбец **CustomerID,** как показано в следующем **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="92c66-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="92c66-117">(Для простоты показаны только значимые свойства.)</span><span class="sxs-lookup"><span data-stu-id="92c66-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="92c66-118">В генерируемом **DataSet** свойство **IsPrimaryKey** настроено **на ложное** для уникального ограничения.</span><span class="sxs-lookup"><span data-stu-id="92c66-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="92c66-119">**Уникальное** свойство на столбце указывает на то, что значения столбца **CustomerID** должны быть уникальными (но они могут быть нулевой ссылкой, указанной свойством **allowDBNull** столбца).</span><span class="sxs-lookup"><span data-stu-id="92c66-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="92c66-120">Если вы измените схему и установите дополнительное значение атрибута **msdata:PrimaryKey** на **True,** уникальное ограничение создается на столе.</span><span class="sxs-lookup"><span data-stu-id="92c66-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="92c66-121">Свойство столбца **AllowDBNull** настроено на **ложное**свойство, а свойство **IsPrimaryKey** ограничения, установленного на **True,** тем самым делая столбец **CustomerID** основным ключевым столбцом.</span><span class="sxs-lookup"><span data-stu-id="92c66-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="92c66-122">Ограничение уникальности можно наложить на сочетание элементов или атрибутов в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="92c66-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="92c66-123">В следующем примере показано, как указать, что сочетание значений **CustomerID** и **CompanyName** должно быть уникальным для всех **Клиентов** в любом случае, добавив другой элемент **xs:field** в схему.</span><span class="sxs-lookup"><span data-stu-id="92c66-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="92c66-124">Это ограничение, которое создается в полученном **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="92c66-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="92c66-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="92c66-125">See also</span></span>

- [<span data-ttu-id="92c66-126">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="92c66-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="92c66-127">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="92c66-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="92c66-128">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="92c66-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
