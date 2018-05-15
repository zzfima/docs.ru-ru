---
title: Практическое руководство. Управление доступностью переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 27ee5d3405ea24c0754cffa85e9b89b2ac561e42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="754af-102">Практическое руководство. Управление доступностью переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="754af-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="754af-103">Управление доступностью переменной, указав его *уровень доступа*.</span><span class="sxs-lookup"><span data-stu-id="754af-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="754af-104">Уровень доступа определяет, какой код имеет разрешение на чтение или запись в переменную.</span><span class="sxs-lookup"><span data-stu-id="754af-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="754af-105">*Переменные-члены* (определяется на уровне модуля и вне любых процедур) по умолчанию для общего доступа, что означает любой код, который могли получить к ним могли обращаться к ним.</span><span class="sxs-lookup"><span data-stu-id="754af-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="754af-106">Это можно изменить, указав модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="754af-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="754af-107">*Локальные переменные* (определяется внутри процедуры) обычно общедоступны являются общедоступными, несмотря на то, что они доступны только код внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="754af-108">Невозможно изменить уровень доступа к локальной переменной, но можно изменить уровень доступа для процедуры, в которой он содержится.</span><span class="sxs-lookup"><span data-stu-id="754af-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="754af-109">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="754af-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="754af-110">Закрытый и открытый доступ</span><span class="sxs-lookup"><span data-stu-id="754af-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="754af-111">Чтобы сделать переменную доступной только из модуля, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="754af-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="754af-112">Место [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="754af-113">Включить [закрытый](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="754af-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="754af-114">Может считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, но не из за его пределами.</span><span class="sxs-lookup"><span data-stu-id="754af-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="754af-115">Чтобы сделать переменную доступной из любого кода, который можно видеть его</span><span class="sxs-lookup"><span data-stu-id="754af-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="754af-116">Переменную-член, поместите `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="754af-117">Включить [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="754af-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="754af-118">Может считывать или записывать значение переменной из любого кода, взаимодействующего со сборкой.</span><span class="sxs-lookup"><span data-stu-id="754af-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="754af-119">- или -</span><span class="sxs-lookup"><span data-stu-id="754af-119">-or-</span></span>  
  
1.  <span data-ttu-id="754af-120">Для локальной переменной, поместите `Dim` инструкции для переменной внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="754af-121">Не включайте `Public` ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="754af-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="754af-122">Вы могли читать или записывать значение переменной из любого места внутри процедуры, но не из за его пределами.</span><span class="sxs-lookup"><span data-stu-id="754af-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="754af-123">Защищенные и дружественный доступ</span><span class="sxs-lookup"><span data-stu-id="754af-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="754af-124">Можно ограничить уровень доступа переменной его класса и всех производных классах, или его сборке.</span><span class="sxs-lookup"><span data-stu-id="754af-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="754af-125">Можно также указать объединение этих ограничений, который позволяет доступ из кода любого производного класса или любого другого места в той же сборке.</span><span class="sxs-lookup"><span data-stu-id="754af-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="754af-126">Укажите это объединение путем объединения `Protected` и `Friend` ключевые слова в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="754af-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="754af-127">Чтобы сделать переменную доступной только из своего класса и его производные классы</span><span class="sxs-lookup"><span data-stu-id="754af-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="754af-128">Место `Dim` инструкции для переменной внутри класса, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="754af-129">Включить [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="754af-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="754af-130">Может считывать или записывать значение переменной из любого места внутри класса, а также внутри любого класса, производного от него, но не из за пределами любого класса в иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="754af-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="754af-131">Чтобы сделать переменную доступной только из той же сборки</span><span class="sxs-lookup"><span data-stu-id="754af-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="754af-132">Место `Dim` инструкции для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="754af-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="754af-133">Включить [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="754af-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="754af-134">Может считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, а также из любого кода в той же сборке, но не из за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="754af-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="754af-135">Пример</span><span class="sxs-lookup"><span data-stu-id="754af-135">Example</span></span>  
 <span data-ttu-id="754af-136">В следующем примере показано объявление переменных с `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private` уровни доступа.</span><span class="sxs-lookup"><span data-stu-id="754af-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="754af-137">Обратите внимание, что при `Dim` инструкция указывает уровень доступа, не должны включать `Dim` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="754af-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="754af-138">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="754af-138">.NET Framework Security</span></span>  
 <span data-ttu-id="754af-139">Более строгий уровень доступа к переменной, тем меньше вероятность того, что вредоносный код может использовать неправильной его использовать.</span><span class="sxs-lookup"><span data-stu-id="754af-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754af-140">См. также</span><span class="sxs-lookup"><span data-stu-id="754af-140">See Also</span></span>  
 [<span data-ttu-id="754af-141">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="754af-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="754af-142">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="754af-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="754af-143">Public</span><span class="sxs-lookup"><span data-stu-id="754af-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="754af-144">Protected</span><span class="sxs-lookup"><span data-stu-id="754af-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="754af-145">Friend</span><span class="sxs-lookup"><span data-stu-id="754af-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="754af-146">Закрытые</span><span class="sxs-lookup"><span data-stu-id="754af-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
