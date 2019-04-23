---
title: Практическое руководство. Определить, какой тип, переменная объекта ссылается на (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342873"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="e3ab5-102">Практическое руководство. Определить, какой тип, переменная объекта ссылается на (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3ab5-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="e3ab5-103">Объектная переменная содержит указатель на данные, которые хранятся в другом месте.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="e3ab5-104">Тип данных можно изменить во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-104">The type of that data can change during run time.</span></span> <span data-ttu-id="e3ab5-105">В любой момент, можно использовать <xref:System.Type.GetTypeCode%2A> метод для определения текущего типа времени выполнения или [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) чтобы определить текущий тип времени выполнения совместим с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="e3ab5-106">Для определения точного типа переменной объекта в данный момент ссылается на</span><span class="sxs-lookup"><span data-stu-id="e3ab5-106">To determine the exact type an object variable currently refers to</span></span>  
  
1. <span data-ttu-id="e3ab5-107">В объектной переменной, вызывать метод <xref:System.Object.GetType%2A> метод для извлечения <xref:System.Type?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. <span data-ttu-id="e3ab5-108">На <xref:System.Type?displayProperty=nameWithType> вызовите общий метод <xref:System.Type.GetTypeCode%2A> извлекаемого <xref:System.TypeCode> значение перечисления для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="e3ab5-109">Вы можете протестировать <xref:System.TypeCode> члена перечисления представляют интерес, такие как значение перечисления `Double`.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="e3ab5-110">Чтобы определить, является ли объект тип переменной совместим с указанным типом</span><span class="sxs-lookup"><span data-stu-id="e3ab5-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="e3ab5-111">Используйте `TypeOf` оператор в сочетании с [оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) проверяемый объект с `TypeOf`... `Is` выражение.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="e3ab5-112">`TypeOf`... `Is` возвращает значение `True` совместим ли объект во время выполнения тип с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="e3ab5-113">Критерий совместимости зависит от того, является ли указанный тип класса, структуры или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="e3ab5-114">Как правило типы совместимы, если объект имеет тот же тип, что, наследует или реализует заданный тип.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="e3ab5-115">Дополнительные сведения см. в разделе [оператор TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="e3ab5-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e3ab5-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e3ab5-116">Compiling the Code</span></span>  
 <span data-ttu-id="e3ab5-117">Обратите внимание на то, что указанный тип не может быть переменной или выражением.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="e3ab5-118">Оно должно быть имя определенного типа, например класс, структура или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="e3ab5-119">Сюда входят встроенные типы, такие как `Integer` и `String`.</span><span class="sxs-lookup"><span data-stu-id="e3ab5-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ab5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ab5-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="e3ab5-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="e3ab5-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="e3ab5-122">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="e3ab5-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="e3ab5-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="e3ab5-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
