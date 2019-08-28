---
title: Не задана переменная объекта или переменная блока With
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040558"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="98a0c-102">Не задана переменная объекта или переменная блока With</span><span class="sxs-lookup"><span data-stu-id="98a0c-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="98a0c-103">Указана недопустимая объектная переменная.</span><span class="sxs-lookup"><span data-stu-id="98a0c-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="98a0c-104">Эта ошибка может возникать по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="98a0c-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="98a0c-105">Переменная объявлена без указания типа.</span><span class="sxs-lookup"><span data-stu-id="98a0c-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="98a0c-106">Если переменная объявлена без указания типа, по умолчанию используется тип `Object`.</span><span class="sxs-lookup"><span data-stu-id="98a0c-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="98a0c-107">Например, переменная, объявленная с `Dim x` типом, будет иметь `Object;` тип переменной, объявленной с `Dim x As String` типом `String`.</span><span class="sxs-lookup"><span data-stu-id="98a0c-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="98a0c-108">Оператор запрещает неявную типизацию, которая приводит к `Object` типу. `Option Strict`</span><span class="sxs-lookup"><span data-stu-id="98a0c-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="98a0c-109">Если опустить тип, возникнет ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="98a0c-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="98a0c-110">См. [оператор Option Case](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="98a0c-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="98a0c-111">Предпринимается попытка сослаться на объект, для `Nothing`которого задано значение.</span><span class="sxs-lookup"><span data-stu-id="98a0c-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="98a0c-112">Предпринята попытка получить доступ к элементу переменной массива, которая была неправильно объявлена.</span><span class="sxs-lookup"><span data-stu-id="98a0c-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="98a0c-113">Например, массив, объявленный как `products() As String` , вызовет ошибку при попытке сослаться на элемент массива. `products(3) = "Widget"`</span><span class="sxs-lookup"><span data-stu-id="98a0c-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="98a0c-114">Массив не содержит элементов и обрабатывается как объект.</span><span class="sxs-lookup"><span data-stu-id="98a0c-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="98a0c-115">Попытка получить доступ к коду в `With...End With` блоке до инициализации блока.</span><span class="sxs-lookup"><span data-stu-id="98a0c-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="98a0c-116">Блок необходимо инициализировать, `With` выполнив точку входа оператора. `With...End With`</span><span class="sxs-lookup"><span data-stu-id="98a0c-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="98a0c-117">В более ранних версиях Visual Basic или VBA эта ошибка также была активирована путем присвоения значения переменной без использования `Set` ключевого слова (`x = "name"` вместо `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="98a0c-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="98a0c-118">`Set` Ключевое слово больше не является допустимым в Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="98a0c-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="98a0c-119">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="98a0c-119">To correct this error</span></span>

1. <span data-ttu-id="98a0c-120">Задайте `Option Strict` для`On` значение, добавив следующий код в начало файла:</span><span class="sxs-lookup"><span data-stu-id="98a0c-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="98a0c-121">При запуске проекта в **Список ошибок** для любой переменной, указанной без типа, отобразится ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="98a0c-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="98a0c-122">Если вы не хотите включать `Option Strict`, найдите в коде любые переменные, которые были указаны без типа (`Dim x` вместо `Dim x As String`), и добавьте предполагаемый тип к объявлению.</span><span class="sxs-lookup"><span data-stu-id="98a0c-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="98a0c-123">Убедитесь, что вы не ссылаетесь на переменную объекта, для `Nothing`которой было задано значение.</span><span class="sxs-lookup"><span data-stu-id="98a0c-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="98a0c-124">Найдите ключевое слово `Nothing`в коде и измените код таким образом, чтобы объект не был установлен в `Nothing` значение до тех пор, пока вы не задали ссылку на него.</span><span class="sxs-lookup"><span data-stu-id="98a0c-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="98a0c-125">Прежде чем обращаться к ним, убедитесь, что все переменные массива имеют размеры.</span><span class="sxs-lookup"><span data-stu-id="98a0c-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="98a0c-126">Можно либо назначить измерение при первом создании массива (`Dim x(5) As String` `Dim x() As String`вместо `ReDim` ), либо использовать ключевое слово, чтобы задать размеры массива до первого доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="98a0c-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="98a0c-127">Убедитесь, что `With` блок инициализирован путем `With` выполнения точки входа оператора.</span><span class="sxs-lookup"><span data-stu-id="98a0c-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="98a0c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="98a0c-128">See also</span></span>

- [<span data-ttu-id="98a0c-129">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="98a0c-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="98a0c-130">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="98a0c-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="98a0c-131">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="98a0c-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
