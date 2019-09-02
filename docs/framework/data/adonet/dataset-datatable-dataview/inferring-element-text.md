---
title: Определение текста элемента
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203532"
---
# <a name="inferring-element-text"></a><span data-ttu-id="d1b43-102">Определение текста элемента</span><span class="sxs-lookup"><span data-stu-id="d1b43-102">Inferring Element Text</span></span>
<span data-ttu-id="d1b43-103">Если элемент содержит текст и не имеет дочерних элементов, которые должны выводиться как таблицы (например, элементы с атрибутами или повторяющиеся элементы), в таблицу, выводимую для элемента, будет добавлен новый столбец с именем **TableName_Text** .</span><span class="sxs-lookup"><span data-stu-id="d1b43-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="d1b43-104">Текст, содержащийся в элементе, будет добавлен в строку таблицы и сохранен в новом столбце.</span><span class="sxs-lookup"><span data-stu-id="d1b43-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="d1b43-105">Свойству **ColumnMapping** нового столбца будет присвоено значение **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="d1b43-106">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="d1b43-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d1b43-107">В процессе вывода создается таблица с именем **Element1** с двумя столбцами: **attr1** и **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="d1b43-108">Свойству **ColumnMapping** столбца **attr1** будет присвоено значение **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="d1b43-109">Свойству **ColumnMapping** столбца **Element1_Text** будет присвоено значение **MappingType. SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="d1b43-110">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d1b43-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d1b43-111">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="d1b43-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d1b43-112">attr1</span><span class="sxs-lookup"><span data-stu-id="d1b43-112">attr1</span></span>|<span data-ttu-id="d1b43-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="d1b43-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="d1b43-114">value1</span><span class="sxs-lookup"><span data-stu-id="d1b43-114">value1</span></span>|<span data-ttu-id="d1b43-115">Text1</span><span class="sxs-lookup"><span data-stu-id="d1b43-115">Text1</span></span>|  
  
 <span data-ttu-id="d1b43-116">Если элемент содержит текст, а также имеет дочерние элементы, содержащие текст, столбец не будет добавлен в таблицу для хранения текста, содержащегося в элементе.</span><span class="sxs-lookup"><span data-stu-id="d1b43-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="d1b43-117">Текст, содержащийся в элементе, пропускается, а текст в дочерних элементах включается в строку таблицы.</span><span class="sxs-lookup"><span data-stu-id="d1b43-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="d1b43-118">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="d1b43-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="d1b43-119">В процессе вывода создается таблица с именем **Element1** с одним столбцом с именем **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="d1b43-120">Текст элемента **ChildElement1** будет включаться в строку таблицы.</span><span class="sxs-lookup"><span data-stu-id="d1b43-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="d1b43-121">Весь прочий текст будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="d1b43-121">The other text will be ignored.</span></span> <span data-ttu-id="d1b43-122">Свойству **ColumnMapping** столбца **ChildElement1** будет присвоено значение **MappingType. element**.</span><span class="sxs-lookup"><span data-stu-id="d1b43-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="d1b43-123">**Объекте** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d1b43-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d1b43-124">**Таблица** Element1</span><span class="sxs-lookup"><span data-stu-id="d1b43-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d1b43-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d1b43-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="d1b43-126">Text2</span><span class="sxs-lookup"><span data-stu-id="d1b43-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1b43-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d1b43-127">See also</span></span>

- [<span data-ttu-id="d1b43-128">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="d1b43-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="d1b43-129">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="d1b43-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="d1b43-130">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="d1b43-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="d1b43-131">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="d1b43-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="d1b43-132">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="d1b43-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="d1b43-133">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d1b43-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
