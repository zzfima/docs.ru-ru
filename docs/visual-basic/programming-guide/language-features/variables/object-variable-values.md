---
title: "Объект значения переменной (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: 5f42706a79212ae523b08ee336fdcacb3f761af6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="8a05f-102">Значения объектных переменных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a05f-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="8a05f-103">Переменная [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md) может ссылаться на данные любого типа.</span><span class="sxs-lookup"><span data-stu-id="8a05f-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="8a05f-104">Значение, сохраненное в `Object` переменной хранится в памяти, а сама переменная содержит указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="8a05f-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="8a05f-105">Функции классификатора объектов</span><span class="sxs-lookup"><span data-stu-id="8a05f-105">Object Classifier Functions</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8a05f-106">предоставляет функции, которые возвращают сведения о том, что `Object` ссылается переменная, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8a05f-106"> supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="8a05f-107">Функция</span><span class="sxs-lookup"><span data-stu-id="8a05f-107">Function</span></span>|<span data-ttu-id="8a05f-108">Возвращает значение True, если переменная объекта ссылается на</span><span class="sxs-lookup"><span data-stu-id="8a05f-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<span data-ttu-id="8a05f-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></span></span>|<span data-ttu-id="8a05f-110">Массив значений, а не одно значение</span><span class="sxs-lookup"><span data-stu-id="8a05f-110">An array of values, rather than a single value</span></span>|  
|<span data-ttu-id="8a05f-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></span></span>|<span data-ttu-id="8a05f-112">Объект [тип данных Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) значение или строку, которая может быть интерпретирована как значение даты и времени</span><span class="sxs-lookup"><span data-stu-id="8a05f-112">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<span data-ttu-id="8a05f-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span></span>|<span data-ttu-id="8a05f-114">Объект типа <xref:System.DBNull>который представляет пропущенные или несуществующие данные</xref:System.DBNull></span><span class="sxs-lookup"><span data-stu-id="8a05f-114">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<span data-ttu-id="8a05f-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></span></span>|<span data-ttu-id="8a05f-116">Объект исключения, являющийся производным от<xref:System.Exception></xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="8a05f-116">An exception object, which derives from <xref:System.Exception></span></span>|  
|<span data-ttu-id="8a05f-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></span></span>|<span data-ttu-id="8a05f-118">[Ничего не](../../../../visual-basic/language-reference/nothing.md), то есть объект не назначено в настоящий момент в переменную</span><span class="sxs-lookup"><span data-stu-id="8a05f-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<span data-ttu-id="8a05f-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span></span>|<span data-ttu-id="8a05f-120">Число или строку, которое может быть интерпретировано как число</span><span class="sxs-lookup"><span data-stu-id="8a05f-120">A number, or a string that can be interpreted as a number</span></span>|  
|<span data-ttu-id="8a05f-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="8a05f-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></span></span>|<span data-ttu-id="8a05f-122">Ссылочный тип (например, строка, массив, делегат или тип класса)</span><span class="sxs-lookup"><span data-stu-id="8a05f-122">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="8a05f-123">Эти функции позволяют избежать передачи несуществующего значения оператору или процедуре.</span><span class="sxs-lookup"><span data-stu-id="8a05f-123">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="8a05f-124">Оператор TypeOf</span><span class="sxs-lookup"><span data-stu-id="8a05f-124">TypeOf Operator</span></span>  
 <span data-ttu-id="8a05f-125">Можно также использовать [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) определить, ссылается ли в данный момент переменная объекта для определенного типа данных.</span><span class="sxs-lookup"><span data-stu-id="8a05f-125">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="8a05f-126">The `TypeOf`... `Is` выражение `True` Если тип операнда во время выполнения является производным от указанного типа или реализует.</span><span class="sxs-lookup"><span data-stu-id="8a05f-126">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="8a05f-127">В следующем примере используется `TypeOf` на переменным объектов, ссылающимся на значение и ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="8a05f-127">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="8a05f-128">Предыдущий пример записывает следующие строки в **отладки** окна:</span><span class="sxs-lookup"><span data-stu-id="8a05f-128">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="8a05f-129">Объектная переменная `num` ссылается на данные типа `Integer`, и `frm` ссылается на объект класса <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="8a05f-129">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="8a05f-130">Массивы объектов</span><span class="sxs-lookup"><span data-stu-id="8a05f-130">Object Arrays</span></span>  
 <span data-ttu-id="8a05f-131">Можно объявить и использовать массив `Object` переменных.</span><span class="sxs-lookup"><span data-stu-id="8a05f-131">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="8a05f-132">Это полезно, когда необходимо обработать различные типы данных и классы объектов.</span><span class="sxs-lookup"><span data-stu-id="8a05f-132">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="8a05f-133">Все элементы массива должны иметь тот же объявленный тип данных.</span><span class="sxs-lookup"><span data-stu-id="8a05f-133">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="8a05f-134">Объявление этого типа данных как `Object` позволяет хранить объекты и экземпляры класса вместе с другими типами данных в массиве.</span><span class="sxs-lookup"><span data-stu-id="8a05f-134">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a05f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8a05f-135">See Also</span></span>  
 <span data-ttu-id="8a05f-136">[Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-136">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="8a05f-137"> [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-137"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="8a05f-138"> [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-138"> [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span></span>  
<span data-ttu-id="8a05f-139"> [Практическое руководство: ссылки на текущий экземпляр объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-139"> [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="8a05f-140"> [Практическое руководство: определение типа, который указывает объектная переменная](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-140"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="8a05f-141"> [Практическое руководство: определение связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-141"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="8a05f-142"> [Практическое руководство: Определение идентичности двух объектов](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span><span class="sxs-lookup"><span data-stu-id="8a05f-142"> [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span></span>  
<span data-ttu-id="8a05f-143"> [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="8a05f-143"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
