---
title: Поддержка наследования
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781563"
---
# <a name="inheritance-support"></a><span data-ttu-id="f86c7-102">Поддержка наследования</span><span class="sxs-lookup"><span data-stu-id="f86c7-102">Inheritance Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="f86c7-103">поддерживает *однотабличное сопоставление*.</span><span class="sxs-lookup"><span data-stu-id="f86c7-103">supports *single-table mapping*.</span></span> <span data-ttu-id="f86c7-104">Другими словами, в одной таблице базы данных хранится полная иерархия наследования.</span><span class="sxs-lookup"><span data-stu-id="f86c7-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="f86c7-105">Таблица содержит плоское объединение всех возможных столбцов данных для всей иерархии.</span><span class="sxs-lookup"><span data-stu-id="f86c7-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="f86c7-106">(Объединение является результатом сочетания двух таблиц в одной, в которой имеются строки любой из исходных таблиц.) Каждая строка в столбцах содержит значения NULL, которые не применяются к типу экземпляра, представленного строкой.</span><span class="sxs-lookup"><span data-stu-id="f86c7-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="f86c7-107">Стратегия однотабличного сопоставления представляет собой простейшее представление наследования и обеспечивает высокую производительность для многих различных категорий запросов.</span><span class="sxs-lookup"><span data-stu-id="f86c7-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="f86c7-108">Чтобы реализовать данное сопоставление в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f86c7-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="f86c7-109">Дополнительные сведения см. в разделе [Практическое руководство. Иерархия наследования](how-to-map-inheritance-hierarchies.md)карт.</span><span class="sxs-lookup"><span data-stu-id="f86c7-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="f86c7-110">Разработчики, использующие Visual Studio, также могут использовать реляционный конструктор объектов для отображения иерархий наследования.</span><span class="sxs-lookup"><span data-stu-id="f86c7-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86c7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f86c7-111">See also</span></span>

- [<span data-ttu-id="f86c7-112">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="f86c7-112">Background Information</span></span>](background-information.md)
