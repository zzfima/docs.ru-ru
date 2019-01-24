---
title: Разрешение перегрузки не может использоваться для &#39; &lt;имя_процедуры&gt; &#39; поскольку интерфейс доступа принадлежит к типу интерфейса
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: db0ce88f63be8d58cc1c1abf91eda6a0e56456c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651523"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="bb52d-102">Разрешение перегрузки не может использоваться для &#39; &lt;имя_процедуры&gt; &#39; поскольку интерфейс доступа принадлежит к типу интерфейса</span><span class="sxs-lookup"><span data-stu-id="bb52d-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="bb52d-103">Компилятор пытается разрешить ссылку на перегруженное свойство или процедуру, но не выполняется, так как аргумент имеет тип `Object` и ссылающийся объект имеет тип данных интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb52d-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="bb52d-104">`Object` Аргумент указывает компилятору разрешить ссылку с поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="bb52d-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="bb52d-105">В этих случаях компилятор разрешает перегрузку посредством реализации класса, а не базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb52d-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="bb52d-106">Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию в качестве перегрузки, так как его имя отличается.</span><span class="sxs-lookup"><span data-stu-id="bb52d-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="bb52d-107">Это указывает компилятору игнорировать переименованную версию, когда было бы разрешить ссылку на правильный выбор.</span><span class="sxs-lookup"><span data-stu-id="bb52d-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="bb52d-108">**Идентификатор ошибки:** BC30933</span><span class="sxs-lookup"><span data-stu-id="bb52d-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb52d-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bb52d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="bb52d-110">Используйте `CType` для приведения аргументов `Object` к типу, указанному в подписи перегрузки, необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="bb52d-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="bb52d-111">Обратите внимание на то, что не дает им возможность привести ссылающийся объект базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bb52d-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="bb52d-112">Необходимо привести аргумент, чтобы избежать этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="bb52d-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb52d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="bb52d-113">Example</span></span>  
 <span data-ttu-id="bb52d-114">В примере показан вызов перегруженной `Sub` процедуру, которая вызывает эту ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="bb52d-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 <span data-ttu-id="bb52d-115">В предыдущем примере, если компилятор разрешил вызов `s1` записи разрешения будет выполняться через класс `c1` вместо интерфейса `i1`.</span><span class="sxs-lookup"><span data-stu-id="bb52d-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="bb52d-116">Это будет означать, что компилятор не будет учитывать `s2` так, как его имя отличается в `c1`, несмотря на то, что это правильный выбор в соответствии с определением `i1`.</span><span class="sxs-lookup"><span data-stu-id="bb52d-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="bb52d-117">Ошибку можно исправить, изменив вызова одной из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="bb52d-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="bb52d-118">Каждая из строк предыдущего кода явно приводит `Object` переменной `o1` к одному из типов параметров, определенных для перегрузок.</span><span class="sxs-lookup"><span data-stu-id="bb52d-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb52d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bb52d-119">See also</span></span>
- [<span data-ttu-id="bb52d-120">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="bb52d-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="bb52d-121">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="bb52d-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="bb52d-122">Функция CType</span><span class="sxs-lookup"><span data-stu-id="bb52d-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
