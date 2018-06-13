---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649169"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="64a5b-102">Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64a5b-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="64a5b-103">Инициализаторы объектов позволяют объявлять и создавать экземпляр класса в одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="64a5b-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="64a5b-104">Кроме того можно инициализировать один или несколько членов экземпляра одновременно, без вызова конструктора с параметрами.</span><span class="sxs-lookup"><span data-stu-id="64a5b-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="64a5b-105">При использовании инициализатора объекта для создания экземпляра именованного типа, вызывается конструктор по умолчанию для класса, следуют инициализации назначенных членов в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="64a5b-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="64a5b-106">Ниже показано, как создать экземпляр `Student` класс тремя разными способами.</span><span class="sxs-lookup"><span data-stu-id="64a5b-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="64a5b-107">Класс имеет имя, фамилию и год свойства класса, в частности.</span><span class="sxs-lookup"><span data-stu-id="64a5b-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="64a5b-108">Каждый из трех объявлений создается новый экземпляр `Student`, со свойством `First` задается значение «Michael», свойство `Last` значение «Tucker», а других членов в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64a5b-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="64a5b-109">В следующем примере, в котором не используется инициализатор объекта соответствует результат каждого объявления в процедуре.</span><span class="sxs-lookup"><span data-stu-id="64a5b-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 <span data-ttu-id="64a5b-110">Для реализации `Student` см. в описании [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="64a5b-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="64a5b-111">Можно скопировать код из этого раздела, чтобы настроить класс и создать список `Student` объектов для работы с.</span><span class="sxs-lookup"><span data-stu-id="64a5b-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="64a5b-112">Для создания объекта именованного класса с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="64a5b-112">To create an object of a named class by using an object initializer</span></span>  
  
1.  <span data-ttu-id="64a5b-113">Начните объявление, как если бы планировалось использовать конструктор.</span><span class="sxs-lookup"><span data-stu-id="64a5b-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2.  <span data-ttu-id="64a5b-114">Введите ключевое слово `With`, а затем список инициализации в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="64a5b-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  <span data-ttu-id="64a5b-115">В списке инициализации укажите каждое свойство, который будет инициализировать и присвойте ему начальное значение.</span><span class="sxs-lookup"><span data-stu-id="64a5b-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="64a5b-116">Имя свойства предшествует периодом.</span><span class="sxs-lookup"><span data-stu-id="64a5b-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     <span data-ttu-id="64a5b-117">Можно инициализировать один или несколько членов класса.</span><span class="sxs-lookup"><span data-stu-id="64a5b-117">You can initialize one or more members of the class.</span></span>  
  
4.  <span data-ttu-id="64a5b-118">Кроме того можно объявить новый экземпляр класса и назначьте ему значение.</span><span class="sxs-lookup"><span data-stu-id="64a5b-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="64a5b-119">Сначала объявите экземпляр `Student`:</span><span class="sxs-lookup"><span data-stu-id="64a5b-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5.  <span data-ttu-id="64a5b-120">Начать создание экземпляра `Student` обычным способом.</span><span class="sxs-lookup"><span data-stu-id="64a5b-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6.  <span data-ttu-id="64a5b-121">Тип `With` и затем инициализатора объекта для инициализации одного или нескольких членов нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64a5b-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  <span data-ttu-id="64a5b-122">Упростить определение на предыдущем шаге, не указывайте `As Student`.</span><span class="sxs-lookup"><span data-stu-id="64a5b-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="64a5b-123">После этого компилятор определяет, что `student3` является экземпляром класса `Student` с помощью локального определения типов.</span><span class="sxs-lookup"><span data-stu-id="64a5b-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     <span data-ttu-id="64a5b-124">Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="64a5b-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a5b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="64a5b-125">See Also</span></span>  
 [<span data-ttu-id="64a5b-126">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="64a5b-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="64a5b-127">Практическое руководство. Создание списка элементов</span><span class="sxs-lookup"><span data-stu-id="64a5b-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [<span data-ttu-id="64a5b-128">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="64a5b-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="64a5b-129">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="64a5b-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
