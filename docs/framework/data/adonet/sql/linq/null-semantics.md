---
title: "Семантика NULL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6786c7ea4441b1a753d6f0b4213f40fa64dcb4ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="null-semantics"></a><span data-ttu-id="bb9a4-102">Семантика NULL</span><span class="sxs-lookup"><span data-stu-id="bb9a4-102">Null Semantics</span></span>
<span data-ttu-id="bb9a4-103">В следующей таблице приведены ссылки на различные части документации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , в которых обсуждаются проблемы, связанные со значением `null` (`Nothing` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="bb9a4-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="bb9a4-104">Раздел</span><span class="sxs-lookup"><span data-stu-id="bb9a4-104">Topic</span></span>|<span data-ttu-id="bb9a4-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb9a4-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bb9a4-106">Несоответствия типов SQL-CLR</span><span class="sxs-lookup"><span data-stu-id="bb9a4-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="bb9a4-107">В подразделе "Семантика со значениями NULL" данного раздела сравнивается тип значений SQL "Boolean", принимающий три состояния, с типом значения среды CLR <xref:System.Boolean>, принимающим два состояния, литералом `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) и `null` (C#) и рассматриваются другие аналогичные проблемы.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="bb9a4-108">Преобразование стандартных операторов запросов</span><span class="sxs-lookup"><span data-stu-id="bb9a4-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="bb9a4-109">В подразделе "Семантика со значениями NULL" данного раздела описывается семантика сравнений со значением NULL в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb9a4-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="bb9a4-110">Методы System.String</span><span class="sxs-lookup"><span data-stu-id="bb9a4-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="bb9a4-111">В подразделе "Отличия от платформы .NET" данного раздела описывается, каким образом значение 0, возвращенное методом <xref:System.String.LastIndexOf%2A> , может означать, что строка равна значению NULL либо найденная позиция равна 0.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="bb9a4-112">Вычисление суммы значений числовой последовательности</span><span class="sxs-lookup"><span data-stu-id="bb9a4-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="bb9a4-113">Описывается, как оператор <xref:System.Linq.Enumerable.Sum%2A> выполняет сравнение со значением `null` (`Nothing` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) вместо 0 для последовательности, содержащей только значения NULL, или пустой последовательности.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb9a4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bb9a4-114">See Also</span></span>  
 [<span data-ttu-id="bb9a4-115">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="bb9a4-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
