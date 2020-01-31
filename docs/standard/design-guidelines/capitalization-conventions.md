---
title: Соглашения о написании прописными буквами
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741761"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="6ef76-102">Соглашения о написании прописными буквами</span><span class="sxs-lookup"><span data-stu-id="6ef76-102">Capitalization Conventions</span></span>
<span data-ttu-id="6ef76-103">Рекомендации в этой главе посвящены созданию простого метода использования, который при единообразном применении делает идентификаторы для типов, членов и параметров простыми для чтения.</span><span class="sxs-lookup"><span data-stu-id="6ef76-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="6ef76-104">Правила использования прописных букв для идентификаторов</span><span class="sxs-lookup"><span data-stu-id="6ef76-104">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="6ef76-105">Чтобы отличать слова в идентификаторе, используйте прописные буквы первой буквы каждого слова в идентификаторе.</span><span class="sxs-lookup"><span data-stu-id="6ef76-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="6ef76-106">Не используйте знаки подчеркивания для различения слов, а также для любого значения в любом месте идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="6ef76-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="6ef76-107">Существует два способа для капитализации идентификаторов в зависимости от использования идентификатора.</span><span class="sxs-lookup"><span data-stu-id="6ef76-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="6ef76-108">паскалкасинг</span><span class="sxs-lookup"><span data-stu-id="6ef76-108">PascalCasing</span></span>

- <span data-ttu-id="6ef76-109">камелкасинг</span><span class="sxs-lookup"><span data-stu-id="6ef76-109">camelCasing</span></span>

 <span data-ttu-id="6ef76-110">Соглашение Паскалкасинг, используемое для всех идентификаторов, кроме имен параметров, состоит из первых букв каждого слова (включая акронимы длиной более двух букв), как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="6ef76-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="6ef76-111">Для акронимов с двумя буквами используется специальный случай, в котором буквы записываются прописными буквами, как показано в следующем идентификаторе:</span><span class="sxs-lookup"><span data-stu-id="6ef76-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="6ef76-112">Соглашение Камелкасинг, используемое только для имен параметров, состоит из первых букв каждого слова, за исключением первого слова, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="6ef76-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="6ef76-113">Как показано в примере, аббревиатуры с двумя буквами, начинающиеся с символов в стиле Camel, являются строчными.</span><span class="sxs-lookup"><span data-stu-id="6ef76-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="6ef76-114">✔️ использовать Паскалкасинг для всех имен открытых членов, типов и пространств имен, состоящих из нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="6ef76-114">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="6ef76-115">✔️ использовать Камелкасинг для имен параметров.</span><span class="sxs-lookup"><span data-stu-id="6ef76-115">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="6ef76-116">В следующей таблице описаны правила капитализации для различных типов идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="6ef76-116">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="6ef76-117">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6ef76-117">Identifier</span></span>|<span data-ttu-id="6ef76-118">Различает</span><span class="sxs-lookup"><span data-stu-id="6ef76-118">Casing</span></span>|<span data-ttu-id="6ef76-119">Пример</span><span class="sxs-lookup"><span data-stu-id="6ef76-119">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="6ef76-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6ef76-120">Namespace</span></span>|<span data-ttu-id="6ef76-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-121">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="6ef76-122">Тип</span><span class="sxs-lookup"><span data-stu-id="6ef76-122">Type</span></span>|<span data-ttu-id="6ef76-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-123">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="6ef76-124">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="6ef76-124">Interface</span></span>|<span data-ttu-id="6ef76-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-125">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="6ef76-126">Метод</span><span class="sxs-lookup"><span data-stu-id="6ef76-126">Method</span></span>|<span data-ttu-id="6ef76-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="6ef76-128">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="6ef76-128">Property</span></span>|<span data-ttu-id="6ef76-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="6ef76-130">Event</span><span class="sxs-lookup"><span data-stu-id="6ef76-130">Event</span></span>|<span data-ttu-id="6ef76-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="6ef76-132">Поле</span><span class="sxs-lookup"><span data-stu-id="6ef76-132">Field</span></span>|<span data-ttu-id="6ef76-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="6ef76-134">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="6ef76-134">Enum value</span></span>|<span data-ttu-id="6ef76-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="6ef76-136">Параметр</span><span class="sxs-lookup"><span data-stu-id="6ef76-136">Parameter</span></span>|<span data-ttu-id="6ef76-137">Нижнем</span><span class="sxs-lookup"><span data-stu-id="6ef76-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="6ef76-138">Преобразование сложных слов и общих терминов в прописные</span><span class="sxs-lookup"><span data-stu-id="6ef76-138">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="6ef76-139">Большинство составных терминов рассматриваются как отдельные слова в целях капитализации.</span><span class="sxs-lookup"><span data-stu-id="6ef76-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="6ef76-140">❌ не заменяйте каждое слово на прописные, так называемые составные слова с закрытыми формами.</span><span class="sxs-lookup"><span data-stu-id="6ef76-140">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="6ef76-141">Это составные слова, написанные как одно слово, например конечная точка.</span><span class="sxs-lookup"><span data-stu-id="6ef76-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="6ef76-142">В соответствии с рекомендациями по регистру рассматривайте составное слово с закрытой формой как одно слово.</span><span class="sxs-lookup"><span data-stu-id="6ef76-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="6ef76-143">Используйте текущий словарь, чтобы определить, написано ли составное слово в закрытой форме.</span><span class="sxs-lookup"><span data-stu-id="6ef76-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="6ef76-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="6ef76-144">Pascal</span></span>|<span data-ttu-id="6ef76-145">Нижнем</span><span class="sxs-lookup"><span data-stu-id="6ef76-145">Camel</span></span>|<span data-ttu-id="6ef76-146">not</span><span class="sxs-lookup"><span data-stu-id="6ef76-146">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="6ef76-147">Учет регистра</span><span class="sxs-lookup"><span data-stu-id="6ef76-147">Case Sensitivity</span></span>
 <span data-ttu-id="6ef76-148">Языки, которые могут выполняться в среде CLR, не должны поддерживать чувствительность к регистру, хотя и некоторые.</span><span class="sxs-lookup"><span data-stu-id="6ef76-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="6ef76-149">Даже если ваш язык поддерживает, другие языки, которые могут получить доступ к вашей платформе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6ef76-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="6ef76-150">Все интерфейсы API, доступ к которым осуществляется извне, поэтому не могут полагаться только на регистр, чтобы различать два имени в одном контексте.</span><span class="sxs-lookup"><span data-stu-id="6ef76-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="6ef76-151">❌ не предполагается, что все языки программирования чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="6ef76-151">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="6ef76-152">Это не так.</span><span class="sxs-lookup"><span data-stu-id="6ef76-152">They are not.</span></span> <span data-ttu-id="6ef76-153">Имена не могут отличаться только регистром.</span><span class="sxs-lookup"><span data-stu-id="6ef76-153">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="6ef76-154">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6ef76-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="6ef76-155">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6ef76-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef76-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ef76-156">See also</span></span>

- [<span data-ttu-id="6ef76-157">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="6ef76-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="6ef76-158">Правила именования</span><span class="sxs-lookup"><span data-stu-id="6ef76-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
