---
title: "Разрешение перегрузки не может применяться к &#39; &lt;имя_процедуры&gt;&#39; поскольку доступ осуществляется из типа интерфейса"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb7f8a9f6eadfc9fd856ea57d362b43d25ff81a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="099e8-102">Разрешение перегрузки не может применяться к &#39; &lt;имя_процедуры&gt;&#39; поскольку доступ осуществляется из типа интерфейса</span><span class="sxs-lookup"><span data-stu-id="099e8-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="099e8-103">Компилятор пытается разрешить ссылку на перегруженного свойства или процедуры, но не выполняется, так как тип аргумента `Object` и ссылающийся объект имеет тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="099e8-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="099e8-104">`Object` Аргумент указывает компилятору разрешить ссылку с поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="099e8-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="099e8-105">В этом случае компилятор разрешает перегрузку посредством реализующего класса вместо базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="099e8-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="099e8-106">Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию в качестве перегрузку, так как его имя отличается.</span><span class="sxs-lookup"><span data-stu-id="099e8-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="099e8-107">Это указывает компилятору игнорировать переименованную версию, когда было бы правильный выбор для разрешения ссылки.</span><span class="sxs-lookup"><span data-stu-id="099e8-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="099e8-108">**Идентификатор ошибки:** BC30933</span><span class="sxs-lookup"><span data-stu-id="099e8-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="099e8-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="099e8-109">To correct this error</span></span>  
  
-   <span data-ttu-id="099e8-110">Используйте `CType` для приведения аргументов `Object` типу, указанному в сигнатуре перегрузки, которые вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="099e8-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="099e8-111">Обратите внимание, что он не поможет приведение ссылающегося объекта базового интерфейса.</span><span class="sxs-lookup"><span data-stu-id="099e8-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="099e8-112">Необходимо привести аргумент, чтобы избежать этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="099e8-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="099e8-113">Пример</span><span class="sxs-lookup"><span data-stu-id="099e8-113">Example</span></span>  
 <span data-ttu-id="099e8-114">В следующем примере показано вызов перегруженной `Sub` процедура, которая вызывает эту ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="099e8-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
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
  
 <span data-ttu-id="099e8-115">В предыдущем примере, если компилятор разрешил вызов `s1` записи разрешение будет иметь место через класс `c1` вместо интерфейса `i1`.</span><span class="sxs-lookup"><span data-stu-id="099e8-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="099e8-116">Это будет означать, что компилятор не будет учитывать `s2` , так как его имя отличается в `c1`, несмотря на то, что это правильный выбор в соответствии с определением `i1`.</span><span class="sxs-lookup"><span data-stu-id="099e8-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="099e8-117">Ошибку можно устранить путем изменения вызова одной из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="099e8-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="099e8-118">Каждая из строк предыдущего кода явно приводит `Object` переменной `o1` к одному из типов параметров, определенных для перегрузки.</span><span class="sxs-lookup"><span data-stu-id="099e8-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099e8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="099e8-119">See Also</span></span>  
 [<span data-ttu-id="099e8-120">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="099e8-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="099e8-121">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="099e8-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [<span data-ttu-id="099e8-122">Функция CType</span><span class="sxs-lookup"><span data-stu-id="099e8-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
