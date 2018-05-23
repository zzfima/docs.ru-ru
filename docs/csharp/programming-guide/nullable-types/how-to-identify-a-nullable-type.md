---
title: Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f3ac4ebd77fc92a133eb326919d5ba55264ced97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="62613-102">Практическое руководство. Идентификация типа, допускающего значение NULL (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="62613-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="62613-103">С помощью оператора C# [typeof](../../../csharp/language-reference/keywords/typeof.md) можно создать объект <xref:System.Type>, который представляет тип, допускающий значения NULL:</span><span class="sxs-lookup"><span data-stu-id="62613-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="62613-104">Кроме того, можно использовать классы и методы из пространства имен <xref:System.Reflection> для создания объектов <xref:System.Type>, которые представляют типы, допускающие значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="62613-105">Тем не менее при попытке получить во время выполнения сведения о типе для переменных, допускающих значения NULL, используя метод <xref:System.Object.GetType%2A> оператора `is`, возвращается объект <xref:System.Type>, который представляет базовый тип, а не сам тип, допускающий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="62613-106">При вызове метода `GetType` для типа, допускающего значения NULL, выполняется операция упаковки-преобразования при неявном преобразовании типа в <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="62613-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="62613-107">Таким образом, метод <xref:System.Object.GetType%2A> всегда возвращает объект <xref:System.Type>, который представляет базовый тип, а не сам тип, допускающий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="62613-108">Оператор C# [is](../../../csharp/language-reference/keywords/is.md) также работает с базовым типом для типа, допускающего значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="62613-109">Поэтому нельзя использовать оператор `is`, чтобы определить, имеет ли переменная тип, допускающий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="62613-110">В следующем примере показано, что оператор `is` рассматривает переменную \<int>, допускающую значения NULL, как переменную int.</span><span class="sxs-lookup"><span data-stu-id="62613-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="62613-111">Пример</span><span class="sxs-lookup"><span data-stu-id="62613-111">Example</span></span>  
 <span data-ttu-id="62613-112">Следующий код позволяет определить, представляет ли объект <xref:System.Type> тип, допускающий значения NULL.</span><span class="sxs-lookup"><span data-stu-id="62613-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="62613-113">Обратите внимание, что этот код всегда возвращает значение false, если объект `Type` был возвращен из вызова <xref:System.Object.GetType%2A>, как описывается выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="62613-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="62613-114">См. также</span><span class="sxs-lookup"><span data-stu-id="62613-114">See Also</span></span>  
 [<span data-ttu-id="62613-115">Типы, допускающие значения NULL</span><span class="sxs-lookup"><span data-stu-id="62613-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="62613-116">Упаковка-преобразование типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="62613-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
