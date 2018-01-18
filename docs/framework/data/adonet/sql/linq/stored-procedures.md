---
title: "Хранимые процедуры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cff3103595ccb782e2e51313d427259c0191105d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="stored-procedures"></a><span data-ttu-id="32a55-102">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="32a55-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="32a55-103">использует методы в объектной модели для представления хранимых процедур в базе данных.</span><span class="sxs-lookup"><span data-stu-id="32a55-103"> uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="32a55-104">Чтобы задать методы в качестве хранимых процедур, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute> и, где необходимо, атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="32a55-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="32a55-105">Дополнительные сведения см. в разделе [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="32a55-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="32a55-106">Разработчики, использующие [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] обычно используется [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="32a55-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="32a55-107">В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.</span><span class="sxs-lookup"><span data-stu-id="32a55-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32a55-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="32a55-108">In This Section</span></span>  
 [<span data-ttu-id="32a55-109">Практическое руководство. Возврат наборов строк</span><span class="sxs-lookup"><span data-stu-id="32a55-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="32a55-110">Содержит сведения о возвращении строк данных и об использовании входного параметра.</span><span class="sxs-lookup"><span data-stu-id="32a55-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="32a55-111">Практическое руководство. Использование хранимых процедур, принимающих параметры</span><span class="sxs-lookup"><span data-stu-id="32a55-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="32a55-112">Содержит сведения об использовании входных и выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="32a55-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="32a55-113">Практическое руководство. Использование хранимых процедур, сопоставленных для нескольких форм результатов</span><span class="sxs-lookup"><span data-stu-id="32a55-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="32a55-114">Содержит сведения о предоставлении возвратов нескольких фигур в одной хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="32a55-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="32a55-115">Практическое руководство. Использование хранимых процедур, сопоставленных для последовательных форм результатов</span><span class="sxs-lookup"><span data-stu-id="32a55-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="32a55-116">Содержит сведения о предоставлении нескольких фигур при наличии известной возвращаемой последовательности.</span><span class="sxs-lookup"><span data-stu-id="32a55-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="32a55-117">Настройка операций за счет хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="32a55-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="32a55-118">Содержит описание использования хранимых процедур для выполнения операций вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="32a55-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="32a55-119">Настройка операций за счет исключительного использования хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="32a55-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="32a55-120">Содержит описание использования только хранимых процедур для выполнения операций вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="32a55-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="32a55-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="32a55-121">Related Sections</span></span>  
 [<span data-ttu-id="32a55-122">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="32a55-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="32a55-123">Содержит сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32a55-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="32a55-124">Пошаговое руководство. Использование только хранимых процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32a55-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="32a55-125">Содержит процедуры, в которых показано использование хранимых процедур в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="32a55-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="32a55-126">Пошаговое руководство. Применение только хранимых процедур (C#)</span><span class="sxs-lookup"><span data-stu-id="32a55-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="32a55-127">Содержит процедуры, в которых показано использование хранимых процедур в C#.</span><span class="sxs-lookup"><span data-stu-id="32a55-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
