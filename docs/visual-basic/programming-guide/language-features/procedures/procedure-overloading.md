---
title: Перегрузка процедур
ms.date: 07/20/2015
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
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352587"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="010fb-102">Перегрузка процедур (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="010fb-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="010fb-103">*Перегрузка* процедуры означает определение ее в нескольких версиях с использованием того же имени, но с разными списками параметров.</span><span class="sxs-lookup"><span data-stu-id="010fb-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="010fb-104">Целью перегрузки является определение нескольких тесно связанных версий процедуры без необходимости отличать их по имени.</span><span class="sxs-lookup"><span data-stu-id="010fb-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="010fb-105">Это можно сделать, изменив список параметров.</span><span class="sxs-lookup"><span data-stu-id="010fb-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="010fb-106">Перегрузка правил</span><span class="sxs-lookup"><span data-stu-id="010fb-106">Overloading Rules</span></span>

<span data-ttu-id="010fb-107">При перегрузке процедуры применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="010fb-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="010fb-108">**То же имя**.</span><span class="sxs-lookup"><span data-stu-id="010fb-108">**Same Name**.</span></span> <span data-ttu-id="010fb-109">Каждая перегруженная версия должна использовать одно и то же имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="010fb-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="010fb-110">**Другая сигнатура**.</span><span class="sxs-lookup"><span data-stu-id="010fb-110">**Different Signature**.</span></span> <span data-ttu-id="010fb-111">Каждая перегруженная версия должна отличаться от всех остальных перегруженных версий хотя бы в одном из следующих соблюда:</span><span class="sxs-lookup"><span data-stu-id="010fb-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="010fb-112">Число параметров</span><span class="sxs-lookup"><span data-stu-id="010fb-112">Number of parameters</span></span>

  - <span data-ttu-id="010fb-113">Порядок параметров</span><span class="sxs-lookup"><span data-stu-id="010fb-113">Order of the parameters</span></span>

  - <span data-ttu-id="010fb-114">Типы данных параметров</span><span class="sxs-lookup"><span data-stu-id="010fb-114">Data types of the parameters</span></span>

  - <span data-ttu-id="010fb-115">Число параметров типа (для универсальной процедуры)</span><span class="sxs-lookup"><span data-stu-id="010fb-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="010fb-116">Тип возвращаемого значения (только для оператора преобразования)</span><span class="sxs-lookup"><span data-stu-id="010fb-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="010fb-117">Вместе с именем процедуры предыдущие элементы называются *сигнатурой* процедуры.</span><span class="sxs-lookup"><span data-stu-id="010fb-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="010fb-118">При вызове перегруженной процедуры компилятор использует сигнатуру для проверки того, что вызов правильно соответствует определению.</span><span class="sxs-lookup"><span data-stu-id="010fb-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="010fb-119">**Элементы не являются частью сигнатуры**.</span><span class="sxs-lookup"><span data-stu-id="010fb-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="010fb-120">Нельзя перегружать процедуру без изменения сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="010fb-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="010fb-121">В частности, невозможно перегрузить процедуру, изменив только один или несколько из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="010fb-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="010fb-122">Ключевые слова модификаторов процедур, такие как `Public`, `Shared`и `Static`</span><span class="sxs-lookup"><span data-stu-id="010fb-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="010fb-123">Имя параметра или параметра типа</span><span class="sxs-lookup"><span data-stu-id="010fb-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="010fb-124">Ограничения параметров типа (для универсальной процедуры)</span><span class="sxs-lookup"><span data-stu-id="010fb-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="010fb-125">Ключевые слова модификаторов параметров, такие как `ByRef` и `Optional`</span><span class="sxs-lookup"><span data-stu-id="010fb-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="010fb-126">Возвращает ли оно значение</span><span class="sxs-lookup"><span data-stu-id="010fb-126">Whether it returns a value</span></span>

  - <span data-ttu-id="010fb-127">Тип данных возвращаемого значения (за исключением оператора преобразования)</span><span class="sxs-lookup"><span data-stu-id="010fb-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="010fb-128">Элементы в приведенном выше списке не являются частью сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="010fb-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="010fb-129">Хотя их нельзя использовать для различения перегруженных версий, их можно изменять в разных перегруженных версиях, которые должны различаться в соответствии с сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="010fb-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="010fb-130">**Аргументы с поздним**связыванием.</span><span class="sxs-lookup"><span data-stu-id="010fb-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="010fb-131">Если предполагается передать переменную объекта с поздней привязкой в перегруженную версию, необходимо объявить соответствующий параметр как <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="010fb-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="010fb-132">Несколько версий процедуры</span><span class="sxs-lookup"><span data-stu-id="010fb-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="010fb-133">Предположим, вы пишете `Sub` процедуру для публикации транзакции по балансу клиента и хотите иметь возможность ссылаться на клиента по имени или номеру счета.</span><span class="sxs-lookup"><span data-stu-id="010fb-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="010fb-134">Для этого можно определить две различные процедуры `Sub`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="010fb-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="010fb-135">Перегруженные версии</span><span class="sxs-lookup"><span data-stu-id="010fb-135">Overloaded Versions</span></span>

<span data-ttu-id="010fb-136">Альтернативой является перегрузка имени одной процедуры.</span><span class="sxs-lookup"><span data-stu-id="010fb-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="010fb-137">Для определения версии процедуры для каждого списка параметров можно использовать ключевое слово [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="010fb-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="010fb-138">Дополнительные перегрузки</span><span class="sxs-lookup"><span data-stu-id="010fb-138">Additional Overloads</span></span>

<span data-ttu-id="010fb-139">Если вы также хотите принять сумму транзакции в `Decimal` или `Single`, можно дополнительно перегрузить `post`, чтобы разрешить этот вариант.</span><span class="sxs-lookup"><span data-stu-id="010fb-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="010fb-140">Если вы сделали это для каждой перегрузки в предыдущем примере, у вас будут четыре `Sub`ные процедуры с одним и тем же именем, но с четырьмя разными сигнатурами.</span><span class="sxs-lookup"><span data-stu-id="010fb-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="010fb-141">Преимущества перегрузки</span><span class="sxs-lookup"><span data-stu-id="010fb-141">Advantages of Overloading</span></span>

<span data-ttu-id="010fb-142">Преимущество перегрузки процедуры заключается в гибкости вызова.</span><span class="sxs-lookup"><span data-stu-id="010fb-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="010fb-143">Чтобы использовать процедуру `post`, объявленную в предыдущем примере, вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем вызвать ту же процедуру в любом случае.</span><span class="sxs-lookup"><span data-stu-id="010fb-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="010fb-144">Это показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="010fb-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="010fb-145">См. также</span><span class="sxs-lookup"><span data-stu-id="010fb-145">See also</span></span>

- [<span data-ttu-id="010fb-146">Процедуры</span><span class="sxs-lookup"><span data-stu-id="010fb-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="010fb-147">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="010fb-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="010fb-148">Практическое руководство. Вызов перегруженной процедуры</span><span class="sxs-lookup"><span data-stu-id="010fb-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="010fb-149">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="010fb-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="010fb-150">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="010fb-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="010fb-151">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="010fb-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="010fb-152">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="010fb-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="010fb-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="010fb-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="010fb-154">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="010fb-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
