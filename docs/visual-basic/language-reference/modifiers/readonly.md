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
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599916"
---
# <a name="readonly-visual-basic"></a><span data-ttu-id="f5d78-102">ReadOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5d78-102">ReadOnly (Visual Basic)</span></span>
<span data-ttu-id="f5d78-103">Указывает, что переменная или свойство можно считывать, но не записываются.</span><span class="sxs-lookup"><span data-stu-id="f5d78-103">Specifies that a variable or property can be read but not written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5d78-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5d78-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f5d78-105">Правила</span><span class="sxs-lookup"><span data-stu-id="f5d78-105">Rules</span></span>  
  
-   <span data-ttu-id="f5d78-106">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="f5d78-106">**Declaration Context.**</span></span> <span data-ttu-id="f5d78-107">`ReadOnly` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="f5d78-107">You can use `ReadOnly` only at module level.</span></span> <span data-ttu-id="f5d78-108">Это означает, что контекст объявления для `ReadOnly` элемент должен быть классом, структурой или модуля и не может быть исходным файлом, пространством имен или процедуры.</span><span class="sxs-lookup"><span data-stu-id="f5d78-108">This means the declaration context for a `ReadOnly` element must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="f5d78-109">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="f5d78-109">**Combined Modifiers.**</span></span> <span data-ttu-id="f5d78-110">Нельзя указать `ReadOnly` вместе с `Static` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="f5d78-110">You cannot specify `ReadOnly` together with `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="f5d78-111">**Присвоение значения.**</span><span class="sxs-lookup"><span data-stu-id="f5d78-111">**Assigning a Value.**</span></span> <span data-ttu-id="f5d78-112">Использование кода `ReadOnly` свойство нельзя задать для него значение.</span><span class="sxs-lookup"><span data-stu-id="f5d78-112">Code consuming a `ReadOnly` property cannot set its value.</span></span> <span data-ttu-id="f5d78-113">Однако код, который имеет доступ к базовое хранилище можно назначить или изменить значение в любое время.</span><span class="sxs-lookup"><span data-stu-id="f5d78-113">But code that has access to the underlying storage can assign or change the value at any time.</span></span>  
  
     <span data-ttu-id="f5d78-114">Можно присвоить значение `ReadOnly` переменной только при объявлении или в конструкторе класса или структуры, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="f5d78-114">You can assign a value to a `ReadOnly` variable only in its declaration or in the constructor of a class or structure in which it is defined.</span></span>  
  
## <a name="when-to-use-a-readonly-variable"></a><span data-ttu-id="f5d78-115">Когда следует использовать переменную только для чтения</span><span class="sxs-lookup"><span data-stu-id="f5d78-115">When to Use a ReadOnly Variable</span></span>  
 <span data-ttu-id="f5d78-116">Существуют ситуации, в которых нельзя использовать [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) объявления и присвоить постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="f5d78-116">There are situations in which you cannot use a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value.</span></span> <span data-ttu-id="f5d78-117">Например `Const` инструкция может не поддерживать тип данных, который вы хотите назначить или не может быть возможность вычисления значения во время компиляции с помощью константного выражения.</span><span class="sxs-lookup"><span data-stu-id="f5d78-117">For example, the `Const` statement might not accept the data type you want to assign, or you might not be able to compute the value at compile time with a constant expression.</span></span> <span data-ttu-id="f5d78-118">Вам может быть даже неизвестно значение во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="f5d78-118">You might not even know the value at compile time.</span></span> <span data-ttu-id="f5d78-119">В этих случаях можно использовать `ReadOnly` переменной для хранения постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="f5d78-119">In these cases, you can use a `ReadOnly` variable to hold a constant value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5d78-120">Если тип данных переменной является ссылочным типом, например, массив или экземпляр класса его члены могут быть изменены, даже если сама переменная `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="f5d78-120">If the data type of the variable is a reference type, such as an array or a class instance, its members can be changed even if the variable itself is `ReadOnly`.</span></span> <span data-ttu-id="f5d78-121">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f5d78-121">The following example illustrates this.</span></span>  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 <span data-ttu-id="f5d78-122">При инициализации массива, на который указывает `characterArray()` содержит «x», «y» и «z».</span><span class="sxs-lookup"><span data-stu-id="f5d78-122">When initialized, the array pointed to by `characterArray()` holds "x", "y", and "z".</span></span> <span data-ttu-id="f5d78-123">Так как переменная `characterArray` — `ReadOnly`, его значение нельзя изменить после инициализации;, нельзя назначить новый массив.</span><span class="sxs-lookup"><span data-stu-id="f5d78-123">Because the variable `characterArray` is `ReadOnly`, you cannot change its value once it is initialized; that is, you cannot assign a new array to it.</span></span> <span data-ttu-id="f5d78-124">Тем не менее можно изменить значения одного или нескольких элементов массива.</span><span class="sxs-lookup"><span data-stu-id="f5d78-124">However, you can change the values of one or more of the array members.</span></span> <span data-ttu-id="f5d78-125">После вызова процедуры `changeArrayElement`, массив, на который указывает `characterArray()` содержит «x», «M» и «z».</span><span class="sxs-lookup"><span data-stu-id="f5d78-125">Following a call to the procedure `changeArrayElement`, the array pointed to by `characterArray()` holds "x", "M", and "z".</span></span>  
  
 <span data-ttu-id="f5d78-126">Обратите внимание, что это похоже на объявление параметра процедуры [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), который запрещает процедуре изменять аргумент вызова, но позволяет менять его члены.</span><span class="sxs-lookup"><span data-stu-id="f5d78-126">Note that this is similar to declaring a procedure parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), which prevents the procedure from changing the calling argument itself but allows it to change its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5d78-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f5d78-127">Example</span></span>  
 <span data-ttu-id="f5d78-128">В следующем примере определяется `ReadOnly` свойство даты найма сотрудника.</span><span class="sxs-lookup"><span data-stu-id="f5d78-128">The following example defines a `ReadOnly` property for the date on which an employee was hired.</span></span> <span data-ttu-id="f5d78-129">Класс хранит значение свойства, внутренне как `Private` переменной и только код внутри класса можно изменить это значение.</span><span class="sxs-lookup"><span data-stu-id="f5d78-129">The class stores the property value internally as a `Private` variable, and only code inside the class can change that value.</span></span> <span data-ttu-id="f5d78-130">Однако свойство `Public`, и любой код, который можно получить доступ к классу можно получить значение свойства.</span><span class="sxs-lookup"><span data-stu-id="f5d78-130">However, the property is `Public`, and any code that can access the class can read the property.</span></span>  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 <span data-ttu-id="f5d78-131">Модификатор `ReadOnly` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="f5d78-131">The `ReadOnly` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f5d78-132">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="f5d78-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f5d78-133">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f5d78-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5d78-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f5d78-134">See Also</span></span>  
 [<span data-ttu-id="f5d78-135">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="f5d78-135">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [<span data-ttu-id="f5d78-136">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f5d78-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
