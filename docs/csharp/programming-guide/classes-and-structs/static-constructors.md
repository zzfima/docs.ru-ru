---
title: Руководство по программированию на C#. Статические конструкторы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 110d83caad0c588fa899a4129897784e9c74aab8
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881914"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="a4554-102">Статические конструкторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="a4554-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="a4554-103">Статический конструктор используется для инициализации любых [статических](../../../csharp/language-reference/keywords/static.md) данных или для выполнения определенного действия, которое требуется выполнить только один раз.</span><span class="sxs-lookup"><span data-stu-id="a4554-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="a4554-104">Он вызывается автоматически перед созданием первого экземпляра или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="a4554-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
  
 <span data-ttu-id="a4554-105">Статические конструкторы обладают следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="a4554-105">Static constructors have the following properties:</span></span>  
  
- <span data-ttu-id="a4554-106">Статический конструктор не принимает модификаторы доступа и не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="a4554-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
- <span data-ttu-id="a4554-107">Статический конструктор вызывается автоматически для инициализации [класса](../../../csharp/language-reference/keywords/class.md) перед созданием первого экземпляра типа или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="a4554-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span> <span data-ttu-id="a4554-108">Обратите внимание на то, что статический конструктор типа вызывается при вызове статического метода, назначенного делегату или событию, а не при его назначении.</span><span class="sxs-lookup"><span data-stu-id="a4554-108">Note that a type's static constructor is called when a static method assigned to an event or a delegate is invoked and not when it is assigned.</span></span>
  
- <span data-ttu-id="a4554-109">Статический конструктор нельзя вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="a4554-109">A static constructor cannot be called directly.</span></span>  
  
- <span data-ttu-id="a4554-110">Пользователь не управляет временем, в течение которого статический конструктор выполняется в программе.</span><span class="sxs-lookup"><span data-stu-id="a4554-110">The user has no control on when the static constructor is executed in the program.</span></span>  
  
- <span data-ttu-id="a4554-111">Типичным использованием статических конструкторов является случай, когда класс использует файл журнала и конструктор применяется для добавления записей в этот файл.</span><span class="sxs-lookup"><span data-stu-id="a4554-111">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
- <span data-ttu-id="a4554-112">Статические конструкторы также полезны при создании классов-оболочек для неуправляемого кода, когда конструктор может вызвать метод `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="a4554-112">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
- <span data-ttu-id="a4554-113">Если статический конструктор инициирует исключение, среда выполнения не вызывает его во второй раз, и тип остается неинициализированным на время существования домена приложения, в котором выполняется программа.</span><span class="sxs-lookup"><span data-stu-id="a4554-113">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4554-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a4554-114">Example</span></span>  
 <span data-ttu-id="a4554-115">В этом примере класс `Bus` имеет статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="a4554-115">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="a4554-116">При создании первого экземпляра класса `Bus` (`bus1`) для инициализации класса вызывается статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="a4554-116">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="a4554-117">В выходных данных этого примера можно увидеть, что статический конструктор выполняется только один раз, несмотря на то, что создается два экземпляра класса `Bus`. Кроме того, этот конструктор вызывается до выполнения конструктора экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a4554-117">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]  
  
## <a name="see-also"></a><span data-ttu-id="a4554-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a4554-118">See also</span></span>

- [<span data-ttu-id="a4554-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a4554-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a4554-120">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="a4554-120">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="a4554-121">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="a4554-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="a4554-122">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="a4554-122">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="a4554-123">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="a4554-123">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
