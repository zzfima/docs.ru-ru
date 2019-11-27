---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347127"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="ccfc5-102">Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccfc5-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="ccfc5-103">Инициализаторы объектов позволяют объявлять и создавать экземпляры класса в одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="ccfc5-104">Кроме того, можно одновременно инициализировать один или несколько членов экземпляра без вызова параметризованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="ccfc5-105">При использовании инициализатора объекта для создания экземпляра именованного типа вызывается конструктор без параметров для класса, за которым следует инициализация назначенных членов в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-105">When you use an object initializer to create an instance of a named type, the parameterless constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="ccfc5-106">В следующей процедуре показано, как создать экземпляр класса `Student` тремя разными способами.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="ccfc5-107">У класса есть имя, фамилия и свойства года, кроме других.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="ccfc5-108">Каждое из трех объявлений создает новый экземпляр `Student`, где свойству `First` присвоено значение "Michael", свойству `Last` задано значение "Туккер", а всем остальным элементам задаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="ccfc5-109">Результат каждого объявления в процедуре эквивалентен следующему примеру, в котором не используется инициализатор объекта.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="ccfc5-110">Сведения о реализации класса `Student` см. в разделе [как создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="ccfc5-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="ccfc5-111">Вы можете скопировать код из этого раздела, чтобы настроить класс и создать список объектов `Student` для работы.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="ccfc5-112">Создание объекта именованного класса с помощью инициализатора объекта</span><span class="sxs-lookup"><span data-stu-id="ccfc5-112">To create an object of a named class by using an object initializer</span></span>  
  
1. <span data-ttu-id="ccfc5-113">Начните объявление, как если бы вы планировали использовать конструктор.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2. <span data-ttu-id="ccfc5-114">Введите ключевое слово `With`, за которым следует список инициализации в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. <span data-ttu-id="ccfc5-115">В списке инициализация Включите каждое свойство, которое необходимо инициализировать, и присвойте ему начальное значение.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="ccfc5-116">Имя свойства предшествует точке.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="ccfc5-117">Можно инициализировать один или несколько членов класса.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-117">You can initialize one or more members of the class.</span></span>  
  
4. <span data-ttu-id="ccfc5-118">Кроме того, можно объявить новый экземпляр класса и присвоить ему значение.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="ccfc5-119">Сначала объявите экземпляр `Student`:</span><span class="sxs-lookup"><span data-stu-id="ccfc5-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5. <span data-ttu-id="ccfc5-120">Начните создание экземпляра `Student` обычным способом.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6. <span data-ttu-id="ccfc5-121">Введите `With` и инициализатор объекта для инициализации одного или нескольких членов нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. <span data-ttu-id="ccfc5-122">Можно упростить определение на предыдущем шаге, опустив `As Student`.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="ccfc5-123">В этом случае компилятор определит, что `student3` является экземпляром `Student`, используя вывод локального типа.</span><span class="sxs-lookup"><span data-stu-id="ccfc5-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="ccfc5-124">Дополнительные сведения см. в разделе [определение локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="ccfc5-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfc5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ccfc5-125">See also</span></span>

- [<span data-ttu-id="ccfc5-126">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="ccfc5-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="ccfc5-127">Практическое руководство. Создание списка элементов</span><span class="sxs-lookup"><span data-stu-id="ccfc5-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="ccfc5-128">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="ccfc5-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="ccfc5-129">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="ccfc5-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
