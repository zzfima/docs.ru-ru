---
title: "Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ce063a70ced98fd8b99b4b46d704e08ddc96e10
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="5146b-102">Упаковка-преобразование типов, допускающих значение NULL (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5146b-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="5146b-103">Объекты на основе типов, допускающих значения NULL, могут быть упакованы, только если объект имеет значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="5146b-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="5146b-104">Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, ссылке на объект присваивается `null` и упаковка-преобразование не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5146b-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="5146b-105">Например:</span><span class="sxs-lookup"><span data-stu-id="5146b-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="5146b-106">Объект имеет значение, отличное от NULL, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`, выполняется упаковка-преобразование, однако упаковывается только базовый тип, который лежит в основе объекта, допускающего значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5146b-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="5146b-107">При упаковке-преобразовании ненулевого типа значения, допускающего NULL, происходит упаковка самого типа значения, а не <xref:System.Nullable%601?displayProperty=fullName>, который упаковывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="5146b-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=fullName> that wraps the value type.</span></span> <span data-ttu-id="5146b-108">Например:</span><span class="sxs-lookup"><span data-stu-id="5146b-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="5146b-109">Два упакованных объекта идентичны объектам, созданным при упаковке-преобразовании типов со значениями, отличными от NULL.</span><span class="sxs-lookup"><span data-stu-id="5146b-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="5146b-110">И так же, как и упакованные типы со значениями, отличными от NULL, они могут быть распакованы в типы, допускающие значения NULL, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5146b-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="5146b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5146b-111">Remarks</span></span>  
 <span data-ttu-id="5146b-112">Поведение упакованных типов, допускающих значения NULL, предоставляет два преимущества:</span><span class="sxs-lookup"><span data-stu-id="5146b-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="5146b-113">Объекты, допускающие значения NULL и их упакованные аналоги, можно проверить на наличие значения NULL:</span><span class="sxs-lookup"><span data-stu-id="5146b-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
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
  
2.  <span data-ttu-id="5146b-114">Упакованные типы, допускающие значения NULL, полностью поддерживают функциональность базового типа:</span><span class="sxs-lookup"><span data-stu-id="5146b-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5146b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5146b-115">See Also</span></span>  
 <span data-ttu-id="5146b-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5146b-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5146b-117">[Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="5146b-117">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="5146b-118">Практическое руководство. Идентификация типа, допускающего значение NULL</span><span class="sxs-lookup"><span data-stu-id="5146b-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)

