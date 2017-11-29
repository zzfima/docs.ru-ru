---
title: "Практическое руководство. Создание нового метода для перечисления (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3cc15d24c9ba954a19fb87d4e364ac6e7f78e8b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="da48a-102">Практическое руководство. Создание нового метода для перечисления (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="da48a-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="da48a-103">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="da48a-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da48a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="da48a-104">Example</span></span>  
 <span data-ttu-id="da48a-105">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="da48a-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="da48a-106">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="da48a-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 <span data-ttu-id="da48a-107">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="da48a-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="da48a-108">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="da48a-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da48a-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="da48a-109">Compiling the Code</span></span>  
 <span data-ttu-id="da48a-110">Чтобы выполнить этот код, скопируйте и вставьте его в проект консольного приложения Visual C#, созданный в [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da48a-110">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="da48a-111">По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="da48a-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="da48a-112">Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="da48a-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da48a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="da48a-113">See Also</span></span>  
 [<span data-ttu-id="da48a-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="da48a-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="da48a-115">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="da48a-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
