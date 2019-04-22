---
title: Предложение Of (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: 880570c714292b0c11eef4e2cd4c4b410bb075f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823445"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="36bd7-102">Предложение Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36bd7-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="36bd7-103">Представляет `Of` предложение, которое идентифицирует *параметр типа* на *универсального* класса, структуры, интерфейса, делегата или процедуры.</span><span class="sxs-lookup"><span data-stu-id="36bd7-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="36bd7-104">Сведения об универсальных типах см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="36bd7-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="36bd7-105">С помощью ключевого слова</span><span class="sxs-lookup"><span data-stu-id="36bd7-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="36bd7-106">В следующем примере кода используется `Of` ключевое слово для определения структуры, класса, который принимает два параметра типа.</span><span class="sxs-lookup"><span data-stu-id="36bd7-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="36bd7-107">Он *ограничивает* `keyType` по <xref:System.IComparable> интерфейс, который означает, что код-потребитель должен предоставить аргумент типа, который реализует <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="36bd7-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="36bd7-108">Это необходимо, чтобы `add` процедура может вызывать <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="36bd7-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36bd7-109">Дополнительные сведения об ограничениях см. в разделе [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="36bd7-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="36bd7-110">Если выполнить предыдущий определение класса, можно создать различные `dictionary` классы из него.</span><span class="sxs-lookup"><span data-stu-id="36bd7-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="36bd7-111">Типы, которые вводятся `entryType` и `keyType` определить, содержит класс тип записи и какой тип ключа, который связывает, с каждой записи.</span><span class="sxs-lookup"><span data-stu-id="36bd7-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="36bd7-112">Из-за ограничения, необходимо указать `keyType` тип, реализующий <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="36bd7-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="36bd7-113">В следующем примере кода создается объект, содержащий `String` записи и связывает `Integer` ключа с каждой из них.</span><span class="sxs-lookup"><span data-stu-id="36bd7-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="36bd7-114">`Integer` реализует <xref:System.IComparable> и таким образом удовлетворяющую на `keyType`.</span><span class="sxs-lookup"><span data-stu-id="36bd7-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="36bd7-115">Ключевое слово `Of` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="36bd7-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="36bd7-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="36bd7-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="36bd7-117">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="36bd7-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="36bd7-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="36bd7-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="36bd7-119">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="36bd7-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="36bd7-120">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="36bd7-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="36bd7-121">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="36bd7-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="36bd7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="36bd7-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="36bd7-123">Список типов</span><span class="sxs-lookup"><span data-stu-id="36bd7-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="36bd7-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="36bd7-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="36bd7-125">In</span><span class="sxs-lookup"><span data-stu-id="36bd7-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="36bd7-126">Out</span><span class="sxs-lookup"><span data-stu-id="36bd7-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
