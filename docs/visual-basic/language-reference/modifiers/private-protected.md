---
title: Частный защищенный
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351346"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="cf9f9-102">Частный защищенный (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf9f9-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="cf9f9-103">Комбинация ключевых слов `Private Protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="cf9f9-104">Элемент `Private Protected` доступен для всех элементов в содержащем его классе, а также по типам, производным от содержащего класса, но только в том случае, если они находятся в содержащей его сборке.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="cf9f9-105">Можно указать `Private Protected` только для членов классов; к членам структуры нельзя применять `Private Protected`, поскольку структуры не могут наследоваться.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="cf9f9-106">Модификатор доступа `Private Protected` поддерживается Visual Basic 15,5 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="cf9f9-107">Чтобы использовать его, можно добавить следующий элемент в файл проекта Visual Basic (\*. vbproj).</span><span class="sxs-lookup"><span data-stu-id="cf9f9-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="cf9f9-108">Если в системе установлен Visual Basic 15,5 или более поздней версии, он позволяет воспользоваться всеми возможностями языка, поддерживаемыми последней версией компилятора Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="cf9f9-109">Дополнительные сведения см. [в разделе Задание языковой версии Visual Basic](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f9-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cf9f9-110">В Visual Studio выбор справки F1 в `private protected` предоставляет справку как для [частных](private.md) , так и для [защищенных](protected.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f9-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="cf9f9-111">Интегрированная среда разработки выбирает один маркер под курсором, а не составное слово.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="cf9f9-112">Правила</span><span class="sxs-lookup"><span data-stu-id="cf9f9-112">Rules</span></span>

- <span data-ttu-id="cf9f9-113">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="cf9f9-113">**Declaration Context.**</span></span> <span data-ttu-id="cf9f9-114">`Private Protected` можно использовать только на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="cf9f9-115">Это означает, что контекст объявления для элемента `Protected` должен быть классом и не может быть исходным файлом, пространством имен, интерфейсом, модулем, структурой или процедурой.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="cf9f9-116">Поведение</span><span class="sxs-lookup"><span data-stu-id="cf9f9-116">Behavior</span></span>

- <span data-ttu-id="cf9f9-117">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="cf9f9-117">**Access Level.**</span></span> <span data-ttu-id="cf9f9-118">Весь код в классе может обращаться к его элементам.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-118">All code in a class can access its elements.</span></span> <span data-ttu-id="cf9f9-119">Код в любом классе, производном от базового класса и содержащийся в той же сборке, имеет доступ ко всем `Private Protected`ным элементам базового класса.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="cf9f9-120">Однако код в любом классе, производном от базового класса и содержащийся в другой сборке, не может получить доступ к базовому классу `Private Protected` элементов.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="cf9f9-121">**Модификаторы доступа.**</span><span class="sxs-lookup"><span data-stu-id="cf9f9-121">**Access Modifiers.**</span></span> <span data-ttu-id="cf9f9-122">Ключевые слова, определяющие уровень доступа, называются *модификаторами доступа*.</span><span class="sxs-lookup"><span data-stu-id="cf9f9-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="cf9f9-123">Сравнение модификаторов доступа см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cf9f9-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="cf9f9-124">Модификатор `Private Protected` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="cf9f9-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="cf9f9-125">[Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md) вложенного класса</span><span class="sxs-lookup"><span data-stu-id="cf9f9-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="cf9f9-126">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="cf9f9-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="cf9f9-127">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="cf9f9-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="cf9f9-128">[Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) делегата, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="cf9f9-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="cf9f9-129">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="cf9f9-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="cf9f9-130">[Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md) перечисления, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="cf9f9-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="cf9f9-131">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="cf9f9-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="cf9f9-132">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="cf9f9-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="cf9f9-133">[Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md) интерфейса, вложенного в класс</span><span class="sxs-lookup"><span data-stu-id="cf9f9-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="cf9f9-134">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="cf9f9-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="cf9f9-135">[Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) структуры, вложенной в класс</span><span class="sxs-lookup"><span data-stu-id="cf9f9-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="cf9f9-136">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="cf9f9-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="cf9f9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="cf9f9-137">See also</span></span>

- [<span data-ttu-id="cf9f9-138">Public</span><span class="sxs-lookup"><span data-stu-id="cf9f9-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="cf9f9-139">Protected</span><span class="sxs-lookup"><span data-stu-id="cf9f9-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="cf9f9-140">Friend</span><span class="sxs-lookup"><span data-stu-id="cf9f9-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="cf9f9-141">Закрытые</span><span class="sxs-lookup"><span data-stu-id="cf9f9-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="cf9f9-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="cf9f9-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="cf9f9-143">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf9f9-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="cf9f9-144">Процедуры</span><span class="sxs-lookup"><span data-stu-id="cf9f9-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="cf9f9-145">Структуры</span><span class="sxs-lookup"><span data-stu-id="cf9f9-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="cf9f9-146">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="cf9f9-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
