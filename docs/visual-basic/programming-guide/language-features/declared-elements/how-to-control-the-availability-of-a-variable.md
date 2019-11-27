---
title: Практическое руководство. Управление доступностью переменной
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
ms.openlocfilehash: 886b57909cf6ba25dbaceea5c5f06eb4e3ba6f1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345393"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="ea9fc-102">Практическое руководство. Управление доступностью переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea9fc-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="ea9fc-103">Для управления доступностью переменной можно указать ее *уровень доступа*.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="ea9fc-104">Уровень доступа определяет, какой код имеет разрешение на чтение или запись в переменную.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="ea9fc-105">*Переменные-члены* (определенные на уровне модуля и вне любой процедуры) по умолчанию имеют открытый доступ, что означает любой код, который может видеть, что они имеют доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="ea9fc-106">Это можно изменить, указав модификатор доступа.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="ea9fc-107">*Локальные переменные* (определенные внутри процедуры) номинально имеют общий доступ, хотя доступ к ним могут получить только код внутри их процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="ea9fc-108">Нельзя изменить уровень доступа локальной переменной, но можно изменить уровень доступа процедуры, содержащей ее.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="ea9fc-109">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ea9fc-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="ea9fc-110">Частный и открытый доступ</span><span class="sxs-lookup"><span data-stu-id="ea9fc-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="ea9fc-111">Предоставление доступа к переменной только внутри модуля, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="ea9fc-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="ea9fc-112">Поместите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ea9fc-113">Включите ключевое слово [Private](../../../../visual-basic/language-reference/modifiers/private.md) в оператор `Dim`.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="ea9fc-114">Можно выполнять чтение или запись в переменную из любого места внутри модуля, класса или структуры, но не за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="ea9fc-115">Чтобы сделать переменную доступной из любого кода, который может ее увидеть</span><span class="sxs-lookup"><span data-stu-id="ea9fc-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="ea9fc-116">Для переменной-члена Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ea9fc-117">Включите в оператор `Dim` ключевое слово [Public](../../../../visual-basic/language-reference/modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="ea9fc-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="ea9fc-118">Можно выполнять чтение или запись в переменную из любого кода, который взаимодействует со сборкой.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="ea9fc-119">\- или -</span><span class="sxs-lookup"><span data-stu-id="ea9fc-119">-or-</span></span>  
  
1. <span data-ttu-id="ea9fc-120">Для локальной переменной поместите оператор `Dim` для переменной внутри процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="ea9fc-121">Не включайте ключевое слово `Public` в инструкцию `Dim`.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="ea9fc-122">Можно выполнять чтение или запись в переменную из любого места внутри процедуры, но не за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="ea9fc-123">Защищенный и дружественный доступ</span><span class="sxs-lookup"><span data-stu-id="ea9fc-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="ea9fc-124">Уровень доступа переменной можно ограничить своим классом и любыми производными классами или сборкой.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="ea9fc-125">Можно также указать объединение этих ограничений, которое разрешает доступ из кода в любом производном классе или в любом другом месте в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="ea9fc-126">Это объединение можно указать, объединив ключевые слова `Protected` и `Friend` в том же объявлении.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="ea9fc-127">Предоставление доступа к переменной только внутри ее класса и любых производных классов</span><span class="sxs-lookup"><span data-stu-id="ea9fc-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="ea9fc-128">Поместите оператор `Dim` для переменной внутри класса, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ea9fc-129">Включите ключевое слово [protected](../../../../visual-basic/language-reference/modifiers/protected.md) в оператор `Dim`.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="ea9fc-130">Можно выполнять чтение или запись в переменную из любого места внутри класса, а также из любого класса, производного от него, но не за пределами класса в цепочке наследования.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="ea9fc-131">Предоставление переменной доступа только из той же сборки</span><span class="sxs-lookup"><span data-stu-id="ea9fc-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="ea9fc-132">Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ea9fc-133">Включите в оператор `Dim` ключевое слово [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) .</span><span class="sxs-lookup"><span data-stu-id="ea9fc-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="ea9fc-134">Можно выполнять чтение или запись в переменную из любого места внутри модуля, класса или структуры, а также из любого кода в той же сборке, но не за пределами сборки.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea9fc-135">Пример</span><span class="sxs-lookup"><span data-stu-id="ea9fc-135">Example</span></span>  
 <span data-ttu-id="ea9fc-136">В следующем примере показаны объявления переменных с уровнями доступа `Public`, `Protected`, `Friend`, `Protected Friend`и `Private`.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="ea9fc-137">Обратите внимание, что если в инструкции `Dim` указан уровень доступа, не нужно включать ключевое слово `Dim`.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="ea9fc-138">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ea9fc-138">.NET Framework Security</span></span>  
 <span data-ttu-id="ea9fc-139">Чем более ограниченный уровень доступа переменной, тем меньше вероятность того, что вредоносный код может неправильно использовать его.</span><span class="sxs-lookup"><span data-stu-id="ea9fc-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea9fc-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ea9fc-140">See also</span></span>

- [<span data-ttu-id="ea9fc-141">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea9fc-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="ea9fc-142">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="ea9fc-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="ea9fc-143">Public</span><span class="sxs-lookup"><span data-stu-id="ea9fc-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="ea9fc-144">Protected</span><span class="sxs-lookup"><span data-stu-id="ea9fc-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="ea9fc-145">Friend</span><span class="sxs-lookup"><span data-stu-id="ea9fc-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="ea9fc-146">Закрытые</span><span class="sxs-lookup"><span data-stu-id="ea9fc-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
