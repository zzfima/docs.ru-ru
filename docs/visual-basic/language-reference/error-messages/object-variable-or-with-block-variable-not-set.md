---
title: "Не задана переменная объекта или переменная блока With"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e1f587e194acf744b6ec9b8f1bede3acef7b753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="5b05c-102">Не задана переменная объекта или переменная блока With</span><span class="sxs-lookup"><span data-stu-id="5b05c-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="5b05c-103">Указан недопустимый объектной переменной.</span><span class="sxs-lookup"><span data-stu-id="5b05c-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="5b05c-104">Эта ошибка может возникать по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="5b05c-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="5b05c-105">Переменная была объявлена без указания типа.</span><span class="sxs-lookup"><span data-stu-id="5b05c-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="5b05c-106">Если переменная объявлена без указания типа, то по умолчанию к типу `Object`.</span><span class="sxs-lookup"><span data-stu-id="5b05c-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="5b05c-107">Например, переменная, объявленная с `Dim x` будет иметь тип `Object;` переменная, объявленная с `Dim x As String` будет иметь тип `String`.</span><span class="sxs-lookup"><span data-stu-id="5b05c-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="5b05c-108">`Option Strict` Инструкции запрещает неявное типизирование, в результате `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="5b05c-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="5b05c-109">Если параметр типа, возникнет ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="5b05c-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="5b05c-110">В разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b05c-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="5b05c-111">Вы пытаетесь ссылаться на объект, который равен`Nothing`</span><span class="sxs-lookup"><span data-stu-id="5b05c-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="5b05c-112">.</span><span class="sxs-lookup"><span data-stu-id="5b05c-112">.</span></span>  
  
-   <span data-ttu-id="5b05c-113">Вы пытаетесь получить доступ к элементу массива, который не был объявлен неправильно.</span><span class="sxs-lookup"><span data-stu-id="5b05c-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="5b05c-114">Например, массив объявлен как `products() As String` приведет к возникновению ошибки при попытке ссылки на элемент массива `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="5b05c-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="5b05c-115">Массив не содержит элементов и обрабатываются как объект.</span><span class="sxs-lookup"><span data-stu-id="5b05c-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="5b05c-116">Вы пытаетесь получить доступ код внутри `With...End With` блокируются прежде, чем блок был инициализирован.</span><span class="sxs-lookup"><span data-stu-id="5b05c-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="5b05c-117">Объект `With...End With` блока должны инициализироваться, выполнив `With` точки входа оператора.</span><span class="sxs-lookup"><span data-stu-id="5b05c-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b05c-118">В более ранних версиях Visual Basic или VBA ошибки также была запущена при присвоении значения переменной без использования `Set` ключевое слово (`x = "name"` вместо `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="5b05c-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="5b05c-119">`Set` Ключевое слово больше не действительна в Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="5b05c-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b05c-120">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5b05c-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="5b05c-121">Задать `Option Strict` для `On` , добавив следующий код в начало файла:</span><span class="sxs-lookup"><span data-stu-id="5b05c-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="5b05c-122">Если вы не хотите включить `Option Strict`, найдите в коде всех переменных, которые были заданы без типа (`Dim x` вместо `Dim x As String`) и добавьте к объявлению нужному типу.</span><span class="sxs-lookup"><span data-stu-id="5b05c-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="5b05c-123">Убедитесь, что не ссылается на объектную переменную, которая настроена для `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5b05c-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="5b05c-124">Найдите в коде для ключевого слова `Nothing`и изменить код таким образом, чтобы объект не задано значение `Nothing` до после создания ссылки на его.</span><span class="sxs-lookup"><span data-stu-id="5b05c-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="5b05c-125">Убедитесь, что все переменные массива измеряются перед обращением к их.</span><span class="sxs-lookup"><span data-stu-id="5b05c-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="5b05c-126">При создании массива можно либо назначить измерения (`Dim x(5) As String` вместо `Dim x() As String`), или используйте `ReDim` ключевое слово для задания измерения массива перед сначала к нему.</span><span class="sxs-lookup"><span data-stu-id="5b05c-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="5b05c-127">Убедитесь, что ваш `With` блок инициализируется путем выполнения `With` точки входа оператора.</span><span class="sxs-lookup"><span data-stu-id="5b05c-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b05c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5b05c-128">See Also</span></span>  
 [<span data-ttu-id="5b05c-129">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="5b05c-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="5b05c-130">Оператор reDim</span><span class="sxs-lookup"><span data-stu-id="5b05c-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="5b05c-131">Оператор With...End With</span><span class="sxs-lookup"><span data-stu-id="5b05c-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
