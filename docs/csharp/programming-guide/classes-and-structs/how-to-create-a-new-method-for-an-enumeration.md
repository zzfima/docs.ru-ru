---
title: Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 0d8e562342239c8ac3c53e05086ede9c234d0b63
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705656"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="da022-102">Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="da022-102">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="da022-103">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="da022-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da022-104">Пример</span><span class="sxs-lookup"><span data-stu-id="da022-104">Example</span></span>  
 <span data-ttu-id="da022-105">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="da022-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="da022-106">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="da022-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="da022-107">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="da022-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="da022-108">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="da022-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da022-109">См. также</span><span class="sxs-lookup"><span data-stu-id="da022-109">See also</span></span>

- [<span data-ttu-id="da022-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="da022-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="da022-111">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="da022-111">Extension Methods</span></span>](./extension-methods.md)
