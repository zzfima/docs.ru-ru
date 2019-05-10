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
ms.openlocfilehash: 419f3eed30a5d4b35bcb9dde5242b9092ee9cb79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610504"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="35d2f-102">Практическое руководство. Управление доступностью переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35d2f-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="35d2f-103">Управление доступностью переменной, указав его *уровень доступа*.</span><span class="sxs-lookup"><span data-stu-id="35d2f-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="35d2f-104">Уровень доступа определяет, какой код имеет разрешение на чтение или запись в переменную.</span><span class="sxs-lookup"><span data-stu-id="35d2f-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="35d2f-105">*Переменные-члены* (определяется на уровне модуля, так и вне любых процедур) по умолчанию для общего доступа, который означает, что любой код, который можно увидеть их доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="35d2f-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="35d2f-106">Вы можете изменить, указав модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="35d2f-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="35d2f-107">*Локальные переменные* (определяется внутри процедуры) сети являются общедоступными, несмотря на то, что они доступны только код внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="35d2f-108">Невозможно изменить уровень доступа к локальной переменной, но можно изменить уровень доступа для процедуры, содержащей его.</span><span class="sxs-lookup"><span data-stu-id="35d2f-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="35d2f-109">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="35d2f-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="35d2f-110">Частный и общий доступ</span><span class="sxs-lookup"><span data-stu-id="35d2f-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="35d2f-111">Чтобы сделать переменную доступной только из модуля, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="35d2f-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="35d2f-112">Место [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35d2f-113">Включить [частного](../../../../visual-basic/language-reference/modifiers/private.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="35d2f-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="35d2f-114">Можно считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, но не из за его пределами.</span><span class="sxs-lookup"><span data-stu-id="35d2f-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="35d2f-115">Чтобы сделать переменную доступной из любой код, который можно увидеть его</span><span class="sxs-lookup"><span data-stu-id="35d2f-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="35d2f-116">Переменную-член, поместите `Dim` инструкцию для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35d2f-117">Включить [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="35d2f-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="35d2f-118">Можно считывать или записывать значение переменной из любого кода, который взаимодействует со сборкой.</span><span class="sxs-lookup"><span data-stu-id="35d2f-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="35d2f-119">-или-</span><span class="sxs-lookup"><span data-stu-id="35d2f-119">-or-</span></span>  
  
1. <span data-ttu-id="35d2f-120">Для локальной переменной, поместите `Dim` инструкцию для переменной внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="35d2f-121">Не используйте `Public` ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="35d2f-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="35d2f-122">Можно считывать или записывать значение переменной из любого места внутри процедуры, но не из за его пределами.</span><span class="sxs-lookup"><span data-stu-id="35d2f-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="35d2f-123">Защищенные и дружественный доступ</span><span class="sxs-lookup"><span data-stu-id="35d2f-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="35d2f-124">Можно ограничить уровень доступа переменной его класса и всем производным классам, или его сборке.</span><span class="sxs-lookup"><span data-stu-id="35d2f-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="35d2f-125">Можно также указать объединение этих ограничений, которая разрешает доступ из кода, в любом производном классе или в любом месте в той же сборке.</span><span class="sxs-lookup"><span data-stu-id="35d2f-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="35d2f-126">Укажите это объединение путем объединения `Protected` и `Friend` ключевые слова в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="35d2f-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="35d2f-127">Чтобы сделать переменную доступной только из своего класса и его производные классы</span><span class="sxs-lookup"><span data-stu-id="35d2f-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="35d2f-128">Место `Dim` инструкцию для переменной внутри класса, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35d2f-129">Включить [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="35d2f-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="35d2f-130">Можно считывать или записывать значение переменной из любого места внутри класса, а также внутри любого класса, производного от него, но не из за пределами любого класса в иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="35d2f-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="35d2f-131">Чтобы сделать переменную доступной только из той же сборки</span><span class="sxs-lookup"><span data-stu-id="35d2f-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="35d2f-132">Место `Dim` инструкцию для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="35d2f-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="35d2f-133">Включить [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="35d2f-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="35d2f-134">Можно считывать или записывать значение переменной из любого места внутри модуля, класса или структуры, а также из любого кода в той же сборке, но не из за пределов сборки.</span><span class="sxs-lookup"><span data-stu-id="35d2f-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d2f-135">Пример</span><span class="sxs-lookup"><span data-stu-id="35d2f-135">Example</span></span>  
 <span data-ttu-id="35d2f-136">В следующем примере показано объявление переменных с `Public`, `Protected`, `Friend`, `Protected Friend`, и `Private` уровни доступа.</span><span class="sxs-lookup"><span data-stu-id="35d2f-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="35d2f-137">Обратите внимание, что при `Dim` инструкция указывает уровень доступа, необходимо включить `Dim` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="35d2f-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="35d2f-138">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="35d2f-138">.NET Framework Security</span></span>  
 <span data-ttu-id="35d2f-139">Чем строже уровень доступа к переменной, тем меньше вероятность того, что вредоносный код может использовать неправильной его использовать.</span><span class="sxs-lookup"><span data-stu-id="35d2f-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d2f-140">См. также</span><span class="sxs-lookup"><span data-stu-id="35d2f-140">See also</span></span>

- [<span data-ttu-id="35d2f-141">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35d2f-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="35d2f-142">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="35d2f-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="35d2f-143">Public</span><span class="sxs-lookup"><span data-stu-id="35d2f-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="35d2f-144">Protected</span><span class="sxs-lookup"><span data-stu-id="35d2f-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="35d2f-145">Friend</span><span class="sxs-lookup"><span data-stu-id="35d2f-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="35d2f-146">Закрытые</span><span class="sxs-lookup"><span data-stu-id="35d2f-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
