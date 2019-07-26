---
title: Разрешение перегружаемой функции с поздним связыванием не может быть применено к <procedurename>, так как типом экземпляра, к которому осуществляется доступ, является интерфейс
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 1fe3c4a29b542302b3615459142a3c565aa8244f
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513025"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="12cad-102">Невозможно применить разрешение перегрузки с привязывания к "\<ProcedureName >", так как доступ к экземпляру является типом интерфейса</span><span class="sxs-lookup"><span data-stu-id="12cad-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>

<span data-ttu-id="12cad-103">Компилятор пытается разрешить ссылку на Перегруженное свойство или процедуру, но ссылка завершается ошибкой, поскольку аргумент имеет тип `Object` , а ссылающийся объект имеет тип данных интерфейса.</span><span class="sxs-lookup"><span data-stu-id="12cad-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="12cad-104">`Object` Аргумент заставляет компилятор разрешить ссылку с поздней привязкой.</span><span class="sxs-lookup"><span data-stu-id="12cad-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>

<span data-ttu-id="12cad-105">В этих случаях компилятор разрешает перегрузку через реализующий класс, а не через базовый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="12cad-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="12cad-106">Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию как перегрузку, поскольку ее имя отличается.</span><span class="sxs-lookup"><span data-stu-id="12cad-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="12cad-107">Это, в свою очередь, приводит к тому, что компилятор пропускает переименованную версию, когда она могла быть правильно выбрана для разрешения ссылки.</span><span class="sxs-lookup"><span data-stu-id="12cad-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>

<span data-ttu-id="12cad-108">**Идентификатор ошибки:** BC30933</span><span class="sxs-lookup"><span data-stu-id="12cad-108">**Error ID:** BC30933</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="12cad-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="12cad-109">To correct this error</span></span>

- <span data-ttu-id="12cad-110">Используйте `CType` для приведения `Object` аргумента к типу, указанному в сигнатуре перегрузки, которую требуется вызвать.</span><span class="sxs-lookup"><span data-stu-id="12cad-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>

  <span data-ttu-id="12cad-111">Обратите внимание, что он не помогает привести ссылающийся объект к базовому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="12cad-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="12cad-112">Чтобы избежать этой ошибки, необходимо привести аргумент.</span><span class="sxs-lookup"><span data-stu-id="12cad-112">You must cast the argument to avoid this error.</span></span>

## <a name="example"></a><span data-ttu-id="12cad-113">Пример</span><span class="sxs-lookup"><span data-stu-id="12cad-113">Example</span></span>

<span data-ttu-id="12cad-114">В следующем примере показан вызов перегруженной `Sub` процедуры, которая вызывает эту ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="12cad-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>

```vb
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

<span data-ttu-id="12cad-115">В предыдущем примере, если компилятор разрешил вызов `s1` как написанный, разрешение будет происходить через класс `c1` вместо интерфейса `i1`.</span><span class="sxs-lookup"><span data-stu-id="12cad-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="12cad-116">Это означает, что компилятор не будет считать `s2` , что его имя отличается в, несмотря на то, что это `i1`правильный вариант, как определено в `c1`.</span><span class="sxs-lookup"><span data-stu-id="12cad-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>

<span data-ttu-id="12cad-117">Ошибку можно исправить, изменив вызов одной из следующих строк кода:</span><span class="sxs-lookup"><span data-stu-id="12cad-117">You can correct the error by changing the call to either of the following lines of code:</span></span>

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

<span data-ttu-id="12cad-118">Каждая из приведенных выше строк кода явным образом приводит `Object` переменную `o1` к одному из типов параметров, определенных для перегрузок.</span><span class="sxs-lookup"><span data-stu-id="12cad-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>

## <a name="see-also"></a><span data-ttu-id="12cad-119">См. также</span><span class="sxs-lookup"><span data-stu-id="12cad-119">See also</span></span>

- [<span data-ttu-id="12cad-120">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="12cad-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="12cad-121">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="12cad-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="12cad-122">Функция CType</span><span class="sxs-lookup"><span data-stu-id="12cad-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
