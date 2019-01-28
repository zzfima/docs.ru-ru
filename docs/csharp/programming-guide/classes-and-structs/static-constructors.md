---
title: Руководство по программированию на C#. Статические конструкторы
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 74932c9a080a077a60ecbc45c997108afa176956
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676891"
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="b1a9b-102">Статические конструкторы (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="b1a9b-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="b1a9b-103">Статический конструктор используется для инициализации любых [статических](../../../csharp/language-reference/keywords/static.md) данных или для выполнения определенного действия, которое требуется выполнить только один раз.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="b1a9b-104">Он вызывается автоматически перед созданием первого экземпляра или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 <span data-ttu-id="b1a9b-105">Статические конструкторы обладают следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="b1a9b-106">Статический конструктор не принимает модификаторы доступа и не имеет параметров.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="b1a9b-107">Статический конструктор вызывается автоматически для инициализации [класса](../../../csharp/language-reference/keywords/class.md) перед созданием первого экземпляра типа или ссылкой на какие-либо статические члены.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="b1a9b-108">Статический конструктор нельзя вызывать напрямую.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="b1a9b-109">Пользователь не управляет временем, в течение которого статический конструктор выполняется в программе.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="b1a9b-110">Типичным использованием статических конструкторов является случай, когда класс использует файл журнала и конструктор применяется для добавления записей в этот файл.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="b1a9b-111">Статические конструкторы также полезны при создании классов-оболочек для неуправляемого кода, когда конструктор может вызвать метод `LoadLibrary`.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="b1a9b-112">Если статический конструктор инициирует исключение, среда выполнения не вызывает его во второй раз, и тип остается неинициализированным на время существования домена приложения, в котором выполняется программа.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1a9b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="b1a9b-113">Example</span></span>  
 <span data-ttu-id="b1a9b-114">В этом примере класс `Bus` имеет статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="b1a9b-115">При создании первого экземпляра класса `Bus` (`bus1`) для инициализации класса вызывается статический конструктор.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="b1a9b-116">В выходных данных этого примера можно увидеть, что статический конструктор выполняется только один раз, несмотря на то, что создается два экземпляра класса `Bus`. Кроме того, этот конструктор вызывается до выполнения конструктора экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b1a9b-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b1a9b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b1a9b-117">See also</span></span>

- [<span data-ttu-id="b1a9b-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b1a9b-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b1a9b-119">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="b1a9b-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="b1a9b-120">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="b1a9b-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="b1a9b-121">Статические классы и члены статических классов</span><span class="sxs-lookup"><span data-stu-id="b1a9b-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="b1a9b-122">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="b1a9b-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
