---
title: Практическое руководство. Определение связи между двумя объектами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342106"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="60796-102">Практическое руководство. Определение связи между двумя объектами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60796-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="60796-103">Вы можете сравнить два объекта для определения связи между классами, из которых они создаются.</span><span class="sxs-lookup"><span data-stu-id="60796-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="60796-104"><xref:System.Type.IsInstanceOfType%2A> Метод <xref:System.Type?displayProperty=nameWithType> возвращает `True` Если класс наследует от текущего класса или если текущий тип является интерфейсом, поддерживаемым указанного класса.</span><span class="sxs-lookup"><span data-stu-id="60796-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="60796-105">Чтобы определить, если один объект наследует от класса или интерфейса другого объекта</span><span class="sxs-lookup"><span data-stu-id="60796-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1. <span data-ttu-id="60796-106">В объекте, который вы считаете может быть базового типа, вызывают <xref:System.Object.GetType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="60796-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2. <span data-ttu-id="60796-107">На <xref:System.Type?displayProperty=nameWithType> объект, возвращаемый <xref:System.Object.GetType%2A>, вызвать <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="60796-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3. <span data-ttu-id="60796-108">В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>, укажите объект, вы думаете, может быть производного типа.</span><span class="sxs-lookup"><span data-stu-id="60796-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="60796-109"><xref:System.Type.IsInstanceOfType%2A> Возвращает `True` Если тип аргумента наследует из <xref:System.Type?displayProperty=nameWithType> тип объекта.</span><span class="sxs-lookup"><span data-stu-id="60796-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60796-110">Пример</span><span class="sxs-lookup"><span data-stu-id="60796-110">Example</span></span>  
 <span data-ttu-id="60796-111">В следующем примере определяется, представляет ли один объект класса, производного от класса другого объекта.</span><span class="sxs-lookup"><span data-stu-id="60796-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
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
  
 <span data-ttu-id="60796-112">Заметьте, переменные два объекта в вызове <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="60796-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="60796-113">Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класс и предполагаемый производный тип передается в качестве аргумента <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="60796-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60796-114">См. также</span><span class="sxs-lookup"><span data-stu-id="60796-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="60796-115">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="60796-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="60796-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="60796-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="60796-117">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="60796-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="60796-118">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="60796-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
