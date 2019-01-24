---
title: Private Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 70f725712d52ad055ff69046096da10b8edfb67c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701148"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="763a1-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="763a1-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="763a1-103">Комбинация ключевых слов `Private Protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="763a1-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="763a1-104">Объект `Private Protected` член доступны все элементы в содержащий его класс, так и по типам, производным от содержащего класса, но только в том случае, если они находятся в его соответствующая сборка.</span><span class="sxs-lookup"><span data-stu-id="763a1-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span> 

<span data-ttu-id="763a1-105">Можно указать `Private Protected` только для членов классов; нельзя применить `Private Protected` к членам структуры, так как структуры не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="763a1-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="763a1-106">`Private Protected` Модификатор доступа поддерживается в Visual Basic 15.5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="763a1-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="763a1-107">Чтобы использовать его, можно добавить следующий элемент в проект Visual Basic (\*.vbproj) файла.</span><span class="sxs-lookup"><span data-stu-id="763a1-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="763a1-108">На компьютере установлен столько времени, Visual Basic 15.5 или более поздней версии, можно воспользоваться преимуществами всех функций языка, поддерживаемые в последней версии компилятора Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="763a1-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="763a1-109">Дополнительные сведения см. в разделе [параметр версии языка Visual Basic](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="763a1-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="763a1-110">В Visual Studio, выбрав Справка F1 на `private protected` предоставляет справку для любого [частного](private.md) или [защищенные](protected.md).</span><span class="sxs-lookup"><span data-stu-id="763a1-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="763a1-111">Интегрированная среда разработки выбирает один токен в курсор, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="763a1-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="763a1-112">Правила</span><span class="sxs-lookup"><span data-stu-id="763a1-112">Rules</span></span>

- <span data-ttu-id="763a1-113">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="763a1-113">**Declaration Context.**</span></span> <span data-ttu-id="763a1-114">Можно использовать `Private Protected` только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="763a1-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="763a1-115">Это означает, что контекст объявления для `Protected` элемент должен быть классом и не может быть исходный файл, пространство имен, интерфейс, модуль, структуру или процедуры.</span><span class="sxs-lookup"><span data-stu-id="763a1-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="763a1-116">Поведение</span><span class="sxs-lookup"><span data-stu-id="763a1-116">Behavior</span></span>

- <span data-ttu-id="763a1-117">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="763a1-117">**Access Level.**</span></span> <span data-ttu-id="763a1-118">Весь код в классе можно получить доступ к его элементам.</span><span class="sxs-lookup"><span data-stu-id="763a1-118">All code in a class can access its elements.</span></span> <span data-ttu-id="763a1-119">Код в любой класс, производный от базового класса, содержащийся в той же сборке может получить доступ ко всем `Private Protected` элементы базового класса.</span><span class="sxs-lookup"><span data-stu-id="763a1-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="763a1-120">Тем не менее, код в любом классе, который является производным от базового класса и содержится в другой сборке не может получить доступ к базовым классом `Private Protected` элементов.</span><span class="sxs-lookup"><span data-stu-id="763a1-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="763a1-121">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="763a1-121">**Access Modifiers.**</span></span> <span data-ttu-id="763a1-122">Ключевые слова, указывающие уровень доступа, называются *модификаторы доступа*.</span><span class="sxs-lookup"><span data-stu-id="763a1-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="763a1-123">Сравнение модификаторов доступа, см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="763a1-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>
  
 <span data-ttu-id="763a1-124">Модификатор `Private Protected` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="763a1-124">The `Private Protected` modifier can be used in these contexts:</span></span>  
  
 <span data-ttu-id="763a1-125">[Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса</span><span class="sxs-lookup"><span data-stu-id="763a1-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>  
  
 [<span data-ttu-id="763a1-126">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="763a1-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="763a1-127">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="763a1-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="763a1-128">[Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенные в классе</span><span class="sxs-lookup"><span data-stu-id="763a1-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>  
  
 [<span data-ttu-id="763a1-129">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="763a1-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 <span data-ttu-id="763a1-130">[Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) eumeration вложенной в классе</span><span class="sxs-lookup"><span data-stu-id="763a1-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an eumeration nested in a class</span></span> 
  
 [<span data-ttu-id="763a1-131">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="763a1-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="763a1-132">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="763a1-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 <span data-ttu-id="763a1-133">[Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса, вложенные в классе</span><span class="sxs-lookup"><span data-stu-id="763a1-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span> 
  
 [<span data-ttu-id="763a1-134">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="763a1-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 <span data-ttu-id="763a1-135">[Структура инструкции](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенные в классе</span><span class="sxs-lookup"><span data-stu-id="763a1-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span> 
  
 [<span data-ttu-id="763a1-136">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="763a1-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="763a1-137">См. также</span><span class="sxs-lookup"><span data-stu-id="763a1-137">See also</span></span>

- [<span data-ttu-id="763a1-138">Public</span><span class="sxs-lookup"><span data-stu-id="763a1-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="763a1-139">Protected</span><span class="sxs-lookup"><span data-stu-id="763a1-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="763a1-140">Friend</span><span class="sxs-lookup"><span data-stu-id="763a1-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="763a1-141">Закрытые</span><span class="sxs-lookup"><span data-stu-id="763a1-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="763a1-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="763a1-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="763a1-143">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="763a1-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="763a1-144">Процедуры</span><span class="sxs-lookup"><span data-stu-id="763a1-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="763a1-145">Структуры</span><span class="sxs-lookup"><span data-stu-id="763a1-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="763a1-146">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="763a1-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
