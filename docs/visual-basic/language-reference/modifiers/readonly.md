---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965425"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="10ebd-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10ebd-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="10ebd-103">Указывает, что переменная или свойство может быть прочитано, но не записано.</span><span class="sxs-lookup"><span data-stu-id="10ebd-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10ebd-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="10ebd-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="10ebd-105">Правила</span><span class="sxs-lookup"><span data-stu-id="10ebd-105">Rules</span></span>  
  
- <span data-ttu-id="10ebd-106">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="10ebd-106">**Declaration Context.**</span></span> <span data-ttu-id="10ebd-107">`ReadOnly` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="10ebd-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="10ebd-108">Это означает, что контекст объявления для `ReadOnly` элемента должен быть классом, структурой или модулем и не может быть исходным файлом, пространством имен или процедурой.</span><span class="sxs-lookup"><span data-stu-id="10ebd-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="10ebd-109">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="10ebd-109">**Combined Modifiers.**</span></span> <span data-ttu-id="10ebd-110">Нельзя указывать `ReadOnly` вместе с `Static` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="10ebd-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="10ebd-111">**Присвоение значения.**</span><span class="sxs-lookup"><span data-stu-id="10ebd-111">**Assigning a Value.**</span></span> <span data-ttu-id="10ebd-112">Код, использующий свойство, `ReadOnly` не может задать его значение.</span><span class="sxs-lookup"><span data-stu-id="10ebd-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="10ebd-113">Но код, имеющий доступ к базовому хранилищу, может назначить или изменить значение в любое время.</span><span class="sxs-lookup"><span data-stu-id="10ebd-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="10ebd-114">Значение `ReadOnly` переменной можно присвоить только в ее объявлении или в конструкторе класса или структуры, в которой он определен.</span><span class="sxs-lookup"><span data-stu-id="10ebd-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="10ebd-115">Когда следует использовать переменную только для чтения</span><span class="sxs-lookup"><span data-stu-id="10ebd-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="10ebd-116">Существуют ситуации, в которых нельзя использовать [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присваивания постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="10ebd-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="10ebd-117">Например, `Const` инструкция может не принять тип данных, который необходимо назначить, или не удастся вычислить значение во время компиляции с помощью константного выражения.</span><span class="sxs-lookup"><span data-stu-id="10ebd-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="10ebd-118">Возможно, вы даже не узнаете значение во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="10ebd-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="10ebd-119">В таких случаях можно использовать `ReadOnly` переменную для хранения постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="10ebd-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="10ebd-120">Если тип данных переменной является ссылочным типом, например массивом или экземпляром класса, его члены можно изменить, даже если сама переменная имеет `ReadOnly`значение.</span><span class="sxs-lookup"><span data-stu-id="10ebd-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="10ebd-121">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="10ebd-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="10ebd-122">При инициализации массив, на `characterArray()` который указывает, содержит "x", "y" и "z".</span><span class="sxs-lookup"><span data-stu-id="10ebd-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="10ebd-123">Так как переменная `characterArray` является `ReadOnly`, ее значение нельзя изменить после инициализации, то есть нельзя присвоить ему новый массив.</span><span class="sxs-lookup"><span data-stu-id="10ebd-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="10ebd-124">Однако можно изменить значения одного или нескольких элементов массива.</span><span class="sxs-lookup"><span data-stu-id="10ebd-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="10ebd-125">После вызова процедуры `changeArrayElement`массив, на который указывает, `characterArray()` содержит "x", "M" и "z".</span><span class="sxs-lookup"><span data-stu-id="10ebd-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="10ebd-126">Обратите внимание, что это похоже на объявление параметра процедуры как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), что не позволяет процедуре изменять сам аргумент вызова, но позволяет ему изменять его члены.</span><span class="sxs-lookup"><span data-stu-id="10ebd-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ebd-127">Пример</span><span class="sxs-lookup"><span data-stu-id="10ebd-127">Example</span></span>  
 <span data-ttu-id="10ebd-128">В следующем примере определяется `ReadOnly` свойство для даты найма сотрудника.</span><span class="sxs-lookup"><span data-stu-id="10ebd-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="10ebd-129">Класс сохраняет значение свойства внутри в виде `Private` переменной, и только код внутри класса может изменить это значение.</span><span class="sxs-lookup"><span data-stu-id="10ebd-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="10ebd-130">Однако свойство имеет `Public`значение, а любой код, который может получить доступ к классу, может считать свойство.</span><span class="sxs-lookup"><span data-stu-id="10ebd-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 <span data-ttu-id="10ebd-131">Модификатор `ReadOnly` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="10ebd-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="10ebd-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="10ebd-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="10ebd-133">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="10ebd-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="10ebd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="10ebd-134">See also</span></span>

- [<span data-ttu-id="10ebd-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="10ebd-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="10ebd-136">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="10ebd-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
