---
title: "Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#)."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="b0dd5-102">Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#).</span><span class="sxs-lookup"><span data-stu-id="b0dd5-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="b0dd5-103">Метод <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> принимает два параметра: один для ключа и один для значения.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="b0dd5-104">Для инициализации <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` которой принимает несколько параметров, следует заключить каждый набор параметров в скобки, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-104">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0dd5-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b0dd5-105">Example</span></span>  
 <span data-ttu-id="b0dd5-106">В приведенном ниже примере <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-106">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span></span>  
  
 <span data-ttu-id="b0dd5-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b0dd5-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span></span>  
  
 <span data-ttu-id="b0dd5-108">Обратите внимание на две пары фигурных скобок в каждом элементе коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="b0dd5-109">Внутренняя пара фигурных скобок заключает инициализатор объекта `StudentName`, а внешняя пара — инициализатор пары "ключ-значение", которая будет добавлена в коллекцию `students`<xref:System.Collections.Generic.Dictionary\`2>.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary\`2>.</span></span> <span data-ttu-id="b0dd5-110">И наконец, весь инициализатор коллекции для словаря заключается в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b0dd5-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b0dd5-111">Compiling the Code</span></span>  
 <span data-ttu-id="b0dd5-112">Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, которое было создано в [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0dd5-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="b0dd5-113">По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву using для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="b0dd5-114">Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="b0dd5-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="b0dd5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b0dd5-115">See Also</span></span>  
 <span data-ttu-id="b0dd5-116">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0dd5-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b0dd5-117">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="b0dd5-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

