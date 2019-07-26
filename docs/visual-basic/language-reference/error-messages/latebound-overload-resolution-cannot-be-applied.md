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
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a>Невозможно применить разрешение перегрузки с привязывания к "\<ProcedureName >", так как доступ к экземпляру является типом интерфейса

Компилятор пытается разрешить ссылку на Перегруженное свойство или процедуру, но ссылка завершается ошибкой, поскольку аргумент имеет тип `Object` , а ссылающийся объект имеет тип данных интерфейса. `Object` Аргумент заставляет компилятор разрешить ссылку с поздней привязкой.

В этих случаях компилятор разрешает перегрузку через реализующий класс, а не через базовый интерфейс. Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию как перегрузку, поскольку ее имя отличается. Это, в свою очередь, приводит к тому, что компилятор пропускает переименованную версию, когда она могла быть правильно выбрана для разрешения ссылки.

**Идентификатор ошибки:** BC30933

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте `CType` для приведения `Object` аргумента к типу, указанному в сигнатуре перегрузки, которую требуется вызвать.

  Обратите внимание, что он не помогает привести ссылающийся объект к базовому интерфейсу. Чтобы избежать этой ошибки, необходимо привести аргумент.

## <a name="example"></a>Пример

В следующем примере показан вызов перегруженной `Sub` процедуры, которая вызывает эту ошибку во время компиляции.

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

В предыдущем примере, если компилятор разрешил вызов `s1` как написанный, разрешение будет происходить через класс `c1` вместо интерфейса `i1`. Это означает, что компилятор не будет считать `s2` , что его имя отличается в, несмотря на то, что это `i1`правильный вариант, как определено в `c1`.

Ошибку можно исправить, изменив вызов одной из следующих строк кода:

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

Каждая из приведенных выше строк кода явным образом приводит `Object` переменную `o1` к одному из типов параметров, определенных для перегрузок.

## <a name="see-also"></a>См. также

- [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Разрешение перегрузки](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
