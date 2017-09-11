---
title: "Свойства интерфейса (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
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
ms.openlocfilehash: 2b76cdc4e8419b08dcd95c3711eaead5513ae1d9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="e7ef4-102">Свойства интерфейса (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e7ef4-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="e7ef4-103">Свойства можно объявлять для [интерфейса](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="e7ef4-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="e7ef4-104">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="e7ef4-104">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="e7ef4-105">[!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7ef4-105">[!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]</span></span>  
  
 <span data-ttu-id="e7ef4-106">Метод доступа свойства интерфейса не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-106">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="e7ef4-107">Таким образом, методы доступа нужны, чтобы указать, доступно ли свойство для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-107">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7ef4-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e7ef4-108">Example</span></span>  
 <span data-ttu-id="e7ef4-109">В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-109">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="e7ef4-110">Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-110">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="e7ef4-111">Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-111">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="e7ef4-112">Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-112">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="e7ef4-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="e7ef4-113">For example:</span></span>  
  
 <span data-ttu-id="e7ef4-114">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7ef4-114">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="e7ef4-115">Это называется [явной реализацией интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="e7ef4-115">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="e7ef4-116">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-116">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="e7ef4-117">Это значит, что потребуется следующее объявление свойства:</span><span class="sxs-lookup"><span data-stu-id="e7ef4-117">That is, the following property declaration:</span></span>  
  
 <span data-ttu-id="e7ef4-118">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7ef4-118">[!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="e7ef4-119">реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="e7ef4-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 <span data-ttu-id="e7ef4-120">[!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7ef4-120">[!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="e7ef4-121">реализует свойство `Name` в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="e7ef4-121">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 <span data-ttu-id="e7ef4-122">[!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7ef4-122">[!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]</span></span>  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="e7ef4-123">Пример результатов выполнения</span><span class="sxs-lookup"><span data-stu-id="e7ef4-123">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="e7ef4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e7ef4-124">See Also</span></span>  
 <span data-ttu-id="e7ef4-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7ef4-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e7ef4-126">[Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="e7ef4-126">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="e7ef4-127">[Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e7ef4-127">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="e7ef4-128">[Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="e7ef4-128">[Comparison Between Properties and Indexers](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md) </span></span>  
 <span data-ttu-id="e7ef4-129">[Индексаторы](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="e7ef4-129">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="e7ef4-130">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e7ef4-130">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

