---
title: Определение текста элемента
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: b32d8f3f89a16166ffc0e903ef1f63c3b97a249c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="inferring-element-text"></a><span data-ttu-id="f9283-102">Определение текста элемента</span><span class="sxs-lookup"><span data-stu-id="f9283-102">Inferring Element Text</span></span>
<span data-ttu-id="f9283-103">Если элемент содержит текст и не имеет дочерних элементов был определен как таблицы, например (элементы с атрибутами) или повторяющимися элементами, новый столбец с именем **TableName_Text** будет добавлен к таблице, выводящейся для элемента.</span><span class="sxs-lookup"><span data-stu-id="f9283-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="f9283-104">Текст, содержащийся в элементе, будет добавлен в строку таблицы и сохранен в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="f9283-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="f9283-105">**ColumnMapping** свойства нового столбца будет присвоено **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="f9283-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="f9283-106">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="f9283-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f9283-107">Процесс вывода сформирует таблицу с именем **Element1** с двумя столбцами: **attr1** и **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="f9283-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="f9283-108">**ColumnMapping** свойство **attr1** столбца будет присвоено **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="f9283-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="f9283-109">**ColumnMapping** свойство **Element1_Text** столбца будет присвоено **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="f9283-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="f9283-110">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f9283-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f9283-111">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="f9283-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f9283-112">attr1</span><span class="sxs-lookup"><span data-stu-id="f9283-112">attr1</span></span>|<span data-ttu-id="f9283-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f9283-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="f9283-114">value1</span><span class="sxs-lookup"><span data-stu-id="f9283-114">value1</span></span>|<span data-ttu-id="f9283-115">Text1</span><span class="sxs-lookup"><span data-stu-id="f9283-115">Text1</span></span>|  
  
 <span data-ttu-id="f9283-116">Если элемент содержит текст, а также имеет дочерние элементы, содержащие текст, столбец не будет добавлен в таблицу для хранения текста, содержащегося в элементе.</span><span class="sxs-lookup"><span data-stu-id="f9283-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="f9283-117">Текст, содержащийся в элементе, пропускается, а текст в дочерних элементах включается в строку таблицы.</span><span class="sxs-lookup"><span data-stu-id="f9283-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="f9283-118">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="f9283-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="f9283-119">Процесс вывода сформирует таблицу с именем **Element1** с одним столбцом с именем **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="f9283-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="f9283-120">Текст для **ChildElement1** элемент будет включен в строку в таблице.</span><span class="sxs-lookup"><span data-stu-id="f9283-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="f9283-121">Весь прочий текст будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="f9283-121">The other text will be ignored.</span></span> <span data-ttu-id="f9283-122">**ColumnMapping** свойство **ChildElement1** столбца будет присвоено **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="f9283-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="f9283-123">**Набор данных:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f9283-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f9283-124">**Таблица:** Element1</span><span class="sxs-lookup"><span data-stu-id="f9283-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f9283-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f9283-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="f9283-126">Text2</span><span class="sxs-lookup"><span data-stu-id="f9283-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9283-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f9283-127">See Also</span></span>  
 [<span data-ttu-id="f9283-128">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="f9283-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="f9283-129">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="f9283-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="f9283-130">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="f9283-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="f9283-131">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="f9283-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="f9283-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="f9283-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="f9283-133">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9283-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
