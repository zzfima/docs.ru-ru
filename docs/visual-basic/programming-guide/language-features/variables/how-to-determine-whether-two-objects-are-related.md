---
title: Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2041f89ffd954e479046eb85c6dd82de1f8793ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649829"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="757ea-102">Практическое руководство. Определение наличия связи между двумя объектами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="757ea-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="757ea-103">Можно сравнить два объекта, чтобы определить связь между классами, от которых они создаются.</span><span class="sxs-lookup"><span data-stu-id="757ea-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="757ea-104"><xref:System.Type.IsInstanceOfType%2A> Метод <xref:System.Type?displayProperty=nameWithType> возвращает `True` Если класс наследуется от текущего класса или если текущий тип является интерфейсом, который поддерживается с помощью указанного класса.</span><span class="sxs-lookup"><span data-stu-id="757ea-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="757ea-105">Чтобы определить, если один объект наследует от класса или интерфейса другого объекта</span><span class="sxs-lookup"><span data-stu-id="757ea-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="757ea-106">В объекте, который вы считаете, может быть базового типа, вызывают <xref:System.Object.GetType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="757ea-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="757ea-107">На <xref:System.Type?displayProperty=nameWithType> объект, возвращаемый <xref:System.Object.GetType%2A>, вызвать <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="757ea-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="757ea-108">В списке аргументов для <xref:System.Type.IsInstanceOfType%2A>, укажите объект, вы считаете, может быть производного типа.</span><span class="sxs-lookup"><span data-stu-id="757ea-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="757ea-109"><xref:System.Type.IsInstanceOfType%2A> Возвращает `True` Если тип аргумента наследует от <xref:System.Type?displayProperty=nameWithType> тип объекта.</span><span class="sxs-lookup"><span data-stu-id="757ea-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="757ea-110">Пример</span><span class="sxs-lookup"><span data-stu-id="757ea-110">Example</span></span>  
 <span data-ttu-id="757ea-111">В следующем примере определяется, является ли один объект представляет класс, производный от класса другого объекта.</span><span class="sxs-lookup"><span data-stu-id="757ea-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
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
  
 <span data-ttu-id="757ea-112">Заметьте, переменные два объекта в вызове <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="757ea-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="757ea-113">Предполагаемый базовый тип используется для создания <xref:System.Type?displayProperty=nameWithType> класс и предполагаемый производный тип передается в качестве аргумента для <xref:System.Type.IsInstanceOfType%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="757ea-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757ea-114">См. также</span><span class="sxs-lookup"><span data-stu-id="757ea-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="757ea-115">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="757ea-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="757ea-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="757ea-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="757ea-117">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="757ea-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="757ea-118">Практическое руководство. Определение идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="757ea-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
