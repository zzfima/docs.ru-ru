---
title: Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150939"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="6daa6-102">Сопоставление ключевых ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="6daa6-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="6daa6-103">В схеме можно указать ограничение ключа на элементе или атрибуте с помощью **ключевого** элемента.</span><span class="sxs-lookup"><span data-stu-id="6daa6-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="6daa6-104">Элемент или атрибут, в котором указывается ограничение ключа, должен иметь уникальные значения во всех экземплярах схемы, не равные NULL.</span><span class="sxs-lookup"><span data-stu-id="6daa6-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="6daa6-105">Ограничение ключа похоже на ограничение уникальности за исключением того, что столбец, в котором определяется ограничение ключа, не может принимать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="6daa6-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="6daa6-106">В следующей таблице излагаются атрибуты **msdata,** которые можно указать в **ключевом** элементе.</span><span class="sxs-lookup"><span data-stu-id="6daa6-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="6daa6-107">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="6daa6-107">Attribute name</span></span>|<span data-ttu-id="6daa6-108">Описание</span><span class="sxs-lookup"><span data-stu-id="6daa6-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6daa6-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="6daa6-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="6daa6-110">Если этот атрибут указан, его значение используется в качестве имени ограничения.</span><span class="sxs-lookup"><span data-stu-id="6daa6-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="6daa6-111">В противном случае атрибут **имени** предоставляет значение имени сограничения.</span><span class="sxs-lookup"><span data-stu-id="6daa6-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="6daa6-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="6daa6-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="6daa6-113">Если `PrimaryKey="true"` присутствует, свойство ограничения **IsPrimaryKey** настроено на **истину,** что делает его основным ключом.</span><span class="sxs-lookup"><span data-stu-id="6daa6-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="6daa6-114">Свойство столбца **AllowDBNull** настроено на **ложное,** поскольку первичные ключи не могут иметь нулевых значений.</span><span class="sxs-lookup"><span data-stu-id="6daa6-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="6daa6-115">При преобразовании схемы, в которой указывается ограничение ключа, процесс отображения создает уникальное ограничение на столе с свойством столбца **AllowDBNull,** установленным **для ложного** для каждого столбца в стаблене.</span><span class="sxs-lookup"><span data-stu-id="6daa6-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="6daa6-116">Свойство **IsPrimaryKey** уникального ограничения также устанавливается на `msdata:PrimaryKey="true"` **ложное,** если вы не указали на **ключевом** элементе.</span><span class="sxs-lookup"><span data-stu-id="6daa6-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="6daa6-117">Это равнозначно ограничению уникальности в схеме, где `PrimaryKey="true"`.</span><span class="sxs-lookup"><span data-stu-id="6daa6-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="6daa6-118">В следующем примере схемы **ключевой** элемент определяет ключевое ограничение элемента **CustomerID.**</span><span class="sxs-lookup"><span data-stu-id="6daa6-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="6daa6-119">**Ключевой** элемент определяет, что значения элемента **CustomerID** ребенка **элемента Клиентов** должны иметь уникальные значения и не могут иметь нулевые значения.</span><span class="sxs-lookup"><span data-stu-id="6daa6-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="6daa6-120">При преобразовании схемы XSD процесс сопоставления создает следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="6daa6-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="6daa6-121">Отображение XML Schema также создает **UniqueConstraint** на столбце <xref:System.Data.DataSet> **CustomerID,** как показано в следующем.</span><span class="sxs-lookup"><span data-stu-id="6daa6-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6daa6-122">(Для простоты показаны только значимые свойства.)</span><span class="sxs-lookup"><span data-stu-id="6daa6-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="6daa6-123">В генерируемом **DataSet** свойство **IsPrimaryKey** **UniqueConstraint** верно, **поскольку** схема определяется `msdata:PrimaryKey="true"` в **ключевом** элементе.</span><span class="sxs-lookup"><span data-stu-id="6daa6-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="6daa6-124">Значение свойства **ConstraintName** **UniqueConstraint** в **DataSet** — это значение атрибута **msdata:ConstraintName,** указанного в **ключевом** элементе схемы.</span><span class="sxs-lookup"><span data-stu-id="6daa6-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6daa6-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6daa6-125">See also</span></span>

- [<span data-ttu-id="6daa6-126">Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных</span><span class="sxs-lookup"><span data-stu-id="6daa6-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="6daa6-127">Создание отношений наборов данных из схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6daa6-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="6daa6-128">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6daa6-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
