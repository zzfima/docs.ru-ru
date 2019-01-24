---
title: Область видимости в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 38dd9d6d40780c25f06a35cf1ffbe4743b7da4a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537252"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="cb316-102">Область видимости в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb316-102">Scope in Visual Basic</span></span>
<span data-ttu-id="cb316-103">*Область* объявленного элемента представляет собой весь код, который могут ссылаться на нее без уточнения его имени или обеспечение его доступности через [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="cb316-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="cb316-104">Элемент может иметь область на одном из следующих уровней:</span><span class="sxs-lookup"><span data-stu-id="cb316-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="cb316-105">Уровень</span><span class="sxs-lookup"><span data-stu-id="cb316-105">Level</span></span>|<span data-ttu-id="cb316-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="cb316-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb316-107">Область действия блока</span><span class="sxs-lookup"><span data-stu-id="cb316-107">Block scope</span></span>|<span data-ttu-id="cb316-108">Доступно только в коде блока, в котором она объявлена</span><span class="sxs-lookup"><span data-stu-id="cb316-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="cb316-109">Область действия процедуры</span><span class="sxs-lookup"><span data-stu-id="cb316-109">Procedure scope</span></span>|<span data-ttu-id="cb316-110">Доступен в коде в рамках процедуры, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="cb316-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="cb316-111">Области модуля</span><span class="sxs-lookup"><span data-stu-id="cb316-111">Module scope</span></span>|<span data-ttu-id="cb316-112">Для всего кода внутри модуля, класса или структуры, в котором она объявлена</span><span class="sxs-lookup"><span data-stu-id="cb316-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="cb316-113">Область видимости пространства имен</span><span class="sxs-lookup"><span data-stu-id="cb316-113">Namespace scope</span></span>|<span data-ttu-id="cb316-114">Доступен в коде в пространстве имен, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="cb316-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="cb316-115">Эти уровни области хода выполнения от самой узкой (блока) для широкой (пространства имен), где *наиболее узкой области* означает наименьший объем кода, которые могут обращаться к элементу без уточнения.</span><span class="sxs-lookup"><span data-stu-id="cb316-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="cb316-116">Дополнительные сведения см. в разделе «Уровни Scope» на этой странице.</span><span class="sxs-lookup"><span data-stu-id="cb316-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="cb316-117">Указание области и определение переменных</span><span class="sxs-lookup"><span data-stu-id="cb316-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="cb316-118">Укажите область действия элемента, при объявлении.</span><span class="sxs-lookup"><span data-stu-id="cb316-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="cb316-119">Область может зависеть от следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="cb316-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="cb316-120">Регион (блокировка, процедуры, модуля, класса или структуры), в которой объявляется элемент</span><span class="sxs-lookup"><span data-stu-id="cb316-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="cb316-121">Пространство имен, содержащее объявление этого элемента</span><span class="sxs-lookup"><span data-stu-id="cb316-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="cb316-122">Уровень доступа, объявляемые для элемента</span><span class="sxs-lookup"><span data-stu-id="cb316-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="cb316-123">Соблюдайте осторожность при определении переменных с одинаковыми именами, но разными областями действия, так как это может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="cb316-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="cb316-124">Для получения дополнительной информации см. [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="cb316-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="cb316-125">Уровни области действия</span><span class="sxs-lookup"><span data-stu-id="cb316-125">Levels of Scope</span></span>  
 <span data-ttu-id="cb316-126">Программный элемент доступен во всем регионе, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="cb316-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="cb316-127">Весь код в одном регионе можно обращаться к элементу без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="cb316-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="cb316-128">Область видимости блока</span><span class="sxs-lookup"><span data-stu-id="cb316-128">Block Scope</span></span>  
 <span data-ttu-id="cb316-129">Блок — это набор операторов, заключенных в начальными и конечными операторы объявления, например следующие:</span><span class="sxs-lookup"><span data-stu-id="cb316-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="cb316-130">`Do` и `Loop`</span><span class="sxs-lookup"><span data-stu-id="cb316-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="cb316-131">`For` [`Each`] и `Next`</span><span class="sxs-lookup"><span data-stu-id="cb316-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="cb316-132">`If` и `End If`</span><span class="sxs-lookup"><span data-stu-id="cb316-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="cb316-133">`Select` и `End Select`</span><span class="sxs-lookup"><span data-stu-id="cb316-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="cb316-134">`SyncLock` и `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="cb316-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="cb316-135">`Try` и `End Try`</span><span class="sxs-lookup"><span data-stu-id="cb316-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="cb316-136">`While` и `End While`</span><span class="sxs-lookup"><span data-stu-id="cb316-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="cb316-137">`With` и `End With`</span><span class="sxs-lookup"><span data-stu-id="cb316-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="cb316-138">Если вы объявляете переменную в пределах блока, его можно использовать только внутри этого блока.</span><span class="sxs-lookup"><span data-stu-id="cb316-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="cb316-139">В следующем примере область целочисленной переменной `cube` представляет собой блок между `If` и `End If`, и вы больше не может ссылаться на `cube` операторами блока.</span><span class="sxs-lookup"><span data-stu-id="cb316-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="cb316-140">Даже если областью видимости переменной ограничен блок, его время существования по-прежнему всей процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb316-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="cb316-141">При вводе блока более одного раза в процессе, каждый блок переменная сохраняет предыдущее значение.</span><span class="sxs-lookup"><span data-stu-id="cb316-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="cb316-142">Чтобы избежать непредвиденных результатов, в этом случае, имеет смысл для инициализации переменных в начале блока.</span><span class="sxs-lookup"><span data-stu-id="cb316-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="cb316-143">Область действия процедуры</span><span class="sxs-lookup"><span data-stu-id="cb316-143">Procedure Scope</span></span>  
 <span data-ttu-id="cb316-144">Элемент, объявленный в процедуре недоступен вне этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb316-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="cb316-145">Его можно использовать только процедура, который содержит объявление.</span><span class="sxs-lookup"><span data-stu-id="cb316-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="cb316-146">Переменные на этом уровне также называются *локальные переменные*.</span><span class="sxs-lookup"><span data-stu-id="cb316-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="cb316-147">Они объявляются с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)с или без [статический](../../../../visual-basic/language-reference/modifiers/static.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="cb316-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="cb316-148">Область процедуры и блок тесно связаны.</span><span class="sxs-lookup"><span data-stu-id="cb316-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="cb316-149">При объявлении переменной внутри процедуры, но вне любого блока, в рамках этой процедуры можно представить что переменная имеет область видимости блока, где блок является всей процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb316-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb316-150">Все локальные элементы, даже если они являются `Static` переменные, процедуры, в котором они появляются.</span><span class="sxs-lookup"><span data-stu-id="cb316-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="cb316-151">Невозможно объявить элемент с использованием [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово в процедуре.</span><span class="sxs-lookup"><span data-stu-id="cb316-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="cb316-152">Области модуля</span><span class="sxs-lookup"><span data-stu-id="cb316-152">Module Scope</span></span>  
 <span data-ttu-id="cb316-153">Для удобства один термин *уровне модуля* применяется одинаково для модулей, классов и структур.</span><span class="sxs-lookup"><span data-stu-id="cb316-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="cb316-154">Можно объявить элементы этого уровня, объявляются за пределами любой процедуры или блока, но внутри модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="cb316-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="cb316-155">При объявлении на уровне модуля, выбранного уровня доступа определяет область.</span><span class="sxs-lookup"><span data-stu-id="cb316-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="cb316-156">Пространство имен, содержащее модуля, класса или структуры также влияет на область.</span><span class="sxs-lookup"><span data-stu-id="cb316-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="cb316-157">Элементы, для которых объявляется [частного](../../../../visual-basic/language-reference/modifiers/private.md) уровень доступа, доступны для каждой процедуры в этом модуле, но не для кода в другом модуле.</span><span class="sxs-lookup"><span data-stu-id="cb316-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="cb316-158">`Dim` Инструкции на уровне модуля по умолчанию равно `Private` Если вы не используете все ключевые слова уровня доступа.</span><span class="sxs-lookup"><span data-stu-id="cb316-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="cb316-159">Тем не менее, внесения областью и нужный уровень доступа более очевидным с помощью `Private` ключевое слово в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cb316-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="cb316-160">В следующем примере все процедуры, определенные в модуле могут ссылаться со строковой переменной `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="cb316-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="cb316-161">Когда вызывается вторая процедура, он отображает содержимое переменной строки `strMsg` в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="cb316-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a><span data-ttu-id="cb316-162">Область видимости пространства имен</span><span class="sxs-lookup"><span data-stu-id="cb316-162">Namespace Scope</span></span>  
 <span data-ttu-id="cb316-163">При объявлении элемента на уровне модуля с [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [открытый](../../../../visual-basic/language-reference/modifiers/public.md) ключевое слово, он становится доступным для всех процедур пространства имен, в котором объявлен элемент.</span><span class="sxs-lookup"><span data-stu-id="cb316-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="cb316-164">Со следующими изменениями в предыдущем примере строковая переменная `strMsg` можно обращаться к любым кодом в ее объявлении пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb316-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="cb316-165">Область видимости пространства имен включает в себя вложенные пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cb316-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="cb316-166">Элемент, доступный в пространстве имен можно получить из любого пространства имен, вложенных в это пространство имен.</span><span class="sxs-lookup"><span data-stu-id="cb316-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="cb316-167">Если проект не содержит [оператор Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, весь проект находится в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="cb316-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="cb316-168">В этом случае область пространства имен может рассматриваться как область проекта.</span><span class="sxs-lookup"><span data-stu-id="cb316-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="cb316-169">`Public` элементы модуля, класса или структуры также доступны для любого проекта, который ссылается на проект.</span><span class="sxs-lookup"><span data-stu-id="cb316-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="cb316-170">Выбор области действия</span><span class="sxs-lookup"><span data-stu-id="cb316-170">Choice of Scope</span></span>  
 <span data-ttu-id="cb316-171">При объявлении переменной, вам следует помнить следующие моменты при выборе ее области действия.</span><span class="sxs-lookup"><span data-stu-id="cb316-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="cb316-172">Преимущества локальных переменных</span><span class="sxs-lookup"><span data-stu-id="cb316-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="cb316-173">Локальные переменные являются хорошим выбором для любого типа временных вычислений по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="cb316-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="cb316-174">**Предотвращение конфликтов имен.**</span><span class="sxs-lookup"><span data-stu-id="cb316-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="cb316-175">Имена локальных переменных не приводит к конфликту.</span><span class="sxs-lookup"><span data-stu-id="cb316-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="cb316-176">Например, можно создать несколько разных процедур, содержащих переменную с именем `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="cb316-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="cb316-177">В течение каждого `intTemp` объявлена как локальная переменная, каждая процедура распознает только свою собственную версию из `intTemp`.</span><span class="sxs-lookup"><span data-stu-id="cb316-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="cb316-178">Любая процедура может изменить значение в ее локальных `intTemp` без влияния на `intTemp` переменных в других процедур.</span><span class="sxs-lookup"><span data-stu-id="cb316-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="cb316-179">**Потребление памяти.**</span><span class="sxs-lookup"><span data-stu-id="cb316-179">**Memory Consumption.**</span></span> <span data-ttu-id="cb316-180">Локальные переменные потребляют память только во время выполнения процедуры.</span><span class="sxs-lookup"><span data-stu-id="cb316-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="cb316-181">Их память освобождается, когда процедура возвращает в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="cb316-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="cb316-182">Напротив [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) и [статический](../../../../visual-basic/language-reference/modifiers/static.md) переменные потребление ресурсов памяти, пока не завершится работа приложения, поэтому использовать их только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="cb316-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="cb316-183">*Переменные экземпляра* потребляют память, пока их экземпляр продолжает существовать, что делает их менее эффективно, чем локальные переменные, но потенциально более эффективно, чем `Shared` или `Static` переменные.</span><span class="sxs-lookup"><span data-stu-id="cb316-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="cb316-184">Сокращение области действия</span><span class="sxs-lookup"><span data-stu-id="cb316-184">Minimizing Scope</span></span>  
 <span data-ttu-id="cb316-185">Как правило, при объявлении любая переменная или константа, он является хорошим стилем программирования вносить Добивайтесь максимального сужения области (области видимости блока является узкая).</span><span class="sxs-lookup"><span data-stu-id="cb316-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="cb316-186">Это помогает освободить ресурсы памяти и сводит к минимуму вероятность коде недопустимой переменной.</span><span class="sxs-lookup"><span data-stu-id="cb316-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="cb316-187">Аналогичным образом, следует объявить переменную [статический](../../../../visual-basic/language-reference/modifiers/static.md) только когда это необходимо сохранить ее значение между вызовами процедур.</span><span class="sxs-lookup"><span data-stu-id="cb316-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb316-188">См. также</span><span class="sxs-lookup"><span data-stu-id="cb316-188">See also</span></span>
- [<span data-ttu-id="cb316-189">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="cb316-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="cb316-190">Практическое руководство. Управление областью действия переменной</span><span class="sxs-lookup"><span data-stu-id="cb316-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="cb316-191">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb316-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="cb316-192">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb316-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="cb316-193">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="cb316-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="cb316-194">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="cb316-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
