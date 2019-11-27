---
title: Предложение Of
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
ms.openlocfilehash: d88c43efe858d6b81b7d8d2470b234ff5d40632a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353843"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="4f794-102">Предложение Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f794-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="4f794-103">Вводит предложение `Of`, которое определяет *параметр типа* в *универсальном* классе, структуре, интерфейсе, делегате или процедуре.</span><span class="sxs-lookup"><span data-stu-id="4f794-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="4f794-104">Сведения об универсальных типах см. [в разделе Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="4f794-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="4f794-105">Использование ключевого слова of</span><span class="sxs-lookup"><span data-stu-id="4f794-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="4f794-106">В следующем примере кода ключевое слово `Of` используется для определения структуры класса, принимающего два параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4f794-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="4f794-107">Он *ограничивает* параметр `keyType` интерфейсом <xref:System.IComparable>, что означает, что в используемом коде должен быть указан аргумент типа, реализующий <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="4f794-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="4f794-108">Это необходимо для того, чтобы процедура `add` могла вызвать метод <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4f794-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4f794-109">Дополнительные сведения об ограничениях см. в разделе [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="4f794-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```vb  
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
  
 <span data-ttu-id="4f794-110">Если вы закончите предыдущее определение класса, можно создать из него разнообразные `dictionary` классы.</span><span class="sxs-lookup"><span data-stu-id="4f794-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="4f794-111">Типы, предоставляемые для `entryType` и `keyType` определяют, какой тип записи принадлежит классу и какой тип ключа он связывает с каждой записью.</span><span class="sxs-lookup"><span data-stu-id="4f794-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="4f794-112">Из-за ограничения необходимо указать, чтобы `keyType` тип, реализующий <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="4f794-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="4f794-113">В следующем примере кода создается объект, содержащий `String` записи и связывающий ключ `Integer` с каждым из них.</span><span class="sxs-lookup"><span data-stu-id="4f794-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="4f794-114">`Integer` реализует <xref:System.IComparable> и, следовательно, удовлетворяет ограничениям на `keyType`.</span><span class="sxs-lookup"><span data-stu-id="4f794-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="4f794-115">Ключевое слово `Of` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="4f794-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4f794-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="4f794-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="4f794-117">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="4f794-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="4f794-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="4f794-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4f794-119">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="4f794-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="4f794-120">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="4f794-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="4f794-121">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="4f794-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f794-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f794-122">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="4f794-123">Список типов</span><span class="sxs-lookup"><span data-stu-id="4f794-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="4f794-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f794-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="4f794-125">In</span><span class="sxs-lookup"><span data-stu-id="4f794-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="4f794-126">Out</span><span class="sxs-lookup"><span data-stu-id="4f794-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
