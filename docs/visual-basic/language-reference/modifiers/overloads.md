---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 0d68846938aba809a7a3a6f7d27f185bb90a39cb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819337"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="51744-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51744-102">Overloads (Visual Basic)</span></span>
<span data-ttu-id="51744-103">Указывает, что свойство или процедура повторно определяет одно или несколько существующих свойств или процедур с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="51744-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51744-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="51744-104">Remarks</span></span>  
 <span data-ttu-id="51744-105">*Перегрузка* — это предоставление нескольких определений для указанного имени свойства или процедуры в той же области.</span><span class="sxs-lookup"><span data-stu-id="51744-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="51744-106">Повторное объявление свойства или процедуры с другой сигнатурой иногда называют *скрытием за сигнатурой*.</span><span class="sxs-lookup"><span data-stu-id="51744-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="51744-107">Правила</span><span class="sxs-lookup"><span data-stu-id="51744-107">Rules</span></span>  
  
-   <span data-ttu-id="51744-108">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="51744-108">**Declaration Context.**</span></span> <span data-ttu-id="51744-109">`Overloads` можно использовать только в операторе объявления свойства или процедуры.</span><span class="sxs-lookup"><span data-stu-id="51744-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="51744-110">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="51744-110">**Combined Modifiers.**</span></span> <span data-ttu-id="51744-111">Нельзя указать `Overloads` вместе с [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) в одном объявлении процедуры.</span><span class="sxs-lookup"><span data-stu-id="51744-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>  
  
-   <span data-ttu-id="51744-112">**Обязательные различия.**</span><span class="sxs-lookup"><span data-stu-id="51744-112">**Required Differences.**</span></span> <span data-ttu-id="51744-113">*Подпись* этого объявления должна отличаться от сигнатуры каждого свойства или процедуры, которые оно переопределяет.</span><span class="sxs-lookup"><span data-stu-id="51744-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="51744-114">Сигнатура включает в себя имя свойства или процедуры, а также следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="51744-114">The signature comprises the property or procedure name together with the following:</span></span>  
  
    -   <span data-ttu-id="51744-115">число параметров;</span><span class="sxs-lookup"><span data-stu-id="51744-115">the number of parameters</span></span>  
  
    -   <span data-ttu-id="51744-116">порядок параметров;</span><span class="sxs-lookup"><span data-stu-id="51744-116">the order of the parameters</span></span>  
  
    -   <span data-ttu-id="51744-117">типы данных параметров;</span><span class="sxs-lookup"><span data-stu-id="51744-117">the data types of the parameters</span></span>  
  
    -   <span data-ttu-id="51744-118">число параметров типа (для универсальной процедуры);</span><span class="sxs-lookup"><span data-stu-id="51744-118">the number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="51744-119">тип возвращаемого значения (только для процедуры оператора преобразования).</span><span class="sxs-lookup"><span data-stu-id="51744-119">the return type (only for a conversion operator procedure)</span></span>  
  
     <span data-ttu-id="51744-120">Все перегрузки должны иметь одно и то же имя, но каждая должна отличаться от всех остальных по одному или нескольким из предыдущих аспектов.</span><span class="sxs-lookup"><span data-stu-id="51744-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="51744-121">Это позволяет компилятору определить, какую именно версию следует использовать, когда код вызывает свойство или процедуру.</span><span class="sxs-lookup"><span data-stu-id="51744-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>  
  
-   <span data-ttu-id="51744-122">**Запрещенные различия.**</span><span class="sxs-lookup"><span data-stu-id="51744-122">**Disallowed Differences.**</span></span> <span data-ttu-id="51744-123">Изменение одного или нескольких из следующих аспектов не является допустимым для перегрузки свойства или процедуры, поскольку они не являются частью сигнатуры:</span><span class="sxs-lookup"><span data-stu-id="51744-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>  
  
    -   <span data-ttu-id="51744-124">наличие возвращаемого значения (для процедуры);</span><span class="sxs-lookup"><span data-stu-id="51744-124">whether or not it returns a value (for a procedure)</span></span>  
  
    -   <span data-ttu-id="51744-125">тип данных возвращаемого значения (за исключением оператора преобразования);</span><span class="sxs-lookup"><span data-stu-id="51744-125">the data type of the return value (except for a conversion operator)</span></span>  
  
    -   <span data-ttu-id="51744-126">имена параметров или параметров типа;</span><span class="sxs-lookup"><span data-stu-id="51744-126">the names of the parameters or type parameters</span></span>  
  
    -   <span data-ttu-id="51744-127">ограничения для параметров типа (для универсальной процедуры);</span><span class="sxs-lookup"><span data-stu-id="51744-127">the constraints on the type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="51744-128">ключевые слова модификаторов параметров (например, `ByRef` или `Optional`);</span><span class="sxs-lookup"><span data-stu-id="51744-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>  
  
    -   <span data-ttu-id="51744-129">ключевые слова модификаторов свойств или процедур (например, `Public` или `Shared`).</span><span class="sxs-lookup"><span data-stu-id="51744-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>  
  
-   <span data-ttu-id="51744-130">**Необязательный модификатор.**</span><span class="sxs-lookup"><span data-stu-id="51744-130">**Optional Modifier.**</span></span> <span data-ttu-id="51744-131">Модификатор `Overloads` можно не использовать при определении нескольких перегруженных свойств или процедур в одном классе.</span><span class="sxs-lookup"><span data-stu-id="51744-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="51744-132">Однако при использовании `Overloads` в одном из объявлений его необходимо использовать в них всех.</span><span class="sxs-lookup"><span data-stu-id="51744-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>  
  
-   <span data-ttu-id="51744-133">**Затенение и перегрузка.**</span><span class="sxs-lookup"><span data-stu-id="51744-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="51744-134">`Overloads` Можно также использовать для затенения существующего члена или набора перегруженных членов в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="51744-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="51744-135">При таком использовании `Overloads` свойство или метод объявляются с таким же именем и таким же списком параметров, как и у члена базового класса, а ключевое слово `Shadows` не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="51744-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>  
  
 <span data-ttu-id="51744-136">При использовании `Overrides` компилятор неявно добавляет `Overloads`, чтобы упростить работу API-интерфейсов с библиотекой C#.</span><span class="sxs-lookup"><span data-stu-id="51744-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="51744-137">Модификатор `Overloads` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="51744-137">The `Overloads` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="51744-138">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="51744-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="51744-139">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="51744-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="51744-140">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="51744-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="51744-141">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="51744-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="51744-142">См. также</span><span class="sxs-lookup"><span data-stu-id="51744-142">See also</span></span>

- [<span data-ttu-id="51744-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="51744-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="51744-144">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="51744-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="51744-145">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="51744-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="51744-146">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="51744-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="51744-147">Практическое руководство. Определение оператора преобразования</span><span class="sxs-lookup"><span data-stu-id="51744-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
