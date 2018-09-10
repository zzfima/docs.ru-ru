---
title: typeof (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 2493e78fd0782eebee17afd979e1c429339d0a3f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529212"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="ef7ec-102">typeof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ef7ec-102">typeof (C# Reference)</span></span>
<span data-ttu-id="ef7ec-103">Позволяет получить объект `System.Type` для типа.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="ef7ec-104">Выражение `typeof` принимает следующую форму:</span><span class="sxs-lookup"><span data-stu-id="ef7ec-104">A `typeof` expression takes the following form:</span></span>  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="ef7ec-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef7ec-105">Remarks</span></span>  
 <span data-ttu-id="ef7ec-106">Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ef7ec-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="ef7ec-107">Оператор `typeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="ef7ec-108">Оператор `typeof` можно также применять к открытым универсальным типам.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="ef7ec-109">Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="ef7ec-110">В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="ef7ec-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> возвращает `null`, если тип возвращаемого значения не является универсальным типом <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a><span data-ttu-id="ef7ec-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ef7ec-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ef7ec-113">Пример</span><span class="sxs-lookup"><span data-stu-id="ef7ec-113">Example</span></span>  
 <span data-ttu-id="ef7ec-114">В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="ef7ec-115">Он зависит от требований к хранилищу для полученного числа.</span><span class="sxs-lookup"><span data-stu-id="ef7ec-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ef7ec-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="ef7ec-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ef7ec-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ef7ec-117">See Also</span></span>

- <xref:System.Type?displayProperty=nameWithType>  
- [<span data-ttu-id="ef7ec-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="ef7ec-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ef7ec-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ef7ec-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ef7ec-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="ef7ec-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ef7ec-121">is</span><span class="sxs-lookup"><span data-stu-id="ef7ec-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="ef7ec-122">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="ef7ec-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
