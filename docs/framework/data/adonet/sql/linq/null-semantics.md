---
title: Семантика NULL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a><span data-ttu-id="bfaad-102">Семантика NULL</span><span class="sxs-lookup"><span data-stu-id="bfaad-102">Null Semantics</span></span>
<span data-ttu-id="bfaad-103">В следующей таблице приведены ссылки на различные части [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации где `null` (`Nothing` в Visual Basic) рассматриваются проблемы.</span><span class="sxs-lookup"><span data-stu-id="bfaad-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="bfaad-104">Раздел</span><span class="sxs-lookup"><span data-stu-id="bfaad-104">Topic</span></span>|<span data-ttu-id="bfaad-105">Описание</span><span class="sxs-lookup"><span data-stu-id="bfaad-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bfaad-106">Несоответствия типов SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="bfaad-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="bfaad-107">В разделе «Семантика со значениями Null» данного раздела рассматриваются три состояния SQL логическое сравнение двух состояний общеязыковая среда выполнения (CLR) <xref:System.Boolean>, литерал `Nothing` (Visual Basic) и `null` (C#) и другие аналогичные проблемы.</span><span class="sxs-lookup"><span data-stu-id="bfaad-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="bfaad-108">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="bfaad-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="bfaad-109">В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfaad-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="bfaad-110">Методы System.String</span><span class="sxs-lookup"><span data-stu-id="bfaad-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="bfaad-111">В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.</span><span class="sxs-lookup"><span data-stu-id="bfaad-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="bfaad-112">Вычисление суммы значений числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="bfaad-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="bfaad-113">Описывает способ <xref:System.Linq.Enumerable.Sum%2A> оператор, результатом которого является `null` (`Nothing` в Visual Basic) вместо 0 для пустой последовательности или последовательности, содержащей только значения NULL.</span><span class="sxs-lookup"><span data-stu-id="bfaad-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfaad-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bfaad-114">See Also</span></span>  
 [<span data-ttu-id="bfaad-115">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="bfaad-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
