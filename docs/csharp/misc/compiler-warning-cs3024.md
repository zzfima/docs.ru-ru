---
title: Предупреждение компилятора CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 7515fdd7bc8f57890e3f1aac6303ed4607cc2249
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61688258"
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="5d3e2-102">Предупреждение компилятора CS3024</span><span class="sxs-lookup"><span data-stu-id="5d3e2-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="5d3e2-103">Тип ограничения "тип" несовместим с CLS</span><span class="sxs-lookup"><span data-stu-id="5d3e2-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="5d3e2-104">Компилятор выдает это предупреждение, поскольку применение несовместимого с CLS типа в качестве как ограничения универсального типа может привести к невозможности использования этого универсального класса в коде, написанном на некоторых языках.</span><span class="sxs-lookup"><span data-stu-id="5d3e2-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="5d3e2-105">Устранение этого предупреждения</span><span class="sxs-lookup"><span data-stu-id="5d3e2-105">To eliminate this warning</span></span>  
  
1. <span data-ttu-id="5d3e2-106">Используйте CLS-совместимый тип для ограничения типа.</span><span class="sxs-lookup"><span data-stu-id="5d3e2-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d3e2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="5d3e2-107">Example</span></span>  
 <span data-ttu-id="5d3e2-108">В следующем примере ошибка CS3024 возникает в нескольких местах:</span><span class="sxs-lookup"><span data-stu-id="5d3e2-108">The following example generates CS3024 in several locations:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d3e2-109">См. также</span><span class="sxs-lookup"><span data-stu-id="5d3e2-109">See also</span></span>

- [<span data-ttu-id="5d3e2-110">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="5d3e2-110">Constraints on Type Parameters</span></span>](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
