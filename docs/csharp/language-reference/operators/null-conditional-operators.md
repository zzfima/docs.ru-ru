---
title: "Операторы с условием NULL (C# и Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95b4079cf4e71c0ef9cd436ec230337f512229a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="4a1ac-102">Операторы с условием NULL (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a1ac-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="4a1ac-103">Используется для проверки на значения NULL перед выполнением операции доступа к элементу (`?.`) или операции индексирования (`?[`)</span><span class="sxs-lookup"><span data-stu-id="4a1ac-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="4a1ac-104">Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="4a1ac-105">Последний пример показывает, что операторы с условием NULL выполняют сокращенную обработку.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="4a1ac-106">Если одна операция в цепочке условных операций доступа к элементу и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки останавливается.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="4a1ac-107">Другие операции с более низким приоритетом в выражении продолжают выполняться.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="4a1ac-108">Например, `E` ниже выполняется во второй строке и выполняются операции `??` и `==`.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="4a1ac-109">В первой строке циклы `??` и `E` не выполняются, если результатом выполнения левой части является значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="4a1ac-110">Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="4a1ac-111">Для старого способа требуется примерно следующий код:</span><span class="sxs-lookup"><span data-stu-id="4a1ac-111">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="4a1ac-112">Новый способ гораздо проще:</span><span class="sxs-lookup"><span data-stu-id="4a1ac-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="4a1ac-113">Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="4a1ac-114">Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="4a1ac-115">Он приводил к слишком большому количеству неоднозначных ситуаций синтаксического анализа, поэтому он не разрешен.</span><span class="sxs-lookup"><span data-stu-id="4a1ac-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="4a1ac-116">Спецификации языков</span><span class="sxs-lookup"><span data-stu-id="4a1ac-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="4a1ac-117">Дополнительные сведения см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a1ac-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a1ac-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4a1ac-118">See Also</span></span>  
 [<span data-ttu-id="4a1ac-119">?? (оператор объединения с null)</span><span class="sxs-lookup"><span data-stu-id="4a1ac-119">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="4a1ac-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4a1ac-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4a1ac-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4a1ac-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4a1ac-122">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a1ac-122">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="4a1ac-123">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a1ac-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
