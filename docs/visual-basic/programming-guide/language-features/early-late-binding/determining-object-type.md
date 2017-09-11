---
title: "Определение типа объекта (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fec7a275029dde469425b651d5b1220cb21ddbf6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="f0d8a-102">Определение типа объекта (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0d8a-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="f0d8a-103">Универсальные объектные переменные (то есть переменные можно объявить как `Object`) содержат объекты любого класса.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="f0d8a-104">При использовании переменных типа `Object`, может потребоваться предпринять различные действия в зависимости от класса объекта; например, некоторые объекты не поддерживают определенное свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f0d8a-105">предоставляет два средства определения типа объекта, хранящегося в переменной объекта: `TypeName` функции и `TypeOf...Is` оператор.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="f0d8a-106">TypeName и TypeOf... —</span><span class="sxs-lookup"><span data-stu-id="f0d8a-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="f0d8a-107">`TypeName` Функция возвращает строку и лучше всего подходит при необходимости хранить или отображать имя класса объекта, как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="f0d8a-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="f0d8a-108">[!code-vb[VbVbalrOOP&#92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0d8a-108">[!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span></span>  
  
 <span data-ttu-id="f0d8a-109">`TypeOf...Is` Оператор лучше всего подходит для тестирования тип объекта, так как он работает намного быстрее, чем эквивалентное строковое сравнение с помощью `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-109">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="f0d8a-110">В следующем фрагменте кода используется `TypeOf...Is` в `If...Then...Else` инструкции:</span><span class="sxs-lookup"><span data-stu-id="f0d8a-110">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 <span data-ttu-id="f0d8a-111">[!code-vb[VbVbalrOOP&#93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0d8a-111">[!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span></span>  
  
 <span data-ttu-id="f0d8a-112">Здесь в качестве предупреждения должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-112">A word of caution is due here.</span></span> <span data-ttu-id="f0d8a-113">`TypeOf...Is` Оператор возвращает `True` , если объект имеет конкретный тип или является производным от конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-113">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="f0d8a-114">Почти все в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняется с помощью объектов, содержащих некоторые элементы, которые не считаются обычно объектами, например строки и целые числа.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-114">Almost everything you do with [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="f0d8a-115">Эти объекты являются производными и наследуют методы от <xref:System.Object>.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="f0d8a-115">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="f0d8a-116">При передаче `Integer` и вычислении с `Object`, `TypeOf...Is` оператор возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-116">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="f0d8a-117">В следующем примере сообщается, что параметр `InParam` одновременно `Object` и `Integer`:</span><span class="sxs-lookup"><span data-stu-id="f0d8a-117">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 <span data-ttu-id="f0d8a-118">[!code-vb[VbVbalrOOP&#94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0d8a-118">[!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span></span>  
  
 <span data-ttu-id="f0d8a-119">В следующем примере оба `TypeOf...Is` и `TypeName` для определения типа объекта, переданного в `Ctrl` аргумент.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-119">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="f0d8a-120">`TestObject` Вызовы процедур `ShowType` с три различных типа элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-120">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="f0d8a-121">Запуск примера</span><span class="sxs-lookup"><span data-stu-id="f0d8a-121">To run the example</span></span>  
  
1.  <span data-ttu-id="f0d8a-122">Создание нового проекта приложения Windows и добавление <xref:System.Windows.Forms.Button>управления <xref:System.Windows.Forms.CheckBox>управления и <xref:System.Windows.Forms.RadioButton>на форму элемент управления.</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f0d8a-122">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="f0d8a-123">С помощью кнопки на форме вызовите `TestObject` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f0d8a-123">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="f0d8a-124">Добавьте следующий код в форму:</span><span class="sxs-lookup"><span data-stu-id="f0d8a-124">Add the following code to your form:</span></span>  
  
     <span data-ttu-id="f0d8a-125">[!code-vb[VbVbalrOOP&#95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0d8a-125">[!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d8a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f0d8a-126">See Also</span></span>  
 <span data-ttu-id="f0d8a-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A></span><span class="sxs-lookup"><span data-stu-id="f0d8a-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></span></span>   
<span data-ttu-id="f0d8a-128"> [Вызов свойства или метода с помощью строкового имени](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span><span class="sxs-lookup"><span data-stu-id="f0d8a-128"> [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span></span>  
<span data-ttu-id="f0d8a-129"> [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="f0d8a-129"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="f0d8a-130"> [If... Затем... Оператор else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f0d8a-130"> [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span></span>  
<span data-ttu-id="f0d8a-131"> [Тип данных String](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="f0d8a-131"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="f0d8a-132"> [Тип данных Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f0d8a-132"> [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span></span>
