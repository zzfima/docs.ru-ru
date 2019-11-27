---
title: Практическое руководство. Определение типа, на который указывает объектная переменная
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 9f9b89e2fea0bd69cba6d50fa1d1fb9cc3927685
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348620"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="7ff75-102">Практическое руководство. Определение типа, на который указывает объектная переменная (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ff75-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="7ff75-103">Объектная переменная содержит указатель на данные, которые хранятся в других местах.</span><span class="sxs-lookup"><span data-stu-id="7ff75-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="7ff75-104">Тип этих данных может изменяться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7ff75-104">The type of that data can change during run time.</span></span> <span data-ttu-id="7ff75-105">В любой момент можно использовать метод <xref:System.Type.GetTypeCode%2A> для определения текущего типа времени выполнения или [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) , чтобы определить, совместим ли текущий тип времени выполнения с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="7ff75-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="7ff75-106">Определение точного типа объектной переменной, на которую в настоящее время ссылается</span><span class="sxs-lookup"><span data-stu-id="7ff75-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="7ff75-107">В объектной переменной вызовите метод <xref:System.Object.GetType%2A>, чтобы получить объект <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7ff75-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="7ff75-108">В классе <xref:System.Type?displayProperty=nameWithType> вызовите общий метод <xref:System.Type.GetTypeCode%2A>, чтобы получить значение перечисления <xref:System.TypeCode> для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="7ff75-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="7ff75-109">Можно проверить значение перечисления <xref:System.TypeCode> в отношении любого интересующего его члена, например `Double`.</span><span class="sxs-lookup"><span data-stu-id="7ff75-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="7ff75-110">Определение, совместима ли тип объектной переменной с указанным типом</span><span class="sxs-lookup"><span data-stu-id="7ff75-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="7ff75-111">Используйте оператор `TypeOf` в сочетании с [оператором is](../../../../visual-basic/language-reference/operators/is-operator.md) для проверки объекта с помощью выражения `TypeOf`...`Is`.</span><span class="sxs-lookup"><span data-stu-id="7ff75-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="7ff75-112">Выражение `TypeOf`...`Is` возвращает `True`, если тип времени выполнения объекта совместим с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="7ff75-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="7ff75-113">Критерий совместимости зависит от того, является ли указанный тип классом, структурой или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="7ff75-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="7ff75-114">Как правило, типы являются совместимыми, если объект имеет тот же тип, что и, наследует от или реализует указанный тип.</span><span class="sxs-lookup"><span data-stu-id="7ff75-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="7ff75-115">Дополнительные сведения см. в разделе [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7ff75-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="7ff75-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7ff75-116">Compiling the Code</span></span>

<span data-ttu-id="7ff75-117">Обратите внимание, что указанный тип не может быть переменной или выражением.</span><span class="sxs-lookup"><span data-stu-id="7ff75-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="7ff75-118">Это должно быть имя определенного типа, например класса, структуры или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7ff75-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="7ff75-119">Сюда входят встроенные типы, такие как `Integer` и `String`.</span><span class="sxs-lookup"><span data-stu-id="7ff75-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ff75-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7ff75-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="7ff75-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="7ff75-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="7ff75-122">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="7ff75-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="7ff75-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="7ff75-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
