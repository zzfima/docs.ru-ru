---
title: Разрешение перегрузки не может применяться к &#39; &lt;имя_процедуры&gt; &#39; , поскольку доступ осуществляется из типа интерфейса
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589884"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>Разрешение перегрузки не может применяться к &#39; &lt;имя_процедуры&gt; &#39; , поскольку доступ осуществляется из типа интерфейса
Компилятор пытается разрешить ссылку на перегруженного свойства или процедуры, но не выполняется, так как тип аргумента `Object` и ссылающийся объект имеет тип интерфейса. `Object` Аргумент указывает компилятору разрешить ссылку с поздней привязкой.  
  
 В этом случае компилятор разрешает перегрузку посредством реализующего класса вместо базового интерфейса. Если класс переименовывает одну из перегруженных версий, компилятор не учитывает эту версию в качестве перегрузку, так как его имя отличается. Это указывает компилятору игнорировать переименованную версию, когда было бы правильный выбор для разрешения ссылки.  
  
 **Идентификатор ошибки:** BC30933  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте `CType` для приведения аргументов `Object` типу, указанному в сигнатуре перегрузки, которые вы хотите вызвать.  
  
     Обратите внимание, что он не поможет приведение ссылающегося объекта базового интерфейса. Необходимо привести аргумент, чтобы избежать этой ошибки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано вызов перегруженной `Sub` процедура, которая вызывает эту ошибку во время компиляции.  
  
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
  
 В предыдущем примере, если компилятор разрешил вызов `s1` записи разрешение будет иметь место через класс `c1` вместо интерфейса `i1`. Это будет означать, что компилятор не будет учитывать `s2` , так как его имя отличается в `c1`, несмотря на то, что это правильный выбор в соответствии с определением `i1`.  
  
 Ошибку можно устранить путем изменения вызова одной из следующих строк кода:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Каждая из строк предыдущего кода явно приводит `Object` переменной `o1` к одному из типов параметров, определенных для перегрузки.  
  
## <a name="see-also"></a>См. также  
 [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Разрешение перегрузки](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)
