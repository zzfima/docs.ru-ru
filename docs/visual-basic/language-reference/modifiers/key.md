---
title: Key (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a><span data-ttu-id="7f361-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f361-102">Key (Visual Basic)</span></span>
<span data-ttu-id="7f361-103">`Key` Ключевое слово позволяет указать поведение свойств анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="7f361-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="7f361-104">Только свойства, указанные как ключевые свойства, участвуют в проверке равенства между экземплярами анонимного типа, или вычисления значений хэш-кода.</span><span class="sxs-lookup"><span data-stu-id="7f361-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="7f361-105">Невозможно изменить значения ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="7f361-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="7f361-106">Укажите свойство анонимного типа как ключевые свойства, поместив ключевое слово `Key` перед ее объявления в списке инициализации.</span><span class="sxs-lookup"><span data-stu-id="7f361-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="7f361-107">В следующем примере `Airline` и `FlightNo` являются ключевыми, но `Gate` не является.</span><span class="sxs-lookup"><span data-stu-id="7f361-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 <span data-ttu-id="7f361-108">При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="7f361-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="7f361-109">Компилятор переопределяет три члена, унаследованного: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f361-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="7f361-110">Переопределение код, который создается для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> основан на ключевые свойства.</span><span class="sxs-lookup"><span data-stu-id="7f361-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="7f361-111">Если нет ключевых свойств в типе, <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> не переопределяются.</span><span class="sxs-lookup"><span data-stu-id="7f361-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="7f361-112">Равенство</span><span class="sxs-lookup"><span data-stu-id="7f361-112">Equality</span></span>  
 <span data-ttu-id="7f361-113">Два экземпляра анонимного типа равны, если они являются экземплярами одного типа, и если равны значения их ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="7f361-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="7f361-114">В следующих примерах `flight2` равен `flight1` из предыдущего примера, поскольку они являются экземплярами одного анонимного типа и иметь совпадающие значения их ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="7f361-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="7f361-115">Тем не менее `flight3` не равно `flight1` , так как он имеет другое значение для ключа свойства `FlightNo`.</span><span class="sxs-lookup"><span data-stu-id="7f361-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="7f361-116">Экземпляр `flight4` не совпадает с типом `flight1` так, как они назначить различные свойства в качестве свойства ключа.</span><span class="sxs-lookup"><span data-stu-id="7f361-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 <span data-ttu-id="7f361-117">Если два экземпляра должны быть объявлены с только неключевыми свойствами, идентичными по имени, типа, порядок и значения, два экземпляра не равны.</span><span class="sxs-lookup"><span data-stu-id="7f361-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="7f361-118">Экземпляр без ключевого свойства равен только самому себе.</span><span class="sxs-lookup"><span data-stu-id="7f361-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="7f361-119">Дополнительные сведения об условиях, при которых два экземпляра анонимного типа являются экземплярами одного анонимного типа см. в разделе [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f361-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="7f361-120">Вычисление хэш-кода</span><span class="sxs-lookup"><span data-stu-id="7f361-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="7f361-121">Как <xref:System.Object.Equals%2A>, хэш-функции, определенные в <xref:System.Object.GetHashCode%2A> для анонимного типа основана на ключевые свойства типа.</span><span class="sxs-lookup"><span data-stu-id="7f361-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="7f361-122">В следующих примерах показано взаимодействие между ключевыми свойствами и хэш-код значения.</span><span class="sxs-lookup"><span data-stu-id="7f361-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="7f361-123">Экземпляры анонимного типа, имеющие одинаковые значения для всех ключевых свойств иметь значение же хэш-кода, даже если неключевые свойства не имеют совпадающих значений.</span><span class="sxs-lookup"><span data-stu-id="7f361-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="7f361-124">Следующая инструкция возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="7f361-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 <span data-ttu-id="7f361-125">Экземпляры анонимного типа, имеющие различные значения для одного или нескольких ключевых свойств имеют разные хэш-код значения.</span><span class="sxs-lookup"><span data-stu-id="7f361-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="7f361-126">Следующая инструкция возвращает `False`.</span><span class="sxs-lookup"><span data-stu-id="7f361-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 <span data-ttu-id="7f361-127">Экземпляры анонимных типов, определяющие различные свойства как ключевые свойства не являются экземплярами одного типа.</span><span class="sxs-lookup"><span data-stu-id="7f361-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="7f361-128">Они имеют разные хэш-код значения даже в том случае, если имена и значения всех свойств совпадают.</span><span class="sxs-lookup"><span data-stu-id="7f361-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="7f361-129">Следующая инструкция возвращает `False`.</span><span class="sxs-lookup"><span data-stu-id="7f361-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a><span data-ttu-id="7f361-130">Значения, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="7f361-130">Read-Only Values</span></span>  
 <span data-ttu-id="7f361-131">Невозможно изменить значения ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="7f361-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="7f361-132">Например, в `flight1` в предыдущих примерах, `Airline` и `FlightNo` поля доступны только для чтения, но `Gate` может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="7f361-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7f361-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7f361-133">See Also</span></span>  
 [<span data-ttu-id="7f361-134">Определение анонимного типа</span><span class="sxs-lookup"><span data-stu-id="7f361-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [<span data-ttu-id="7f361-135">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="7f361-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [<span data-ttu-id="7f361-136">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="7f361-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
