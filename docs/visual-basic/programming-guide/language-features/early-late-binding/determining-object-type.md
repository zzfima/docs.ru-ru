---
title: Определение типа объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302716"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="87727-102">Определение типа объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87727-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="87727-103">Универсальные объектные переменные (то есть переменные необходимо обозначить как `Object`) может содержать объекты любого класса.</span><span class="sxs-lookup"><span data-stu-id="87727-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="87727-104">При использовании переменных типа `Object`, может потребоваться предпринять различные действия на основе класса объекта; например, некоторые объекты могут не поддерживать определенное свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="87727-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="87727-105">Visual Basic предоставляет два средства определения типа объекта, хранящегося в переменной объекта: `TypeName` функции и `TypeOf...Is` оператор.</span><span class="sxs-lookup"><span data-stu-id="87727-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="87727-106">Имя типа и TypeOf... —</span><span class="sxs-lookup"><span data-stu-id="87727-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="87727-107">`TypeName` Функция возвращает строку и является лучшим выбором, если вам нужно хранить или отображать имя класса объекта, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="87727-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="87727-108">`TypeOf...Is` Оператор отлично подходит для тестирования тип объекта, так как это намного быстрее, чем в эквивалентное ему строковое сравнение с помощью `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="87727-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="87727-109">В следующем фрагменте кода используется `TypeOf...Is` в `If...Then...Else` инструкции:</span><span class="sxs-lookup"><span data-stu-id="87727-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="87727-110">Предупреждение здесь должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="87727-110">A word of caution is due here.</span></span> <span data-ttu-id="87727-111">`TypeOf...Is` Оператор возвращает `True` Если определенного типа, или объекта является производным от определенного типа.</span><span class="sxs-lookup"><span data-stu-id="87727-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="87727-112">Почти все, что делается с помощью Visual Basic включает в себя объекты, которые содержат элементы считаются не обычно объекты, такие как строки и целые числа.</span><span class="sxs-lookup"><span data-stu-id="87727-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="87727-113">Эти объекты являются производными от и наследуют методы из <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="87727-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="87727-114">При передаче `Integer` и вычислении с `Object`, `TypeOf...Is` оператор возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="87727-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="87727-115">В следующем примере сообщается, что параметр `InParam` одновременно `Object` и `Integer`:</span><span class="sxs-lookup"><span data-stu-id="87727-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="87727-116">В следующем примере используются оба `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в него в `Ctrl` аргумент.</span><span class="sxs-lookup"><span data-stu-id="87727-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="87727-117">`TestObject` Вызовы процедур `ShowType` с три различных типа элементов управления.</span><span class="sxs-lookup"><span data-stu-id="87727-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="87727-118">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="87727-118">To run the example</span></span>  
  
1. <span data-ttu-id="87727-119">Создайте новый проект приложения Windows и добавьте <xref:System.Windows.Forms.Button> управления <xref:System.Windows.Forms.CheckBox> элемента управления и <xref:System.Windows.Forms.RadioButton> на форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="87727-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="87727-120">С помощью кнопки на форме, вызовите `TestObject` процедуры.</span><span class="sxs-lookup"><span data-stu-id="87727-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="87727-121">Добавьте следующий код в форму:</span><span class="sxs-lookup"><span data-stu-id="87727-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="87727-122">См. также</span><span class="sxs-lookup"><span data-stu-id="87727-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="87727-123">Вызов свойства или метода с помощью строкового имени</span><span class="sxs-lookup"><span data-stu-id="87727-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="87727-124">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="87727-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="87727-125">Оператор If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="87727-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="87727-126">Тип данных String</span><span class="sxs-lookup"><span data-stu-id="87727-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="87727-127">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="87727-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
