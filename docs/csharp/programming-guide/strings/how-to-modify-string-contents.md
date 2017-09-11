---
title: "Практическое руководство. Изменение содержимого строки (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 16
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
ms.openlocfilehash: 114b6fdabd235d7e57947e77b672352e28aff11e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="614bb-102">Практическое руководство. Изменение содержимого строки (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="614bb-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="614bb-103">Поскольку строки являются *неизменяемыми*, после создания строкового объекта нельзя изменить его значение без использования небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="614bb-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="614bb-104">Тем не менее есть множество способов изменить значение строки и сохранить результат в новом строковом объекте.</span><span class="sxs-lookup"><span data-stu-id="614bb-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="614bb-105">В классе <xref:System.String?displayProperty=fullName> представлены методы, которые позволяют работать с входной строкой и вернуть новый строковый объект.</span><span class="sxs-lookup"><span data-stu-id="614bb-105">The <xref:System.String?displayProperty=fullName> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="614bb-106">Во многих случаях новый объект можно присвоить переменной, содержащей исходную строку.</span><span class="sxs-lookup"><span data-stu-id="614bb-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="614bb-107">Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> предоставляет дополнительные методы, работающие аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="614bb-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="614bb-108">Класс <xref:System.Text.StringBuilder?displayProperty=fullName> предоставляет буфер символов, который можно изменять на месте.</span><span class="sxs-lookup"><span data-stu-id="614bb-108">The <xref:System.Text.StringBuilder?displayProperty=fullName> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="614bb-109">При вызове метода <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> создается новый строковый объект, в который помещается текущее содержимое буфера.</span><span class="sxs-lookup"><span data-stu-id="614bb-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=fullName> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="614bb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="614bb-110">Example</span></span>  
 <span data-ttu-id="614bb-111">В следующем примере показаны различные способы замены или удаления подстрок в указанной строке.</span><span class="sxs-lookup"><span data-stu-id="614bb-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 <span data-ttu-id="614bb-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="614bb-112">[!code-cs[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="614bb-113">Пример</span><span class="sxs-lookup"><span data-stu-id="614bb-113">Example</span></span>  
 <span data-ttu-id="614bb-114">Для доступа к отдельным символам строки с применением нотации массива можно использовать объект <xref:System.Text.StringBuilder>, который перегружает оператор `[]` для доступа к его внутреннему буферу символов.</span><span class="sxs-lookup"><span data-stu-id="614bb-114">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="614bb-115">Также можно преобразовать строку в массив символов с помощью метода <xref:System.String.ToCharArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="614bb-115">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="614bb-116">В следующем примере с помощью метода `ToCharArray` создается массив.</span><span class="sxs-lookup"><span data-stu-id="614bb-116">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="614bb-117">После этого некоторые элементы массива изменяются.</span><span class="sxs-lookup"><span data-stu-id="614bb-117">Some elements of this array are then modified.</span></span> <span data-ttu-id="614bb-118">Затем вызывается конструктор строки, который принимает в качестве входного параметра массив символов и создает новую строку.</span><span class="sxs-lookup"><span data-stu-id="614bb-118">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 <span data-ttu-id="614bb-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="614bb-119">[!code-cs[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="614bb-120">Пример</span><span class="sxs-lookup"><span data-stu-id="614bb-120">Example</span></span>  
 <span data-ttu-id="614bb-121">В следующем примере показана редкая ситуация, в которой требуется изменить строку на месте с использованием небезопасного кода аналогично массивам символов в языке C.</span><span class="sxs-lookup"><span data-stu-id="614bb-121">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="614bb-122">В этом примере демонстрируется доступ к отдельным символам на месте с помощью ключевого слова fixed.</span><span class="sxs-lookup"><span data-stu-id="614bb-122">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="614bb-123">Также здесь показан один из возможных побочных эффектов, связанных с выполнением небезопасных операций со строками, причиной которого является интернирование (внутреннее сохранение) строк компилятором C#.</span><span class="sxs-lookup"><span data-stu-id="614bb-123">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="614bb-124">В общем случае этот способ следует использовать только при крайней необходимости.</span><span class="sxs-lookup"><span data-stu-id="614bb-124">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="614bb-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="614bb-125">[!code-cs[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614bb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="614bb-126">See Also</span></span>  
 <span data-ttu-id="614bb-127">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="614bb-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="614bb-128">Строки</span><span class="sxs-lookup"><span data-stu-id="614bb-128">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

