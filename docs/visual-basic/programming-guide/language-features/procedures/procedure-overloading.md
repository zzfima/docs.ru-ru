---
title: "Перегрузка процедур (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65fd5a6763752c616f13891bfa5acabff6115d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="7666f-102">Перегрузка процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7666f-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="7666f-103">*Перегрузка* процедуры означает определение ее в нескольких версиях с помощью тем же именем, но различными списками параметров.</span><span class="sxs-lookup"><span data-stu-id="7666f-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="7666f-104">Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры, не различая их по имени.</span><span class="sxs-lookup"><span data-stu-id="7666f-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="7666f-105">Это делается путем изменения списка параметров.</span><span class="sxs-lookup"><span data-stu-id="7666f-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="7666f-106">Правила перегрузки</span><span class="sxs-lookup"><span data-stu-id="7666f-106">Overloading Rules</span></span>  
 <span data-ttu-id="7666f-107">При перегрузке процедур действуют следующие правила:</span><span class="sxs-lookup"><span data-stu-id="7666f-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="7666f-108">**Таким же именем**.</span><span class="sxs-lookup"><span data-stu-id="7666f-108">**Same Name**.</span></span> <span data-ttu-id="7666f-109">Каждая перегруженная версия необходимо использовать то же имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="7666f-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="7666f-110">**Сигнатура**.</span><span class="sxs-lookup"><span data-stu-id="7666f-110">**Different Signature**.</span></span> <span data-ttu-id="7666f-111">Каждая перегруженная версия должна отличаться от всех остальных перегруженных версий хотя бы один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7666f-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="7666f-112">Число параметров</span><span class="sxs-lookup"><span data-stu-id="7666f-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="7666f-113">Порядок параметров</span><span class="sxs-lookup"><span data-stu-id="7666f-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="7666f-114">Типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="7666f-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="7666f-115">Число параметров типа (для универсальной процедуры)</span><span class="sxs-lookup"><span data-stu-id="7666f-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="7666f-116">Тип возвращаемого значения (только для оператора преобразования)</span><span class="sxs-lookup"><span data-stu-id="7666f-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="7666f-117">Вместе с именем процедуры предыдущие элементы называются *подписи* процедуры.</span><span class="sxs-lookup"><span data-stu-id="7666f-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="7666f-118">При вызове перегруженной процедуры компилятор использует подпись для проверки вызова на соответствие определению.</span><span class="sxs-lookup"><span data-stu-id="7666f-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="7666f-119">**Элементы не являются частью сигнатуры**.</span><span class="sxs-lookup"><span data-stu-id="7666f-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="7666f-120">Нельзя перегрузить процедуру без изменения подписи.</span><span class="sxs-lookup"><span data-stu-id="7666f-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="7666f-121">В частности нельзя перегрузить процедуру путем изменения только один или несколько из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="7666f-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="7666f-122">Ключевые слова модификаторов процедур, таких как `Public`, `Shared`, и`Static`</span><span class="sxs-lookup"><span data-stu-id="7666f-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="7666f-123">Имена параметров для параметра или типа</span><span class="sxs-lookup"><span data-stu-id="7666f-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="7666f-124">Ограничения параметров типа (для универсальной процедуры)</span><span class="sxs-lookup"><span data-stu-id="7666f-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="7666f-125">Ключевые слова модификаторов параметров, таких как `ByRef` и`Optional`</span><span class="sxs-lookup"><span data-stu-id="7666f-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="7666f-126">Оно возвращает значение</span><span class="sxs-lookup"><span data-stu-id="7666f-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="7666f-127">Тип данных возвращаемого значения (за исключением оператора преобразования)</span><span class="sxs-lookup"><span data-stu-id="7666f-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="7666f-128">Элементы, перечисленные в списке не являются частью сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="7666f-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="7666f-129">Несмотря на то, что их нельзя использовать для различения перегруженных версий, можно изменять их для перегруженных версий, которые правильно различаются по подписи.</span><span class="sxs-lookup"><span data-stu-id="7666f-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="7666f-130">**Позднее связывание аргументов**.</span><span class="sxs-lookup"><span data-stu-id="7666f-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="7666f-131">Если требуется передать переменную объекта поздней привязкой перегруженную версию, необходимо объявить соответствующий аргумент как <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="7666f-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="7666f-132">Несколько версий процедуры</span><span class="sxs-lookup"><span data-stu-id="7666f-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="7666f-133">Предположим, что вы пишете `Sub` процедуры для учета транзакции по балансу клиента и должны быть можно ссылаться по имени или номеру учетной записи клиента.</span><span class="sxs-lookup"><span data-stu-id="7666f-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="7666f-134">Чтобы решить эту проблему, можно определить двумя разными `Sub` процедуры, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7666f-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="7666f-135">Перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="7666f-135">Overloaded Versions</span></span>  
 <span data-ttu-id="7666f-136">Альтернативой является перегрузка отдельного имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="7666f-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="7666f-137">Можно использовать [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово можно определить версии процедуры для каждого списка аргументов, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="7666f-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="7666f-138">Дополнительные перегрузки</span><span class="sxs-lookup"><span data-stu-id="7666f-138">Additional Overloads</span></span>  
 <span data-ttu-id="7666f-139">Если вы хотите принять сумму транзакции в формате `Decimal` или `Single`, определить дополнительные перегруженные версии `post` для для этих вариантов.</span><span class="sxs-lookup"><span data-stu-id="7666f-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="7666f-140">Если сделать это для каждой перегрузки, показанной в предыдущем примере, будет иметь четыре `Sub` процедуры с тем же именем, но с четырьмя разными сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="7666f-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="7666f-141">Преимущества перегрузки</span><span class="sxs-lookup"><span data-stu-id="7666f-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="7666f-142">Преимущество перегрузки процедуры заключается в гибкости вызова.</span><span class="sxs-lookup"><span data-stu-id="7666f-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="7666f-143">Для использования `post` объявление процедуры в предыдущем примере, вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем вызвать процедуру в любом случае.</span><span class="sxs-lookup"><span data-stu-id="7666f-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="7666f-144">Это показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="7666f-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7666f-145">См. также</span><span class="sxs-lookup"><span data-stu-id="7666f-145">See Also</span></span>  
 [<span data-ttu-id="7666f-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="7666f-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="7666f-147">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="7666f-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="7666f-148">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="7666f-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="7666f-149">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="7666f-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="7666f-150">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="7666f-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="7666f-151">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="7666f-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="7666f-152">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="7666f-152">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="7666f-153">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="7666f-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="7666f-154">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7666f-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
