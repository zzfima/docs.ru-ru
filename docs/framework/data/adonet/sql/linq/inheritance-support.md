---
title: Поддержка наследования
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 668f4f1dd284550e644ce6b8a4491ca47105575e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033557"
---
# <a name="inheritance-support"></a><span data-ttu-id="633ba-102">Поддержка наследования</span><span class="sxs-lookup"><span data-stu-id="633ba-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="633ba-103">поддерживает *однотабличное сопоставление*.</span><span class="sxs-lookup"><span data-stu-id="633ba-103">supports *single-table mapping*.</span></span> <span data-ttu-id="633ba-104">Другими словами, в одной таблице базы данных хранится полная иерархия наследования.</span><span class="sxs-lookup"><span data-stu-id="633ba-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="633ba-105">Таблица содержит плоское объединение всех возможных столбцов данных для всей иерархии.</span><span class="sxs-lookup"><span data-stu-id="633ba-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="633ba-106">(Объединение является результатом сочетания двух таблиц в одной, в которой имеются строки любой из исходных таблиц.) Каждая строка в столбцах содержит значения NULL, которые не применяются к типу экземпляра, представленного строкой.</span><span class="sxs-lookup"><span data-stu-id="633ba-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="633ba-107">Стратегия однотабличного сопоставления представляет собой простейшее представление наследования и обеспечивает высокую производительность для многих различных категорий запросов.</span><span class="sxs-lookup"><span data-stu-id="633ba-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="633ba-108">Чтобы реализовать данное сопоставление в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов.</span><span class="sxs-lookup"><span data-stu-id="633ba-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="633ba-109">Дополнительные сведения см. в разделе [Как Сопоставление иерархий наследования](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="633ba-109">For more information, see [How to: Map Inheritance Hierarchies](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="633ba-110">Разработчики, использующие Visual Studio можно также использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] сопоставить иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="633ba-110">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633ba-111">См. также</span><span class="sxs-lookup"><span data-stu-id="633ba-111">See also</span></span>

- [<span data-ttu-id="633ba-112">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="633ba-112">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
