---
title: Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189921"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="8fa2d-102">Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="8fa2d-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="8fa2d-103">В схеме, можно задать ограничение ключа в элементе или атрибуте с помощью **ключ** элемент.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="8fa2d-104">Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="8fa2d-105">Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="8fa2d-106">В следующей таблице описываются **msdata** атрибуты, которые можно указать в **ключ** элемент.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="8fa2d-107">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="8fa2d-107">Attribute name</span></span>|<span data-ttu-id="8fa2d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8fa2d-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8fa2d-109">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="8fa2d-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="8fa2d-110">Если этот атрибут указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="8fa2d-111">В противном случае **имя** атрибут содержит значение имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="8fa2d-112">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="8fa2d-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="8fa2d-113">Если `PrimaryKey="true"` присутствует, **IsPrimaryKey** ограничение свойству **true**, делая его первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="8fa2d-114">**AllowDBNull** столбца задано значение **false**, поскольку первичные ключи не могут иметь значения null.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="8fa2d-115">При преобразовании схемы, в котором указывается ограничение ключа, процесс сопоставления создает ограничение уникальности для таблицы с **AllowDBNull** свойство столбца, значение **false** для каждого столбца в ограничение.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="8fa2d-116">**IsPrimaryKey** ограничения уникальности также задано значение **false** пока не задана `msdata:PrimaryKey="true"` на **ключ** элемент.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="8fa2d-117">Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="8fa2d-118">В следующем примере схемы **ключ** элемент задает ограничение ключа на **CustomerID** элемент.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="8fa2d-119">**Ключ** элемент указывает, что значения **CustomerID** дочерний элемент элемента **клиентов** элемент должен содержать уникальные значения и не может иметь значения null.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="8fa2d-120">При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="8fa2d-121">Сопоставление схем XML также создает **UniqueConstraint** на **CustomerID** столбца, как показано в следующем примере <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8fa2d-122">(Для простоты показаны только значимые свойства.)</span><span class="sxs-lookup"><span data-stu-id="8fa2d-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="8fa2d-123">В **набора данных** сформированном **IsPrimaryKey** свойство **UniqueConstraint** присваивается **true** так как схемы Указывает `msdata:PrimaryKey="true"` в **ключ** элемент.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="8fa2d-124">Значение **ConstraintName** свойство **UniqueConstraint** в **набора данных** значение **msdata: ConstraintName** атрибут, указанный в **ключ** элемента в схеме.</span><span class="sxs-lookup"><span data-stu-id="8fa2d-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa2d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8fa2d-125">See also</span></span>

- [<span data-ttu-id="8fa2d-126">Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet</span><span class="sxs-lookup"><span data-stu-id="8fa2d-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="8fa2d-127">Создание отношений DataSet из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="8fa2d-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="8fa2d-128">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8fa2d-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
