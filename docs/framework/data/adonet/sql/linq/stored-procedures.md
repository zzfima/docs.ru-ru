---
title: Хранимые процедуры
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 9201965192f300de62679c1e5be75cf98a24e700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917947"
---
# <a name="stored-procedures"></a><span data-ttu-id="3c3ab-102">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="3c3ab-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3c3ab-103">использует методы в объектной модели для представления хранимых процедур в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="3c3ab-104">Чтобы задать методы в качестве хранимых процедур, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute> и, где необходимо, атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="3c3ab-105">Дополнительные сведения см. в разделе [LINQ to SQL объектной модели](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="3c3ab-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="3c3ab-106">Разработчики, использующие Visual Studio обычно используется [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-106">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="3c3ab-107">В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c3ab-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3c3ab-108">In This Section</span></span>  
 [<span data-ttu-id="3c3ab-109">Практическое руководство. Возврат наборов строк</span><span class="sxs-lookup"><span data-stu-id="3c3ab-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="3c3ab-110">Содержит сведения о возвращении строк данных и об использовании входного параметра.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="3c3ab-111">Практическое руководство. Использование хранимых процедур, принимающих параметры</span><span class="sxs-lookup"><span data-stu-id="3c3ab-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="3c3ab-112">Содержит сведения об использовании входных и выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="3c3ab-113">Практическое руководство. Использовать хранимые процедуры, сопоставленные с несколькими результирующими формами</span><span class="sxs-lookup"><span data-stu-id="3c3ab-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="3c3ab-114">Содержит сведения о предоставлении возвратов нескольких фигур в одной хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="3c3ab-115">Практическое руководство. Использовать хранимые процедуры, сопоставленные с последовательными результирующими формами</span><span class="sxs-lookup"><span data-stu-id="3c3ab-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="3c3ab-116">Содержит сведения о предоставлении нескольких фигур при наличии известной возвращаемой последовательности.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="3c3ab-117">Настройка операций за счет хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="3c3ab-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="3c3ab-118">Содержит описание использования хранимых процедур для выполнения операций вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="3c3ab-119">Настройка операций за счет исключительного использования хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="3c3ab-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="3c3ab-120">Содержит описание использования только хранимых процедур для выполнения операций вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c3ab-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3c3ab-121">Related Sections</span></span>  
 [<span data-ttu-id="3c3ab-122">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="3c3ab-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="3c3ab-123">Содержит сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c3ab-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="3c3ab-124">Пошаговое руководство: Применение только хранимых процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c3ab-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="3c3ab-125">Содержит процедуры, в которых показано использование хранимых процедур в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="3c3ab-126">Пошаговое руководство: Применение только хранимых процедур (C#)</span><span class="sxs-lookup"><span data-stu-id="3c3ab-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="3c3ab-127">Содержит процедуры, в которых показано использование хранимых процедур в C#.</span><span class="sxs-lookup"><span data-stu-id="3c3ab-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
