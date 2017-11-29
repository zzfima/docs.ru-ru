---
title: "Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 29fccba56f6758fdfd407fa1879baa9260b69187
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="f4420-102">Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f4420-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="f4420-103">Объекты на основе типов, допускающих значения NULL, могут быть упакованы, только если объект имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="f4420-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="f4420-104">Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, ссылке на объект присваивается `null` и упаковка-преобразование не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f4420-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="f4420-105">Например:</span><span class="sxs-lookup"><span data-stu-id="f4420-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="f4420-106">Объект имеет значение, отличное от NULL, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`, выполняется упаковка-преобразование, однако упаковывается только базовый тип, который лежит в основе объекта, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f4420-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="f4420-107">При упаковке-преобразовании ненулевого типа значения, допускающего NULL, происходит упаковка самого типа значения, а не <xref:System.Nullable%601?displayProperty=nameWithType>, который упаковывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="f4420-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=nameWithType> that wraps the value type.</span></span> <span data-ttu-id="f4420-108">Например:</span><span class="sxs-lookup"><span data-stu-id="f4420-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="f4420-109">Два упакованных объекта идентичны объектам, созданным при упаковке-преобразовании типов со значениями, отличными от NULL.</span><span class="sxs-lookup"><span data-stu-id="f4420-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="f4420-110">И так же, как и упакованные типы со значениями, отличными от NULL, они могут быть распакованы в типы, допускающие значения NULL, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f4420-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="f4420-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4420-111">Remarks</span></span>  
 <span data-ttu-id="f4420-112">Поведение упакованных типов, допускающих значения NULL, предоставляет два преимущества:</span><span class="sxs-lookup"><span data-stu-id="f4420-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="f4420-113">Объекты, допускающие значения NULL и их упакованные аналоги, можно проверить на наличие значения NULL:</span><span class="sxs-lookup"><span data-stu-id="f4420-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  <span data-ttu-id="f4420-114">Упакованные типы, допускающие значения NULL, полностью поддерживают функциональность базового типа:</span><span class="sxs-lookup"><span data-stu-id="f4420-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4420-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f4420-115">See Also</span></span>  
 [<span data-ttu-id="f4420-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f4420-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f4420-117">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="f4420-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="f4420-118">Практическое руководство. Идентификация типа, допускающего значение NULL</span><span class="sxs-lookup"><span data-stu-id="f4420-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
