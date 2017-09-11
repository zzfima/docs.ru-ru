---
title: "Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
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
ms.openlocfilehash: 88b96c15f724ee5961c72917308138a045988225
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="077ce-102">Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="077ce-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="077ce-103">В этом примере объявляются [интерфейс](../../../csharp/language-reference/keywords/interface.md) `IDimensions` и класс `Box`, который явно реализует члены интерфейса `getLength` и `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="077ce-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="077ce-104">Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="077ce-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="077ce-105">Пример</span><span class="sxs-lookup"><span data-stu-id="077ce-105">Example</span></span>  
 <span data-ttu-id="077ce-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="077ce-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="077ce-107">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="077ce-107">Robust Programming</span></span>  
  
-   <span data-ttu-id="077ce-108">Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки.</span><span class="sxs-lookup"><span data-stu-id="077ce-108">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="077ce-109">Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../../csharp/language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="077ce-109">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     <span data-ttu-id="077ce-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="077ce-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span></span>  
  
-   <span data-ttu-id="077ce-111">Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="077ce-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     <span data-ttu-id="077ce-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="077ce-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="077ce-113">См. также</span><span class="sxs-lookup"><span data-stu-id="077ce-113">See Also</span></span>  
 <span data-ttu-id="077ce-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="077ce-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="077ce-115">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="077ce-115">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="077ce-116">[Интерфейсы](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="077ce-116">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="077ce-117">Практическое руководство. Явная реализация членов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="077ce-117">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)

