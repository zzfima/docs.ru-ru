---
title: Общие сведения о процессе определения схемы набора данных
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 5266d08212e5259bd5b242a70d61e29ad9008006
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203248"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="28d32-102">Общие сведения о процессе определения схемы набора данных</span><span class="sxs-lookup"><span data-stu-id="28d32-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="28d32-103">Процесс вывода схемы из XML-документа вначале определяет, какие элементы будут выведены как таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d32-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="28d32-104">Из оставшегося XML процесс вывода схемы определяет столбцы этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="28d32-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="28d32-105">Для вложенных таблиц процесс вывода формирует вложенные объекты <xref:System.Data.DataRelation> и <xref:System.Data.ForeignKeyConstraint>.</span><span class="sxs-lookup"><span data-stu-id="28d32-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="28d32-106">Далее представлена краткая сводка правил вывода.</span><span class="sxs-lookup"><span data-stu-id="28d32-106">Following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="28d32-107">Элементы с атрибутами выводятся как таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d32-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="28d32-108">Элементы, имеющие дочерние элементы, выводятся как таблицы.</span><span class="sxs-lookup"><span data-stu-id="28d32-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="28d32-109">Повторяющиеся элементы выводятся как одна таблица.</span><span class="sxs-lookup"><span data-stu-id="28d32-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="28d32-110">Если элемент документа (корневой элемент) не имеет ни атрибутов, ни дочерних элементов, которые выводились бы как столбцы, он выводится как <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="28d32-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="28d32-111">В противном случае элемент документа выводится как таблица.</span><span class="sxs-lookup"><span data-stu-id="28d32-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="28d32-112">Атрибуты выводятся как столбцы.</span><span class="sxs-lookup"><span data-stu-id="28d32-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="28d32-113">Элементы, которые не повторяются и не имеют ни атрибутов, ни дочерних элементов, выводятся как столбцы.</span><span class="sxs-lookup"><span data-stu-id="28d32-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="28d32-114">Для элементов, которые выводятся в виде вложенных таблиц в других элементах, которые также выводятся в виде таблиц, между двумя таблицами создается вложенная **связь DataRelation** .</span><span class="sxs-lookup"><span data-stu-id="28d32-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="28d32-115">Новый первичный ключевой столбец с именем **TableName_Id** добавляется в обе таблицы и используется **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="28d32-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="28d32-116">Объект **ForeignKeyConstraint** создается между двумя таблицами с помощью столбца **TableName_Id** .</span><span class="sxs-lookup"><span data-stu-id="28d32-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="28d32-117">Для элементов, которые выводятся в виде таблиц и содержат текст, но не имеют дочерних элементов, для текста каждого элемента создается новый столбец с именем **TableName_Text** .</span><span class="sxs-lookup"><span data-stu-id="28d32-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="28d32-118">Если элемент выводится как таблица и имеет текст, но при этом имеет дочерние элементы, текст пропускается.</span><span class="sxs-lookup"><span data-stu-id="28d32-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d32-119">См. также</span><span class="sxs-lookup"><span data-stu-id="28d32-119">See also</span></span>

- [<span data-ttu-id="28d32-120">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="28d32-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="28d32-121">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="28d32-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="28d32-122">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="28d32-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="28d32-123">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="28d32-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="28d32-124">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="28d32-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="28d32-125">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28d32-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
