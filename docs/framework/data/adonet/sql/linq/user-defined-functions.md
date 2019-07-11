---
title: Пользовательские функции
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742713"
---
# <a name="user-defined-functions"></a><span data-ttu-id="b5bad-102">Пользовательские функции</span><span class="sxs-lookup"><span data-stu-id="b5bad-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b5bad-103">использует методы в объектной модели для представления пользовательских функций.</span><span class="sxs-lookup"><span data-stu-id="b5bad-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="b5bad-104">Чтобы назначить методы в качестве функций, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>, а где необходимо - атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5bad-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="b5bad-105">Дополнительные сведения см. в разделе [LINQ to SQL объектной модели](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="b5bad-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="b5bad-106">Чтобы избежать <xref:System.InvalidOperationException>, пользовательские функции в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] должны быть представлены в одной из следующих форм.</span><span class="sxs-lookup"><span data-stu-id="b5bad-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="b5bad-107">Функция, упакованная в качестве вызова метода с правильными атрибутами сопоставления.</span><span class="sxs-lookup"><span data-stu-id="b5bad-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="b5bad-108">Дополнительные сведения см. в разделе [сопоставление, основанное на атрибутах](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b5bad-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="b5bad-109">Статический метод SQL, характерный для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5bad-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="b5bad-110">Функция, поддерживаемая методом .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5bad-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="b5bad-111">В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.</span><span class="sxs-lookup"><span data-stu-id="b5bad-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="b5bad-112">Разработчики, использующие Visual Studio обычно используется для сопоставления определяемых пользователем функций реляционного конструктора объектов.</span><span class="sxs-lookup"><span data-stu-id="b5bad-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5bad-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b5bad-113">In This Section</span></span>  
 [<span data-ttu-id="b5bad-114">Практическое руководство. Используйте скалярные определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="b5bad-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="b5bad-115">Описано, как реализовать функцию, возвращающую скалярные значения.</span><span class="sxs-lookup"><span data-stu-id="b5bad-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="b5bad-116">Практическое руководство. Использование возвращающих табличные значения определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="b5bad-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="b5bad-117">Содержит описание способов реализации функции, возвращающей табличные значения.</span><span class="sxs-lookup"><span data-stu-id="b5bad-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="b5bad-118">Практическое руководство. Вызывать встроенные определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="b5bad-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="b5bad-119">Содержит описание преобразования встроенных вызовов в функции и представляет различия при внутреннем осуществлении вызова.</span><span class="sxs-lookup"><span data-stu-id="b5bad-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
