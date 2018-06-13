---
title: Определение анонимного типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 179fb9773fde2631666498d54894037b2bbfd087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649624"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="b846e-102">Определение анонимного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b846e-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="b846e-103">В ответ на объявление экземпляра анонимного типа компилятор создает определение нового класса, который содержит указанные свойства для типа.</span><span class="sxs-lookup"><span data-stu-id="b846e-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="b846e-104">Созданный компилятором код</span><span class="sxs-lookup"><span data-stu-id="b846e-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="b846e-105">Следующие определения `product`, компилятор создает определение нового класса, который содержит свойства `Name`, `Price`, и `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="b846e-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 <span data-ttu-id="b846e-106">Определение класса содержит определения свойств следующего вида.</span><span class="sxs-lookup"><span data-stu-id="b846e-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="b846e-107">Обратите внимание, что имеется не `Set` метод для ключевых свойств.</span><span class="sxs-lookup"><span data-stu-id="b846e-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="b846e-108">Значения ключевых свойств доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b846e-108">The values of key properties are read-only.</span></span>  
  
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
  
 <span data-ttu-id="b846e-109">Кроме того определения анонимного типа содержат конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b846e-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="b846e-110">Конструкторы, требующие параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="b846e-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="b846e-111">Если в объявлении анонимного типа содержит по крайней мере одно ключевое свойство, определение переопределяет три члена, унаследованные от <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="b846e-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="b846e-112">Если ключевые свойства не объявлены, только <xref:System.Object.ToString%2A> переопределяется.</span><span class="sxs-lookup"><span data-stu-id="b846e-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="b846e-113">Переопределение предоставляет следующие функциональные возможности:</span><span class="sxs-lookup"><span data-stu-id="b846e-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="b846e-114">`Equals` Возвращает `True` , если два экземпляра анонимного типа являются одним экземпляром или при соблюдении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="b846e-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="b846e-115">Они имеют одинаковое число свойств.</span><span class="sxs-lookup"><span data-stu-id="b846e-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="b846e-116">Свойства объявляются в том же порядке, с теми же именами и те же возвращаемые типы.</span><span class="sxs-lookup"><span data-stu-id="b846e-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="b846e-117">Имя сравнения регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="b846e-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="b846e-118">По крайней мере одно из свойств является ключевым свойством и `Key` те же свойства применяется ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b846e-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="b846e-119">Сравнение каждой соответствующей пары ключевых свойств возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="b846e-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="b846e-120">Например, в следующих примерах `Equals` возвращает `True` только для `employee01` и `employee08`.</span><span class="sxs-lookup"><span data-stu-id="b846e-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="b846e-121">Комментарий перед каждой строки определяет причины, почему нового экземпляра не соответствует `employee01`.</span><span class="sxs-lookup"><span data-stu-id="b846e-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   <span data-ttu-id="b846e-122">`GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="b846e-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="b846e-123">Алгоритм использует только ключевые свойства для вычисления хэш-код.</span><span class="sxs-lookup"><span data-stu-id="b846e-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="b846e-124">`ToString` Возвращает строку объединены значения свойств, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b846e-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="b846e-125">Включены ключ и неключевые свойства.</span><span class="sxs-lookup"><span data-stu-id="b846e-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 <span data-ttu-id="b846e-126">Явно именованные свойства анонимного типа не могут конфликтовать с этими созданными методами.</span><span class="sxs-lookup"><span data-stu-id="b846e-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="b846e-127">Другими словами, нельзя использовать `.Equals`, `.GetHashCode`, или `.ToString` для имени свойства.</span><span class="sxs-lookup"><span data-stu-id="b846e-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="b846e-128">Определения анонимных типов, включающих по крайней мере одно ключевое свойство, также реализуют <xref:System.IEquatable%601?displayProperty=nameWithType> интерфейса, где `T` тип анонимного типа.</span><span class="sxs-lookup"><span data-stu-id="b846e-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b846e-129">Объявления анонимного типа создают одного анонимного типа только в том случае, если они встречаются в той же сборке, их свойства имеют те же имена и те же выводимые типы, свойства объявлены в том же порядке и те же свойства помечены как ключевые свойства.</span><span class="sxs-lookup"><span data-stu-id="b846e-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b846e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b846e-130">See Also</span></span>  
 [<span data-ttu-id="b846e-131">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="b846e-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="b846e-132">Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов</span><span class="sxs-lookup"><span data-stu-id="b846e-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
