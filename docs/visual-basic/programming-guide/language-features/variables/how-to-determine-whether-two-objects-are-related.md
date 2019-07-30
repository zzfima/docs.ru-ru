---
title: Практическое руководство. Определить, связаны ли два объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626555"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="f26b9-102">Практическое руководство. Определить, связаны ли два объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f26b9-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="f26b9-103">Можно сравнить два объекта, чтобы определить связь между классами, из которых они были созданы.</span><span class="sxs-lookup"><span data-stu-id="f26b9-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="f26b9-104"><xref:System.Type.IsInstanceOfType%2A> Метод класса<xref:System.Type?displayProperty=nameWithType> возвращает значение,еслиуказанныйкласснаследуетсяоттекущегокласса,илиеслитекущийтипявляетсяинтерфейсом`True` , поддерживаемым указанным классом.</span><span class="sxs-lookup"><span data-stu-id="f26b9-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="f26b9-105">Определение того, наследуется ли один объект от класса или интерфейса другого объекта</span><span class="sxs-lookup"><span data-stu-id="f26b9-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="f26b9-106">В объекте, который вы считаете, может быть базовым типом, вызовите <xref:System.Object.GetType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="f26b9-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="f26b9-107">В объекте, возвращенном <xref:System.Object.GetType%2A>методом, вызовите <xref:System.Type.IsInstanceOfType%2A> метод. <xref:System.Type?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f26b9-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="f26b9-108">В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>укажите объект, который может иметь производный тип.</span><span class="sxs-lookup"><span data-stu-id="f26b9-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="f26b9-109"><xref:System.Type.IsInstanceOfType%2A>Возвращает `True` значение, <xref:System.Type?displayProperty=nameWithType> если тип его аргумента наследуется от типа объекта.</span><span class="sxs-lookup"><span data-stu-id="f26b9-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="f26b9-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f26b9-110">Example</span></span>
 <span data-ttu-id="f26b9-111">В следующем примере определяется, представляет ли один объект класс, производный от класса другого объекта.</span><span class="sxs-lookup"><span data-stu-id="f26b9-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="f26b9-112">Обратите внимание на непредвиденное размещение двух переменных объекта в вызове <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f26b9-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="f26b9-113">Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класса, а предполагаемый производный тип передается в качестве аргумента <xref:System.Type.IsInstanceOfType%2A> в метод.</span><span class="sxs-lookup"><span data-stu-id="f26b9-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="f26b9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f26b9-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="f26b9-115">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="f26b9-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="f26b9-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="f26b9-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="f26b9-117">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="f26b9-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="f26b9-118">Практическое руководство. Определить, идентичны ли два объекта</span><span class="sxs-lookup"><span data-stu-id="f26b9-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
