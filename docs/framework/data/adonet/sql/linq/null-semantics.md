---
title: Семантика NULL
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: d0b18c0a699840d11f5e4add05147672f9bb69e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792978"
---
# <a name="null-semantics"></a><span data-ttu-id="27d5e-102">Семантика NULL</span><span class="sxs-lookup"><span data-stu-id="27d5e-102">Null Semantics</span></span>
<span data-ttu-id="27d5e-103">В следующей таблице приведены ссылки на различные части [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации, где `null` обсуждаются`Nothing` проблемы (в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="27d5e-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="27d5e-104">Раздел</span><span class="sxs-lookup"><span data-stu-id="27d5e-104">Topic</span></span>|<span data-ttu-id="27d5e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="27d5e-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="27d5e-106">Несоответствия типов SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="27d5e-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="27d5e-107">В подразделе "семантика со значениями NULL" <xref:System.Boolean>этого раздела содержится обсуждение логического состояния SQL, основанного на трех и двух состоянийх, литерал `Nothing` (Visual Basic) и `null` (C#) и другие аналогичные проблем.</span><span class="sxs-lookup"><span data-stu-id="27d5e-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="27d5e-108">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="27d5e-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="27d5e-109">В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27d5e-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="27d5e-110">Методы System.String</span><span class="sxs-lookup"><span data-stu-id="27d5e-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="27d5e-111">В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.</span><span class="sxs-lookup"><span data-stu-id="27d5e-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="27d5e-112">Вычисление суммы значений числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="27d5e-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="27d5e-113">Описывает, как <xref:System.Linq.Enumerable.Sum%2A> оператор вычисляет `null` значение (`Nothing` в Visual Basic) вместо 0 для последовательности, содержащей только значения NULL или для пустой последовательности.</span><span class="sxs-lookup"><span data-stu-id="27d5e-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27d5e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="27d5e-114">See also</span></span>

- [<span data-ttu-id="27d5e-115">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="27d5e-115">Data Types and Functions</span></span>](data-types-and-functions.md)
