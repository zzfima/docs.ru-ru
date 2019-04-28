---
title: Пользовательские функции
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: f1222d9332d365c9c3c6ca2aa28cbb48e92c04e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917674"
---
# <a name="user-defined-functions"></a><span data-ttu-id="e8283-102">Пользовательские функции</span><span class="sxs-lookup"><span data-stu-id="e8283-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e8283-103">использует методы в объектной модели для представления пользовательских функций.</span><span class="sxs-lookup"><span data-stu-id="e8283-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="e8283-104">Чтобы назначить методы в качестве функций, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>, а где необходимо - атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e8283-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="e8283-105">Дополнительные сведения см. в разделе [LINQ to SQL объектной модели](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="e8283-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="e8283-106">Чтобы избежать <xref:System.InvalidOperationException>, пользовательские функции в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] должны быть представлены в одной из следующих форм.</span><span class="sxs-lookup"><span data-stu-id="e8283-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="e8283-107">Функция, упакованная в качестве вызова метода с правильными атрибутами сопоставления.</span><span class="sxs-lookup"><span data-stu-id="e8283-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="e8283-108">Дополнительные сведения см. в разделе [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="e8283-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="e8283-109">Статический метод SQL, характерный для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8283-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="e8283-110">Функция, поддерживаемая методом [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8283-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="e8283-111">В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.</span><span class="sxs-lookup"><span data-stu-id="e8283-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="e8283-112">Разработчики, использующие Visual Studio обычно используется [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления определяемых пользователем функций.</span><span class="sxs-lookup"><span data-stu-id="e8283-112">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8283-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e8283-113">In This Section</span></span>  
 [<span data-ttu-id="e8283-114">Практическое руководство. Используйте скалярные определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="e8283-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="e8283-115">Описано, как реализовать функцию, возвращающую скалярные значения.</span><span class="sxs-lookup"><span data-stu-id="e8283-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="e8283-116">Практическое руководство. Использование возвращающих табличные значения определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="e8283-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="e8283-117">Содержит описание способов реализации функции, возвращающей табличные значения.</span><span class="sxs-lookup"><span data-stu-id="e8283-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="e8283-118">Практическое руководство. Вызывать встроенные определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="e8283-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="e8283-119">Содержит описание преобразования встроенных вызовов в функции и представляет различия при внутреннем осуществлении вызова.</span><span class="sxs-lookup"><span data-stu-id="e8283-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
