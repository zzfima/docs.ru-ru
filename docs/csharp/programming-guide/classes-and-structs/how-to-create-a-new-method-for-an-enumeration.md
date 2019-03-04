---
title: Как выполнить Руководство по программированию на C#. Создание метода для перечисления
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: ebd0433efda43c65ea6d9494a8ec25e8263f5b43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968131"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="3046e-102">Как выполнить Руководство по программированию на C#. Создание метода для перечисления</span><span class="sxs-lookup"><span data-stu-id="3046e-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="3046e-103">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="3046e-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3046e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3046e-104">Example</span></span>  
 <span data-ttu-id="3046e-105">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="3046e-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="3046e-106">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="3046e-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="3046e-107">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="3046e-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="3046e-108">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="3046e-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3046e-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3046e-109">Compiling the Code</span></span>  
 <span data-ttu-id="3046e-110">Чтобы выполнить этот код, скопируйте и вставьте его в проект консольного приложения Visual C#, созданный в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3046e-110">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="3046e-111">По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="3046e-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="3046e-112">Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="3046e-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3046e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3046e-113">See also</span></span>

- [<span data-ttu-id="3046e-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3046e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3046e-115">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="3046e-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
