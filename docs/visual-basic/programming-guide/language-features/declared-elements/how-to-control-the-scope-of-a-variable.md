---
title: Практическое руководство. Управление областью действия переменной
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 0ee6ce183310aa836ecdbbc0bc819e0e83d1872d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345379"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="8471d-102">Практическое руководство. Управление областью действия переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8471d-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="8471d-103">Как правило, переменная находится в *области видимости*или видима для справки по всему региону, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="8471d-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="8471d-104">В некоторых случаях *уровень доступа* переменной может повлиять на ее область.</span><span class="sxs-lookup"><span data-stu-id="8471d-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="8471d-105">Для получения дополнительной информации см. [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="8471d-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="8471d-106">Область на уровне блока или процедуры</span><span class="sxs-lookup"><span data-stu-id="8471d-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="8471d-107">Предоставление переменной видимой только внутри блока</span><span class="sxs-lookup"><span data-stu-id="8471d-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="8471d-108">Поместите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для переменной между операторами объявления начала и завершения этого блока, например между операторами `For` и `Next` цикла `For`.</span><span class="sxs-lookup"><span data-stu-id="8471d-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="8471d-109">Ссылаться на переменную можно только внутри блока.</span><span class="sxs-lookup"><span data-stu-id="8471d-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="8471d-110">Предоставление переменной видимой только внутри процедуры</span><span class="sxs-lookup"><span data-stu-id="8471d-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="8471d-111">Поместите оператор `Dim` для переменной внутри процедуры, но вне любого блока (например, `With`...`End With` блок).</span><span class="sxs-lookup"><span data-stu-id="8471d-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="8471d-112">Ссылаться на переменную можно только внутри процедуры, включая внутри любого блока, содержащегося в процедуре.</span><span class="sxs-lookup"><span data-stu-id="8471d-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="8471d-113">Область на уровне модуля или пространства имен</span><span class="sxs-lookup"><span data-stu-id="8471d-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="8471d-114">Для удобства *уровень модуля* единого термина применяется в равной степени к модулям, классам и структурам.</span><span class="sxs-lookup"><span data-stu-id="8471d-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="8471d-115">Уровень доступа переменной уровня модуля определяет ее область.</span><span class="sxs-lookup"><span data-stu-id="8471d-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="8471d-116">Пространство имен, содержащее модуль, класс или структуру, также влияет на область.</span><span class="sxs-lookup"><span data-stu-id="8471d-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="8471d-117">Чтобы сделать переменную видимой в пределах модуля, класса или структуры</span><span class="sxs-lookup"><span data-stu-id="8471d-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="8471d-118">Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="8471d-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8471d-119">Включите ключевое слово [Private](../../../../visual-basic/language-reference/modifiers/private.md) в оператор `Dim`.</span><span class="sxs-lookup"><span data-stu-id="8471d-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="8471d-120">Можно ссылаться на переменную из любого места в модуле, классе или структуре, но не за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="8471d-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="8471d-121">Как сделать переменную видимой во всем пространстве имен</span><span class="sxs-lookup"><span data-stu-id="8471d-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="8471d-122">Поместите оператор `Dim` для переменной внутри модуля, класса или структуры, но вне любой процедуры.</span><span class="sxs-lookup"><span data-stu-id="8471d-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8471d-123">Включите в оператор `Dim` ключевое слово [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [Public](../../../../visual-basic/language-reference/modifiers/public.md) .</span><span class="sxs-lookup"><span data-stu-id="8471d-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="8471d-124">Можно ссылаться на переменную из любого места в пространстве имен, содержащем модуль, класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="8471d-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8471d-125">Пример</span><span class="sxs-lookup"><span data-stu-id="8471d-125">Example</span></span>  
 <span data-ttu-id="8471d-126">В следующем примере объявляется переменная на уровне модуля и ограничивается ее видимость кодом внутри модуля.</span><span class="sxs-lookup"><span data-stu-id="8471d-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="8471d-127">В предыдущем примере все процедуры, определенные в `demonstrateScope` модуля, могут ссылаться на `String` переменную `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="8471d-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="8471d-128">При вызове процедуры `usePrivateVariable` она отображает содержимое строковой переменной, `strMsg` в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="8471d-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="8471d-129">После приведения к предыдущему примеру изменений, строковая переменная `strMsg` может называться кодом в любом месте пространства имен его объявления.</span><span class="sxs-lookup"><span data-stu-id="8471d-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="8471d-130">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8471d-130">Robust Programming</span></span>  
 <span data-ttu-id="8471d-131">Чем более узкие области переменной, тем меньше возможностей вы случайно ссылаетесь на нее вместо другой переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="8471d-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="8471d-132">Можно также избежать проблем, связанных с сопоставлением ссылок.</span><span class="sxs-lookup"><span data-stu-id="8471d-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8471d-133">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8471d-133">.NET Framework Security</span></span>  
 <span data-ttu-id="8471d-134">Чем короче область переменной, тем меньше вероятность того, что вредоносный код может неправильно использовать его.</span><span class="sxs-lookup"><span data-stu-id="8471d-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8471d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8471d-135">See also</span></span>

- [<span data-ttu-id="8471d-136">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8471d-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="8471d-137">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8471d-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="8471d-138">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8471d-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="8471d-139">Переменные</span><span class="sxs-lookup"><span data-stu-id="8471d-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="8471d-140">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="8471d-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="8471d-141">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="8471d-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
