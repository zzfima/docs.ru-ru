---
title: "Предупреждение компилятора CS3024"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f175d102fa8a05b7f8c0a787564b933ff81cdf6c
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="2265a-102">Предупреждение компилятора CS3024</span><span class="sxs-lookup"><span data-stu-id="2265a-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="2265a-103">Тип ограничения "тип" несовместим с CLS</span><span class="sxs-lookup"><span data-stu-id="2265a-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="2265a-104">Компилятор выдает это предупреждение, поскольку применение несовместимого с CLS типа в качестве как ограничения универсального типа может привести к невозможности использования этого универсального класса в коде, написанном на некоторых языках.</span><span class="sxs-lookup"><span data-stu-id="2265a-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="2265a-105">Устранение этого предупреждения</span><span class="sxs-lookup"><span data-stu-id="2265a-105">To eliminate this warning</span></span>  
  
1.  <span data-ttu-id="2265a-106">Используйте CLS-совместимый тип для ограничения типа.</span><span class="sxs-lookup"><span data-stu-id="2265a-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2265a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2265a-107">Example</span></span>  
 <span data-ttu-id="2265a-108">В следующем примере ошибка CS3024 возникает в нескольких местах:</span><span class="sxs-lookup"><span data-stu-id="2265a-108">The following example generates CS3024 in several locations:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2265a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2265a-109">See Also</span></span>  
 [<span data-ttu-id="2265a-110">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="2265a-110">Constraints on Type Parameters</span></span>](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
