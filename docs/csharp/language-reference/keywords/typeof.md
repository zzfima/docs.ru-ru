---
title: "typeof (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="74693-102">typeof (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="74693-102">typeof (C# Reference)</span></span>
<span data-ttu-id="74693-103">Позволяет получить объект `System.Type` для типа.</span><span class="sxs-lookup"><span data-stu-id="74693-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="74693-104">Выражение `typeof` принимает следующую форму:</span><span class="sxs-lookup"><span data-stu-id="74693-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="74693-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="74693-105">Remarks</span></span>  
 <span data-ttu-id="74693-106">Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="74693-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="74693-107">Оператор `typeof` перегрузить нельзя.</span><span class="sxs-lookup"><span data-stu-id="74693-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="74693-108">Оператор `typeof` можно также применять к открытым универсальным типам.</span><span class="sxs-lookup"><span data-stu-id="74693-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="74693-109">Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации.</span><span class="sxs-lookup"><span data-stu-id="74693-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="74693-110">В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="74693-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="74693-111">Предположим, что метод является экземпляром типа MethodInfo:</span><span class="sxs-lookup"><span data-stu-id="74693-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="74693-112">Пример</span><span class="sxs-lookup"><span data-stu-id="74693-112">Example</span></span>  
 <span data-ttu-id="74693-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="74693-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="74693-114">Пример</span><span class="sxs-lookup"><span data-stu-id="74693-114">Example</span></span>  
 <span data-ttu-id="74693-115">В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления.</span><span class="sxs-lookup"><span data-stu-id="74693-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="74693-116">Он зависит от требований к хранилищу для полученного числа.</span><span class="sxs-lookup"><span data-stu-id="74693-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="74693-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="74693-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="74693-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="74693-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74693-119">См. также</span><span class="sxs-lookup"><span data-stu-id="74693-119">See Also</span></span>  
 <span data-ttu-id="74693-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="74693-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="74693-121">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="74693-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="74693-122">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="74693-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="74693-123">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="74693-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="74693-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="74693-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="74693-125">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="74693-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

