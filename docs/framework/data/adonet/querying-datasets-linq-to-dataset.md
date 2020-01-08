---
title: Запросы к наборам данных (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634785"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="772b9-102">Запросы к наборам данных (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="772b9-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="772b9-103">После того как в объекте <xref:System.Data.DataSet> появятся данные, к нему можно выполнять запросы.</span><span class="sxs-lookup"><span data-stu-id="772b9-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="772b9-104">Запросы составления с LINQ to DataSet аналогичны использованию запросов LINQ к другим источникам данных, поддерживающим LINQ.</span><span class="sxs-lookup"><span data-stu-id="772b9-104">Formulating queries with LINQ to DataSet is similar to using Language-Integrated Query (LINQ) against other LINQ-enabled data sources.</span></span> <span data-ttu-id="772b9-105">Однако помните, что при использовании запросов LINQ через объект <xref:System.Data.DataSet> выполняется запрос перечисления <xref:System.Data.DataRow> объектов вместо перечисления настраиваемого типа.</span><span class="sxs-lookup"><span data-stu-id="772b9-105">Remember, however, that when you use LINQ queries over a <xref:System.Data.DataSet> object, you're querying an enumeration of <xref:System.Data.DataRow> objects instead of an enumeration of a custom type.</span></span> <span data-ttu-id="772b9-106">Это означает, что вы можете использовать любой из членов класса <xref:System.Data.DataRow> в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="772b9-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your LINQ queries.</span></span> <span data-ttu-id="772b9-107">Это позволяет создавать сложные сложных запросы.</span><span class="sxs-lookup"><span data-stu-id="772b9-107">This lets you create rich, complex queries.</span></span>  
  
 <span data-ttu-id="772b9-108">Как и в других реализациях LINQ, запросы LINQ to DataSet можно создавать в двух разных формах: синтаксис выражений запроса и синтаксис запросов на основе методов.</span><span class="sxs-lookup"><span data-stu-id="772b9-108">As with other implementations of LINQ, you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="772b9-109">Синтаксис выражений запросов или синтаксис запросов на основе методов можно использовать для выполнения запросов к отдельным таблицам в <xref:System.Data.DataSet>, к нескольким таблицам в <xref:System.Data.DataSet> или к таблицам в типизированном <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="772b9-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="772b9-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="772b9-110">In This Section</span></span>  
 [<span data-ttu-id="772b9-111">Запросы к одной таблице</span><span class="sxs-lookup"><span data-stu-id="772b9-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="772b9-112">Описывается выполнение запросов к отдельным таблицам.</span><span class="sxs-lookup"><span data-stu-id="772b9-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="772b9-113">Запросы между таблицами</span><span class="sxs-lookup"><span data-stu-id="772b9-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="772b9-114">Описывается выполнение межтабличных запросов.</span><span class="sxs-lookup"><span data-stu-id="772b9-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="772b9-115">Запрос к типизированным объектам DataSet</span><span class="sxs-lookup"><span data-stu-id="772b9-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="772b9-116">Описываются запросы к типизированным объектам <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="772b9-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772b9-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="772b9-117">See also</span></span>

- [<span data-ttu-id="772b9-118">Примеры LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="772b9-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="772b9-119">Загрузка данных в DataSet</span><span class="sxs-lookup"><span data-stu-id="772b9-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
