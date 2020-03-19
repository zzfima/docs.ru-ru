---
title: Имена классов, структур и интерфейсов
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401241"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="3cf99-102">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="3cf99-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="3cf99-103">Руководящие принципы именования, которые следуют, применяются к общему наименованию типов.</span><span class="sxs-lookup"><span data-stu-id="3cf99-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="3cf99-104">✔️ классы имен и структур с существительными или существительными фразами, используя PascalCasing.</span><span class="sxs-lookup"><span data-stu-id="3cf99-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="3cf99-105">Это отличает имена типов от методов, которые называются глагольных фраз.</span><span class="sxs-lookup"><span data-stu-id="3cf99-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="3cf99-106">✔️ интерфейсы имен DO с прилагательными фразами, или иногда с существительными или существительными фразами.</span><span class="sxs-lookup"><span data-stu-id="3cf99-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="3cf99-107">Существить и существить фразы должны использоваться редко, и они могут указывать на то, что тип должен быть абстрактным классом, а не интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="3cf99-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="3cf99-108">❌НЕ давайте названия классов приставку (например, "C").</span><span class="sxs-lookup"><span data-stu-id="3cf99-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="3cf99-109">✔️ CONSIDER, заканчивая название выведенных классов с названием базового класса.</span><span class="sxs-lookup"><span data-stu-id="3cf99-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="3cf99-110">Это очень читаемо и объясняет отношения ясно.</span><span class="sxs-lookup"><span data-stu-id="3cf99-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="3cf99-111">Некоторые примеры этого в `ArgumentOutOfRangeException`коде: , `Exception`который `SerializableAttribute`является своего рода `Attribute`, и , который является своего рода .</span><span class="sxs-lookup"><span data-stu-id="3cf99-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="3cf99-112">Однако при применении этого руководства важно использовать разумные суждения; например, `Button` класс является своего `Control` рода `Control` событием, хотя и не отображается в его названии.</span><span class="sxs-lookup"><span data-stu-id="3cf99-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="3cf99-113">✔️ do приставки интерфейса имена с буквой I, чтобы указать, что тип интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3cf99-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="3cf99-114">Например, `IComponent` (описательное `ICustomAttributeProvider` существительное), (существительное) и `IPersistable` (прилагательное) являются подходящими именами интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3cf99-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="3cf99-115">Как и в других именах типов, избегайте сокращений.</span><span class="sxs-lookup"><span data-stu-id="3cf99-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="3cf99-116">✔️ убедиться, что имена отличаются только префиксом "I" на названии интерфейса при определении пары класса и интерфейса, где класс является стандартной реализацией интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3cf99-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="3cf99-117">Названия параметров общего типа</span><span class="sxs-lookup"><span data-stu-id="3cf99-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="3cf99-118">Общие предложения были добавлены в .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3cf99-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="3cf99-119">Функция представила новый вид идентификатора, называемый *параметром типа.*</span><span class="sxs-lookup"><span data-stu-id="3cf99-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="3cf99-120">✔️ значения общих параметров типа DO с описательными именами, если только однобуквенное имя не является полностью понятным и описательное имя не добавит ценности.</span><span class="sxs-lookup"><span data-stu-id="3cf99-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="3cf99-121">✔️ CONSIDER `T` в качестве типа параметра для типов с одним параметром типа одной буквы.</span><span class="sxs-lookup"><span data-stu-id="3cf99-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="3cf99-122">✔️ DO прикрепительное описательное тип параметр имена с `T`.</span><span class="sxs-lookup"><span data-stu-id="3cf99-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="3cf99-123">✔️ CONSIDER, указывающие ограничения, наложенные на параметр типа в названии параметра.</span><span class="sxs-lookup"><span data-stu-id="3cf99-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="3cf99-124">Например, параметр, `ISession` ограниченный `TSession`может быть вызван.</span><span class="sxs-lookup"><span data-stu-id="3cf99-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="3cf99-125">Названия распространенных типов</span><span class="sxs-lookup"><span data-stu-id="3cf99-125">Names of Common Types</span></span>
 <span data-ttu-id="3cf99-126">✔️ do следовать руководящим принципам, описанным в следующей таблице, когда именования типов, полученных из или реализации определенных типов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3cf99-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="3cf99-127">Базовый тип</span><span class="sxs-lookup"><span data-stu-id="3cf99-127">Base Type</span></span>|<span data-ttu-id="3cf99-128">Руководство по типу производных/реализации</span><span class="sxs-lookup"><span data-stu-id="3cf99-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="3cf99-129">✔️ добавить суффикс "Атрибут" к названиям пользовательских классов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="3cf99-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="3cf99-130">✔️ do добавить суффикс "EventHandler" к именам делегатов, которые используются в событиях.</span><span class="sxs-lookup"><span data-stu-id="3cf99-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="3cf99-131">✔️ добавить суффикс "Callback" к именам делегатов, кроме тех, которые используются в качестве обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="3cf99-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="3cf99-132">❌НЕ добавляйте суффикс "Делегат" делегату.</span><span class="sxs-lookup"><span data-stu-id="3cf99-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="3cf99-133">✔️ добавить суффикс "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="3cf99-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="3cf99-134">❌НЕ вытекают из этого класса; вместо этого используйте ключевое слово, поддерживаемое вашим языком; например, в C q, используйте ключевое `enum` слово.</span><span class="sxs-lookup"><span data-stu-id="3cf99-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="3cf99-135">❌НЕ добавляйте суффикс "Enum" или "Flag".</span><span class="sxs-lookup"><span data-stu-id="3cf99-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="3cf99-136">✔️ добавить суффикс "Исключение".</span><span class="sxs-lookup"><span data-stu-id="3cf99-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="3cf99-137">✔️ добавить суффикс "Словарь".</span><span class="sxs-lookup"><span data-stu-id="3cf99-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="3cf99-138">Обратите `IDictionary` внимание, что это определенный тип коллекции, но это руководство имеет приоритет над более общим исправлениям коллекций, которое следует.</span><span class="sxs-lookup"><span data-stu-id="3cf99-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="3cf99-139">✔️ do добавить суффикс "Коллекция".</span><span class="sxs-lookup"><span data-stu-id="3cf99-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="3cf99-140">✔️ DO добавить суффикс "Stream".</span><span class="sxs-lookup"><span data-stu-id="3cf99-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="3cf99-141">✔️ добавить суффикс "Разрешение".</span><span class="sxs-lookup"><span data-stu-id="3cf99-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="3cf99-142">Именование ичислений</span><span class="sxs-lookup"><span data-stu-id="3cf99-142">Naming Enumerations</span></span>
 <span data-ttu-id="3cf99-143">Названия типов перечислений (также называемых перечислениями) в целом должны следовать стандартным правилам именования типов (PascalCasing и т.д.).</span><span class="sxs-lookup"><span data-stu-id="3cf99-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="3cf99-144">Однако существуют дополнительные руководящие принципы, которые применяются конкретно к перечислениям.</span><span class="sxs-lookup"><span data-stu-id="3cf99-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="3cf99-145">✔️ do использовать имя единственного типа для перечисления, если его значения не являются битовыми полями.</span><span class="sxs-lookup"><span data-stu-id="3cf99-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="3cf99-146">✔️ do использовать имя типа множественного числа для перечисления с битовыми полями в качестве значений, также называемых флагами enum.</span><span class="sxs-lookup"><span data-stu-id="3cf99-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="3cf99-147">❌НЕ используйте суффикс "Enum" в именах типов enum.</span><span class="sxs-lookup"><span data-stu-id="3cf99-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="3cf99-148">❌НЕ используйте суффиксы "Flag" или "Flags" в именах типов enum.</span><span class="sxs-lookup"><span data-stu-id="3cf99-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="3cf99-149">❌НЕ используйте префикс на именах значений перечисления (например, "объявление" для enums ADO, "rtf" для богатых текстовых перечислений и т.д.).</span><span class="sxs-lookup"><span data-stu-id="3cf99-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="3cf99-150">*Порции © 2005, 2009 Microsoft Corporation. Все права зарезервированы.*</span><span class="sxs-lookup"><span data-stu-id="3cf99-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3cf99-151">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3cf99-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf99-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cf99-152">See also</span></span>

- [<span data-ttu-id="3cf99-153">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="3cf99-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="3cf99-154">Правила именования</span><span class="sxs-lookup"><span data-stu-id="3cf99-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
