---
title: Protected Private (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="9f1be-102">Protected Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f1be-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="9f1be-103">`Private Protected` Сочетание ключевых слов — это модификатор доступа члена.</span><span class="sxs-lookup"><span data-stu-id="9f1be-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="9f1be-104">Объект `Private Protected` член доступны все элементы в его вмещающий класс, а также по типам, производным от содержащего класса, но только если они находятся в его содержащей его сборки.</span><span class="sxs-lookup"><span data-stu-id="9f1be-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span> 

<span data-ttu-id="9f1be-105">Можно указать `Private Protected` только для членов классов; не удается применить `Private Protected` к членам структуры, так как структуры не наследуется.</span><span class="sxs-lookup"><span data-stu-id="9f1be-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="9f1be-106">`Private Protected` Модификатор доступа поддерживается по 15,5 Visual Basic и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="9f1be-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="9f1be-107">Чтобы использовать его, можно добавить следующий элемент в файл проекта (\*.vbproj) Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f1be-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="9f1be-108">При условии, что 15,5 Visual Basic или более поздней версии установлена в системе, она позволяет воспользоваться преимуществами возможности языка, поддерживаемые в последней версии компилятора Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9f1be-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="9f1be-109">В Visual Studio, выбрав Справка F1 на `private protected` предоставляет справку для любого [закрытый](private.md) или [защищенных](protected.md).</span><span class="sxs-lookup"><span data-stu-id="9f1be-109">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="9f1be-110">Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="9f1be-110">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="9f1be-111">Правила</span><span class="sxs-lookup"><span data-stu-id="9f1be-111">Rules</span></span>

- <span data-ttu-id="9f1be-112">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="9f1be-112">**Declaration Context.**</span></span> <span data-ttu-id="9f1be-113">Можно использовать `Private Protected` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="9f1be-113">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="9f1be-114">Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейса, модуля, структуры или процедуры.</span><span class="sxs-lookup"><span data-stu-id="9f1be-114">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="9f1be-115">Поведение</span><span class="sxs-lookup"><span data-stu-id="9f1be-115">Behavior</span></span>

- <span data-ttu-id="9f1be-116">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="9f1be-116">**Access Level.**</span></span> <span data-ttu-id="9f1be-117">Весь код в классе можно получить доступ к его элементам.</span><span class="sxs-lookup"><span data-stu-id="9f1be-117">All code in a class can access its elements.</span></span> <span data-ttu-id="9f1be-118">Код в любой класс, производный от базового класса, содержащихся в той же сборке может получать доступ ко всем `Private Protected` элементы базового класса.</span><span class="sxs-lookup"><span data-stu-id="9f1be-118">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="9f1be-119">Тем не менее, код в любой класс, производный от базового класса, а также содержится в другой сборке не может получить доступ к базовым классом `Private Protected` элементов.</span><span class="sxs-lookup"><span data-stu-id="9f1be-119">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="9f1be-120">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="9f1be-120">**Access Modifiers.**</span></span> <span data-ttu-id="9f1be-121">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="9f1be-121">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="9f1be-122">Сравнение модификаторов доступа см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9f1be-122">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>
  
 <span data-ttu-id="9f1be-123">Модификатор `Private Protected` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="9f1be-123">The `Private Protected` modifier can be used in these contexts:</span></span>  
  
 <span data-ttu-id="9f1be-124">[Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса</span><span class="sxs-lookup"><span data-stu-id="9f1be-124">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>  
  
 [<span data-ttu-id="9f1be-125">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="9f1be-125">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="9f1be-126">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="9f1be-126">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="9f1be-127">[Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенные в классе</span><span class="sxs-lookup"><span data-stu-id="9f1be-127">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>  
  
 [<span data-ttu-id="9f1be-128">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="9f1be-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 <span data-ttu-id="9f1be-129">[Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) eumeration вложенной в классе</span><span class="sxs-lookup"><span data-stu-id="9f1be-129">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an eumeration nested in a class</span></span> 
  
 [<span data-ttu-id="9f1be-130">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="9f1be-130">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="9f1be-131">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="9f1be-131">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 <span data-ttu-id="9f1be-132">[Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса вложены в класс</span><span class="sxs-lookup"><span data-stu-id="9f1be-132">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span> 
  
 [<span data-ttu-id="9f1be-133">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="9f1be-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 <span data-ttu-id="9f1be-134">[Структура инструкции](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенные в классе</span><span class="sxs-lookup"><span data-stu-id="9f1be-134">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span> 
  
 [<span data-ttu-id="9f1be-135">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="9f1be-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f1be-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9f1be-136">See Also</span></span>

[<span data-ttu-id="9f1be-137">Public</span><span class="sxs-lookup"><span data-stu-id="9f1be-137">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="9f1be-138">Protected</span><span class="sxs-lookup"><span data-stu-id="9f1be-138">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="9f1be-139">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="9f1be-139">[Friend](friend.md) </span></span>  
[<span data-ttu-id="9f1be-140">Закрытые</span><span class="sxs-lookup"><span data-stu-id="9f1be-140">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="9f1be-141">[Protected Friend](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="9f1be-141">[Protected Friend](./protected-friend.md) </span></span>  
[<span data-ttu-id="9f1be-142">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f1be-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="9f1be-143">Процедуры</span><span class="sxs-lookup"><span data-stu-id="9f1be-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="9f1be-144">Структуры</span><span class="sxs-lookup"><span data-stu-id="9f1be-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="9f1be-145">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="9f1be-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
