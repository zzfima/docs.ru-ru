---
title: "Переменная объекта или переменная блока With не задано | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4db2c827c3e77cfa6cc51132f0d647a58c93c769
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="e3d17-102">Не задана переменная объекта или переменная блока With</span><span class="sxs-lookup"><span data-stu-id="e3d17-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="e3d17-103">Указан недопустимый объект переменной.</span><span class="sxs-lookup"><span data-stu-id="e3d17-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="e3d17-104">Эта ошибка может возникать по нескольким причинам:</span><span class="sxs-lookup"><span data-stu-id="e3d17-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="e3d17-105">Переменная, объявленная без определения типа.</span><span class="sxs-lookup"><span data-stu-id="e3d17-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="e3d17-106">Если переменная объявлена без указания типа, то по умолчанию введите `Object`.</span><span class="sxs-lookup"><span data-stu-id="e3d17-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="e3d17-107">Например, переменная, объявленная с `Dim x` будут иметь тип `Object;` переменная, объявленная с `Dim x As String` будут иметь тип `String`.</span><span class="sxs-lookup"><span data-stu-id="e3d17-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e3d17-108">`Option Strict` Инструкции запрещает неявной типизации, в результате `Object` типа.</span><span class="sxs-lookup"><span data-stu-id="e3d17-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="e3d17-109">Если тип не указан, произойдет ошибка времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="e3d17-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="e3d17-110">В разделе [Option Strict оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e3d17-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="e3d17-111">Вы пытаетесь получить ссылку на объект, который имеет значение`Nothing`</span><span class="sxs-lookup"><span data-stu-id="e3d17-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="e3d17-112">.</span><span class="sxs-lookup"><span data-stu-id="e3d17-112">.</span></span>  
  
-   <span data-ttu-id="e3d17-113">Была попытка доступа к элементу массива, который не был объявлен неправильно.</span><span class="sxs-lookup"><span data-stu-id="e3d17-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="e3d17-114">Например, массив объявлен как `products() As String` вызовет ошибку при попытке ссылки на элемент массива `products(3) = "Widget"`.</span><span class="sxs-lookup"><span data-stu-id="e3d17-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="e3d17-115">Массив не содержит элементов и рассматривается как объект.</span><span class="sxs-lookup"><span data-stu-id="e3d17-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="e3d17-116">Вы пытаетесь получить код доступа в `With...End With` блокировать до инициализации блока.</span><span class="sxs-lookup"><span data-stu-id="e3d17-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="e3d17-117">Объект `With...End With` блок необходимо инициализировать посредством выполнения `With` точки входа оператора.</span><span class="sxs-lookup"><span data-stu-id="e3d17-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3d17-118">В более ранних версиях Visual Basic или VBA Эта ошибка также была активирована путем присвоения значения переменной без использования `Set` ключевое слово (`x = "name"` вместо `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="e3d17-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="e3d17-119">`Set` Ключевое слово больше не действительна в Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="e3d17-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3d17-120">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e3d17-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="e3d17-121">Задайте `Option Strict` в `On` , добавив следующий код в начало файла:</span><span class="sxs-lookup"><span data-stu-id="e3d17-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="e3d17-122">Если вы не хотите включить `Option Strict`, выполнить поиск кода для всех переменных, которые были заданы без типа (`Dim x` вместо `Dim x As String`) и добавьте нужный тип в объявлении.</span><span class="sxs-lookup"><span data-stu-id="e3d17-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="e3d17-123">Убедитесь, что не ссылки на объектную переменную, которая имеет значение `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e3d17-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="e3d17-124">Найдите в коде для ключевого слова `Nothing`и измените код так, что объект не `Nothing` до после создания ссылки на его.</span><span class="sxs-lookup"><span data-stu-id="e3d17-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="e3d17-125">Убедитесь, что все переменные массива измеряются до доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="e3d17-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="e3d17-126">При создании массива можно либо назначить измерения (`Dim x(5) As String` вместо `Dim x() As String`), или использовать `ReDim` ключевое слово для задания измерения массива перед сначала к нему.</span><span class="sxs-lookup"><span data-stu-id="e3d17-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="e3d17-127">Убедитесь, что ваш `With` блок инициализируется посредством выполнения `With` точки входа оператора.</span><span class="sxs-lookup"><span data-stu-id="e3d17-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d17-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e3d17-128">See Also</span></span>  
 <span data-ttu-id="e3d17-129">[Объявление переменных объектов](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="e3d17-129">[Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="e3d17-130"> [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e3d17-130"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="e3d17-131"> [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e3d17-131"> [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
