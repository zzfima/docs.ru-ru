---
title: Практическое руководство. Руководство по программированию на C#. Явная реализация членов интерфейса
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5ef8b42fe5ca07548d52b88720ea4845d2408bb1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589204"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="bd657-102">Практическое руководство. Руководство по программированию на C#. Явная реализация членов интерфейса</span><span class="sxs-lookup"><span data-stu-id="bd657-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="bd657-103">В этом примере объявляются [интерфейс](../../language-reference/keywords/interface.md) `IDimensions` и класс `Box`, который явно реализует члены интерфейса `getLength` и `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="bd657-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="bd657-104">Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="bd657-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd657-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bd657-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="bd657-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="bd657-106">Robust Programming</span></span>  
  
- <span data-ttu-id="bd657-107">Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки.</span><span class="sxs-lookup"><span data-stu-id="bd657-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="bd657-108">Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="bd657-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="bd657-109">Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="bd657-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="bd657-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bd657-110">See also</span></span>

- [<span data-ttu-id="bd657-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bd657-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bd657-112">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="bd657-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="bd657-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="bd657-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="bd657-114">Практическое руководство. Явная реализация элементов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="bd657-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
