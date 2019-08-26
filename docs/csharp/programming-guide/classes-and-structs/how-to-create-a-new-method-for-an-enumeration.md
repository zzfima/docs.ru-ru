---
title: Практическое руководство. Руководство по программированию на C#. Создание метода для перечисления
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 99a2005e1a64fa214776145a903341fb162f0633
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597041"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="ca125-102">Практическое руководство. Руководство по программированию на C#. Создание метода для перечисления</span><span class="sxs-lookup"><span data-stu-id="ca125-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="ca125-103">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="ca125-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca125-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ca125-104">Example</span></span>  
 <span data-ttu-id="ca125-105">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="ca125-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="ca125-106">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="ca125-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="ca125-107">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="ca125-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="ca125-108">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="ca125-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca125-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ca125-109">See also</span></span>

- [<span data-ttu-id="ca125-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ca125-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ca125-111">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="ca125-111">Extension Methods</span></span>](./extension-methods.md)
