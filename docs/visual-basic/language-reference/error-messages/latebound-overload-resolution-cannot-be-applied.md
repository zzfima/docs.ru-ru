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
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>Разрешение перегрузки не может использоваться для &#39; &lt;имя_процедуры&gt; &#39; поскольку интерфейс доступа принадлежит к типу интерфейса
Компилятор пытается разрешить ссылку на перегруженное свойство или процедуру, но не выполняется, так как аргумент имеет тип `Object` и ссылающийся объект имеет тип данных интерфейса. `Object` Аргумент указывает компилятору разрешить ссылку с поздней привязкой.  
  
 В этих случаях компилятор разрешает перегрузку посредством реализации класса, а не базового интерфейса. Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию в качестве перегрузки, так как его имя отличается. Это указывает компилятору игнорировать переименованную версию, когда было бы разрешить ссылку на правильный выбор.  
  
 **Идентификатор ошибки:** BC30933  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте `CType` для приведения аргументов `Object` к типу, указанному в подписи перегрузки, необходимо вызвать.  
  
     Обратите внимание на то, что не дает им возможность привести ссылающийся объект базового интерфейса. Необходимо привести аргумент, чтобы избежать этой ошибки.  
  
## <a name="example"></a>Пример  
 В примере показан вызов перегруженной `Sub` процедуру, которая вызывает эту ошибку во время компиляции.  
  
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
  
 В предыдущем примере, если компилятор разрешил вызов `s1` записи разрешения будет выполняться через класс `c1` вместо интерфейса `i1`. Это будет означать, что компилятор не будет учитывать `s2` так, как его имя отличается в `c1`, несмотря на то, что это правильный выбор в соответствии с определением `i1`.  
  
 Ошибку можно исправить, изменив вызова одной из следующих строк кода:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Каждая из строк предыдущего кода явно приводит `Object` переменной `o1` к одному из типов параметров, определенных для перегрузок.  
  
## <a name="see-also"></a>См. также
- [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Разрешение перегрузки](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
