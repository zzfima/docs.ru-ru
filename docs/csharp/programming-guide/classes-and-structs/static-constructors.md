---
title: "Статические конструкторы (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: 23
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
ms.openlocfilehash: 73df76c61f393bf5fe09af66935acfbac4b5663f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="8eb40-102">Статические конструкторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="8eb40-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="8eb40-103">Статический конструктор используется для инициализации любых [статических](../../../csharp/language-reference/keywords/static.md) данных или для выполнения определенного действия, которое требуется выполнить только один раз.</span><span class="sxs-lookup"><span data-stu-id="8eb40-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="8eb40-104">Он вызывается автоматически перед созданием первого экземпляра или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="8eb40-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 <span data-ttu-id="8eb40-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8eb40-105">[!code-cs[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="8eb40-106">Статические конструкторы обладают следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="8eb40-106">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="8eb40-107">Статический конструктор не принимает модификаторы доступа и не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="8eb40-107">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="8eb40-108">Статический конструктор вызывается автоматически для инициализации [класса](../../../csharp/language-reference/keywords/class.md) перед созданием первого экземпляра типа или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="8eb40-108">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="8eb40-109">Статический конструктор нельзя вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="8eb40-109">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="8eb40-110">Пользователь не управляет временем, в течение которого статический конструктор выполняется в программе.</span><span class="sxs-lookup"><span data-stu-id="8eb40-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="8eb40-111">Типичным использованием статических конструкторов является случай, когда класс использует файл журнала и конструктор применяется для добавления записей в этот файл.</span><span class="sxs-lookup"><span data-stu-id="8eb40-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="8eb40-112">Статические конструкторы также полезны при создании классов-оболочек для неуправляемого кода, когда конструктор может вызвать метод `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="8eb40-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="8eb40-113">Если статический конструктор инициирует исключение, среда выполнения не вызывает его во второй раз, и тип остается неинициализированным на время существования домена приложения, в котором выполняется программа.</span><span class="sxs-lookup"><span data-stu-id="8eb40-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb40-114">Пример</span><span class="sxs-lookup"><span data-stu-id="8eb40-114">Example</span></span>  
 <span data-ttu-id="8eb40-115">В этом примере класс `Bus` имеет статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="8eb40-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="8eb40-116">При создании первого экземпляра класса `Bus` (`bus1`) для инициализации класса вызывается статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="8eb40-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="8eb40-117">В выходных данных этого примера можно увидеть, что статический конструктор выполняется только один раз, несмотря на то, что создается два экземпляра класса `Bus`. Кроме того, этот конструктор вызывается до выполнения конструктора экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8eb40-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 <span data-ttu-id="8eb40-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8eb40-118">[!code-cs[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb40-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8eb40-119">See Also</span></span>  
 <span data-ttu-id="8eb40-120">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8eb40-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8eb40-121">[Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="8eb40-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="8eb40-122">[Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="8eb40-122">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="8eb40-123">[Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="8eb40-123">[Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
 [<span data-ttu-id="8eb40-124">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="8eb40-124">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

