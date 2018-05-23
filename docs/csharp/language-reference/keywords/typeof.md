---
title: typeof (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 4203b597d7045a13ffed9e61ddbbde57e2113c23
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="typeof-c-reference"></a><span data-ttu-id="3cea8-102">typeof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3cea8-102">typeof (C# Reference)</span></span>
<span data-ttu-id="3cea8-103">Позволяет получить объект `System.Type` для типа.</span><span class="sxs-lookup"><span data-stu-id="3cea8-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="3cea8-104">Выражение `typeof` принимает следующую форму:</span><span class="sxs-lookup"><span data-stu-id="3cea8-104">A `typeof` expression takes the following form:</span></span>  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3cea8-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cea8-105">Remarks</span></span>  
 <span data-ttu-id="3cea8-106">Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3cea8-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="3cea8-107">Оператор `typeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="3cea8-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="3cea8-108">Оператор `typeof` можно также применять к открытым универсальным типам.</span><span class="sxs-lookup"><span data-stu-id="3cea8-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="3cea8-109">Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации.</span><span class="sxs-lookup"><span data-stu-id="3cea8-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="3cea8-110">В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="3cea8-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="3cea8-111">Предположим, что метод является экземпляром типа MethodInfo:</span><span class="sxs-lookup"><span data-stu-id="3cea8-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```csharp  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="3cea8-112">Пример</span><span class="sxs-lookup"><span data-stu-id="3cea8-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3cea8-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3cea8-113">Example</span></span>  
 <span data-ttu-id="3cea8-114">В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления.</span><span class="sxs-lookup"><span data-stu-id="3cea8-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="3cea8-115">Он зависит от требований к хранилищу для полученного числа.</span><span class="sxs-lookup"><span data-stu-id="3cea8-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3cea8-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3cea8-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cea8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3cea8-117">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 [<span data-ttu-id="3cea8-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3cea8-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3cea8-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3cea8-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3cea8-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="3cea8-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3cea8-121">is</span><span class="sxs-lookup"><span data-stu-id="3cea8-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="3cea8-122">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="3cea8-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
