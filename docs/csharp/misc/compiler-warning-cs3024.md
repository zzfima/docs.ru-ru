---
title: Предупреждение компилятора CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: c4c2f915d6172e3c30fc32c5c57fe9921c3f915d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280349"
---
# <a name="compiler-warning-cs3024"></a>Предупреждение компилятора CS3024
Тип ограничения "тип" несовместим с CLS  
  
 Компилятор выдает это предупреждение, поскольку применение несовместимого с CLS типа в качестве как ограничения универсального типа может привести к невозможности использования этого универсального класса в коде, написанном на некоторых языках.  
  
### <a name="to-eliminate-this-warning"></a>Устранение этого предупреждения  
  
1.  Используйте CLS-совместимый тип для ограничения типа.  
  
## <a name="example"></a>Пример  
 В следующем примере ошибка CS3024 возникает в нескольких местах:  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ограничения параметров типа](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
