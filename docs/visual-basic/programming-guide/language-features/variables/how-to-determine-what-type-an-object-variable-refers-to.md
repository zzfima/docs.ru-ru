---
title: Практическое руководство. Определение типа, на который ссылается объектная переменная (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626570"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="0c249-102">Практическое руководство. Определение типа, на который ссылается объектная переменная (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c249-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="0c249-103">Объектная переменная содержит указатель на данные, которые хранятся в других местах.</span><span class="sxs-lookup"><span data-stu-id="0c249-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="0c249-104">Тип этих данных может изменяться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0c249-104">The type of that data can change during run time.</span></span> <span data-ttu-id="0c249-105">В любой момент можно использовать <xref:System.Type.GetTypeCode%2A> метод для определения текущего типа времени выполнения или [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) , чтобы определить, совместим ли текущий тип времени выполнения с указанным типом.</span><span class="sxs-lookup"><span data-stu-id="0c249-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="0c249-106">Определение точного типа объектной переменной, на которую в настоящее время ссылается</span><span class="sxs-lookup"><span data-stu-id="0c249-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="0c249-107">В объектной переменной вызовите <xref:System.Object.GetType%2A> метод, чтобы <xref:System.Type?displayProperty=nameWithType> получить объект.</span><span class="sxs-lookup"><span data-stu-id="0c249-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="0c249-108">В классе вызовите метод <xref:System.Type.GetTypeCode%2A> Shared, чтобы получить <xref:System.TypeCode> значение перечисления для типа объекта. <xref:System.Type?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c249-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="0c249-109">Можно проверить значение перечисления <xref:System.TypeCode> в отношении любого интересующего его члена, `Double`например.</span><span class="sxs-lookup"><span data-stu-id="0c249-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="0c249-110">Определение, совместима ли тип объектной переменной с указанным типом</span><span class="sxs-lookup"><span data-stu-id="0c249-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="0c249-111">Используйте оператор в сочетании с оператором [is](../../../../visual-basic/language-reference/operators/is-operator.md) для проверки объекта с помощью `TypeOf`... `TypeOf` `Is` выражение.</span><span class="sxs-lookup"><span data-stu-id="0c249-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="0c249-112">`TypeOf`... выражение возвращает `True` значение, если тип времени выполнения объекта совместим с указанным типом. `Is`</span><span class="sxs-lookup"><span data-stu-id="0c249-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="0c249-113">Критерий совместимости зависит от того, является ли указанный тип классом, структурой или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="0c249-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="0c249-114">Как правило, типы являются совместимыми, если объект имеет тот же тип, что и, наследует от или реализует указанный тип.</span><span class="sxs-lookup"><span data-stu-id="0c249-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="0c249-115">Дополнительные сведения см. в разделе [оператор typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0c249-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="0c249-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0c249-116">Compiling the Code</span></span>

<span data-ttu-id="0c249-117">Обратите внимание, что указанный тип не может быть переменной или выражением.</span><span class="sxs-lookup"><span data-stu-id="0c249-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="0c249-118">Это должно быть имя определенного типа, например класса, структуры или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0c249-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="0c249-119">Сюда входят встроенные типы, `Integer` такие `String`как и.</span><span class="sxs-lookup"><span data-stu-id="0c249-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c249-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0c249-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="0c249-121">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="0c249-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="0c249-122">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="0c249-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="0c249-123">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="0c249-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
