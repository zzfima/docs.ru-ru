---
title: Определение анонимного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 5f6486965d9e44524420975523e10ded32a135b7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755215"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="89278-102">Определение анонимного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89278-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="89278-103">В ответ на объявление экземпляра анонимного типа компилятор создает определение нового класса, который содержит указанные свойства для типа.</span><span class="sxs-lookup"><span data-stu-id="89278-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="89278-104">Созданный компилятором код</span><span class="sxs-lookup"><span data-stu-id="89278-104">Compiler-Generated Code</span></span>

<span data-ttu-id="89278-105">Для следующее определение `product`, компилятор создает определение нового класса, который содержит свойства `Name`, `Price`, и `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="89278-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="89278-106">Определение класса содержит определения свойств следующего вида.</span><span class="sxs-lookup"><span data-stu-id="89278-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="89278-107">Обратите внимание, что не `Set` метод для ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="89278-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="89278-108">Значения свойств ключа доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="89278-108">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="89278-109">Кроме того определения анонимного типа содержат конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="89278-109">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="89278-110">Конструкторы, требующие параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="89278-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="89278-111">Если в объявлении анонимного типа содержит по крайней мере одно ключевое свойство, определение переопределяет три члена, унаследованные от <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="89278-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="89278-112">При объявлении ключевые свойства, а только <xref:System.Object.ToString%2A> переопределяется.</span><span class="sxs-lookup"><span data-stu-id="89278-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="89278-113">Переопределение предоставляет следующие функциональные возможности:</span><span class="sxs-lookup"><span data-stu-id="89278-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="89278-114">`Equals` Возвращает `True` Если два экземпляра анонимного типа являются одним экземпляром или при соблюдении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="89278-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="89278-115">Они имеют такое же количество свойств.</span><span class="sxs-lookup"><span data-stu-id="89278-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="89278-116">Свойства объявляются в том же порядке, с теми же именами и те же возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="89278-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="89278-117">Сравнение имен регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="89278-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="89278-118">По крайней мере одно из свойств является свойством ключа и `Key` те же свойства применяется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="89278-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="89278-119">Сравнение каждой соответствующей пары ключевых свойств возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="89278-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="89278-120">Например, в следующих примерах `Equals` возвращает `True` только для `employee01` и `employee08`.</span><span class="sxs-lookup"><span data-stu-id="89278-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="89278-121">Комментарий перед каждой строке указывается причина, почему нового экземпляра не соответствует `employee01`.</span><span class="sxs-lookup"><span data-stu-id="89278-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="89278-122">`GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="89278-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="89278-123">Алгоритм использует только ключевые свойства для вычисления хэш-код.</span><span class="sxs-lookup"><span data-stu-id="89278-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="89278-124">`ToString` Возвращает строку объединены значения свойств, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="89278-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="89278-125">Включены ключевые и неключевые свойства.</span><span class="sxs-lookup"><span data-stu-id="89278-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="89278-126">Явно именованные свойства анонимного типа не должны конфликтовать с эти созданные методы.</span><span class="sxs-lookup"><span data-stu-id="89278-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="89278-127">То есть нельзя использовать `.Equals`, `.GetHashCode`, или `.ToString` для имени свойства.</span><span class="sxs-lookup"><span data-stu-id="89278-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="89278-128">Определения анонимного типа, включающих по крайней мере одно ключевое свойство, также реализуют <xref:System.IEquatable%601?displayProperty=nameWithType> интерфейс, где `T` тип анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="89278-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="89278-129">Объявления анонимного типа создать анонимный тип аналогично только в том случае, если они встречаются в той же сборке, их свойства имеют те же имена и те же возвращаемые типы, свойства объявляются в том же порядке и те же свойства, помечаются как ключевые свойства.</span><span class="sxs-lookup"><span data-stu-id="89278-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="89278-130">См. также</span><span class="sxs-lookup"><span data-stu-id="89278-130">See also</span></span>

- [<span data-ttu-id="89278-131">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="89278-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="89278-132">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="89278-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
