---
title: "Общая структура программы на C# (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
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
ms.openlocfilehash: d55ac6a6d35e5f47ab26da681afe9fb5555331ec
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="e66f6-102">Общая структура программы на C# (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e66f6-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="e66f6-103">Программа на языке C# может состоять из одного или нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="e66f6-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="e66f6-104">Каждый файл может содержать нуль или несколько пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e66f6-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="e66f6-105">Пространство имен может содержать типы, такие как классы, структуры, интерфейсы, перечисления и делегаты, а также другие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e66f6-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="e66f6-106">Ниже приведена структура программы на C#, содержащей все эти элементы.</span><span class="sxs-lookup"><span data-stu-id="e66f6-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 <span data-ttu-id="e66f6-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e66f6-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e66f6-108">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e66f6-108">Related Sections</span></span>  
 <span data-ttu-id="e66f6-109">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="e66f6-109">For more information:</span></span>  
  
-   [<span data-ttu-id="e66f6-110">Классы</span><span class="sxs-lookup"><span data-stu-id="e66f6-110">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="e66f6-111">Структуры</span><span class="sxs-lookup"><span data-stu-id="e66f6-111">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="e66f6-112">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="e66f6-112">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="e66f6-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e66f6-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="e66f6-114">Делегаты</span><span class="sxs-lookup"><span data-stu-id="e66f6-114">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="e66f6-115">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="e66f6-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e66f6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e66f6-116">See Also</span></span>  
 <span data-ttu-id="e66f6-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e66f6-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e66f6-118">[Структура программы C#](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="e66f6-118">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="e66f6-119">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e66f6-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="e66f6-120">\<paveover>Примеры приложений C#</span><span class="sxs-lookup"><span data-stu-id="e66f6-120">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

