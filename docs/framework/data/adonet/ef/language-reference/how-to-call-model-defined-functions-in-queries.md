---
title: "Практическое руководство. Вызов определенных моделью функций в запросах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 179c00def6b5a810806d536a8728cbbc544b1084
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="c4f45-102">Практическое руководство. Вызов определенных моделью функций в запросах</span><span class="sxs-lookup"><span data-stu-id="c4f45-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="c4f45-103">В этом разделе описаны процедуры вызова функций, определенные в концептуальной модели, из запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f45-103">This topic describes how to call functions that are defined in the conceptual model from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="c4f45-104">Приведенная ниже процедура обеспечивает высокоуровневую структуру для вызова функции, определяемой моделью, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f45-104">The procedure below provides a high-level outline for calling a model-defined function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="c4f45-105">В следующем примере подробно описаны шаги данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="c4f45-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="c4f45-106">Для этой процедуры предполагается, что функция была определена в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="c4f45-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="c4f45-107">Дополнительные сведения см. в разделе [как: определение пользовательских функций в концептуальной модели](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span><span class="sxs-lookup"><span data-stu-id="c4f45-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="c4f45-108">Вызов функции, определенной в концептуальной модели</span><span class="sxs-lookup"><span data-stu-id="c4f45-108">To call a function defined in the conceptual model</span></span>  
  
1.  <span data-ttu-id="c4f45-109">Добавьте в приложение метод среды CLR, который сопоставляется с функцией, определенной в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="c4f45-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="c4f45-110">Для сопоставления метода к нему необходимо применить атрибут <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c4f45-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="c4f45-111">Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.</span><span class="sxs-lookup"><span data-stu-id="c4f45-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="c4f45-112">При разрешении имени функции для LINQ учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c4f45-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2.  <span data-ttu-id="c4f45-113">Вызовите функцию в запросе [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f45-113">Call the function in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4f45-114">Пример</span><span class="sxs-lookup"><span data-stu-id="c4f45-114">Example</span></span>  
 <span data-ttu-id="c4f45-115">В следующем примере показано, как вызвать функцию, определенную в концептуальной модели, из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f45-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="c4f45-116">В этом примере используется модель School.</span><span class="sxs-lookup"><span data-stu-id="c4f45-116">The example uses the School model.</span></span> <span data-ttu-id="c4f45-117">Сведения о модели School см. в разделе [Создание образца базы данных School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) и [Создание EDMX-файла School файл](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="c4f45-117">For information about the School model, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="c4f45-118">В следующей концептуальной модели функция возвращает сведения о количестве лет, истекших с момента приема инструктора на работу.</span><span class="sxs-lookup"><span data-stu-id="c4f45-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="c4f45-119">Сведения о добавлении функции к концептуальной модели см. в разделе [как: определение пользовательских функций в концептуальной модели](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span><span class="sxs-lookup"><span data-stu-id="c4f45-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="c4f45-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c4f45-120">Example</span></span>  
 <span data-ttu-id="c4f45-121">Затем добавьте в приложение следующий метод и с помощью атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> сопоставьте его с функцией концептуальной модели:</span><span class="sxs-lookup"><span data-stu-id="c4f45-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="c4f45-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c4f45-122">Example</span></span>  
 <span data-ttu-id="c4f45-123">Теперь можно вызвать функцию концептуальной модели из запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4f45-123">Now you can call the conceptual model function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="c4f45-124">Следующий код вызывает метод, чтобы отобразить всех инструкторов, которые были приняты на работу более десяти лет назад:</span><span class="sxs-lookup"><span data-stu-id="c4f45-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c4f45-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c4f45-125">See Also</span></span>  
 [<span data-ttu-id="c4f45-126">Общие сведения о файлах .edmx</span><span class="sxs-lookup"><span data-stu-id="c4f45-126">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="c4f45-127">Запросы в LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c4f45-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="c4f45-128">Вызов функций в запросах LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c4f45-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="c4f45-129">Как: вызов определенных моделью функций как методов объектов</span><span class="sxs-lookup"><span data-stu-id="c4f45-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
