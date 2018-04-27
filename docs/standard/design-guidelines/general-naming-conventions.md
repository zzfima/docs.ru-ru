---
title: Общие соглашения об именовании
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 87f866210667905566d75bfed22ba7b9a521abdc
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="general-naming-conventions"></a><span data-ttu-id="5acc8-102">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="5acc8-102">General Naming Conventions</span></span>
<span data-ttu-id="5acc8-103">В этом разделе описаны общие соглашения об именовании, связанные с выбором word, инструкции по использованию сокращений и акронимов и рекомендации о том, как следует избегать использования имен конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="5acc8-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="5acc8-104">Выбор слов</span><span class="sxs-lookup"><span data-stu-id="5acc8-104">Word Choice</span></span>  
 <span data-ttu-id="5acc8-105">**✓ СДЕЛАТЬ** выберите легко читаемые имена идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="5acc8-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="5acc8-106">Например, свойство с именем `HorizontalAlignment` — английский понятным, чем `AlignmentHorizontal`.</span><span class="sxs-lookup"><span data-stu-id="5acc8-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="5acc8-107">**✓ СДЕЛАТЬ** предпочтение краткости удобочитаемости.</span><span class="sxs-lookup"><span data-stu-id="5acc8-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="5acc8-108">Имя свойства `CanScrollHorizontally` лучше, чем `ScrollableX` (запутанные ссылка на ось x).</span><span class="sxs-lookup"><span data-stu-id="5acc8-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="5acc8-109">**X не** использовать другие символы, дефисы и знаки подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5acc8-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="5acc8-110">**X не** венгерская нотация.</span><span class="sxs-lookup"><span data-stu-id="5acc8-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="5acc8-111">**X ИЗБЕГАЙТЕ** использования идентификаторов, совпадающих с ключевыми словами, широко используемые языки программирования.</span><span class="sxs-lookup"><span data-stu-id="5acc8-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="5acc8-112">В соответствии с правилом 4 из общеязыковой спецификацией (CLS) все языки, совместимые с необходимо предоставить механизм, обеспечивающий доступ к именованных элементов, использующих в качестве идентификатора ключевого слова этого языка.</span><span class="sxs-lookup"><span data-stu-id="5acc8-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="5acc8-113">C#, например, используется знак как механизм escape в данном случае @.</span><span class="sxs-lookup"><span data-stu-id="5acc8-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="5acc8-114">Однако она по-прежнему рекомендуется избегать распространенные ключевые слова, так как он является более сложной, можно использовать метод с escape-последовательность, чем другой — нет.</span><span class="sxs-lookup"><span data-stu-id="5acc8-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="5acc8-115">С помощью сокращения и акронимы</span><span class="sxs-lookup"><span data-stu-id="5acc8-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="5acc8-116">**X не** использовать аббревиатуры или сокращения как часть имени идентификатора.</span><span class="sxs-lookup"><span data-stu-id="5acc8-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="5acc8-117">Например, использовать `GetWindow` вместо `GetWin`.</span><span class="sxs-lookup"><span data-stu-id="5acc8-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="5acc8-118">**X не** использовать акронимы, которые не являются широко применяемый и даже в том случае, если они включены, только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="5acc8-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="5acc8-119">Предотвращение имена, зависящие от языка</span><span class="sxs-lookup"><span data-stu-id="5acc8-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="5acc8-120">**✓ СДЕЛАТЬ** используйте семантически значимых имен, а не зарезервированные слова языка имен типов.</span><span class="sxs-lookup"><span data-stu-id="5acc8-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="5acc8-121">Например `GetLength` лучше от имени `GetInt`.</span><span class="sxs-lookup"><span data-stu-id="5acc8-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="5acc8-122">**✓ СДЕЛАТЬ** использовать имя универсального типа CLR, а не имя конкретного языка, в редких случаях, когда идентификатор не имеет семантического значения за пределами своего типа.</span><span class="sxs-lookup"><span data-stu-id="5acc8-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="5acc8-123">Например, преобразование в метод <xref:System.Int64> должен быть назван `ToInt64`, а не `ToLong` (поскольку <xref:System.Int64> — это имя среды CLR для C#-псевдоним `long`).</span><span class="sxs-lookup"><span data-stu-id="5acc8-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="5acc8-124">В следующей таблице представлены некоторые базовые типы данных с помощью имен типов среды CLR (а также соответствующие имена типов для C#, Visual Basic и C++).</span><span class="sxs-lookup"><span data-stu-id="5acc8-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="5acc8-125">C#</span><span class="sxs-lookup"><span data-stu-id="5acc8-125">C#</span></span>|<span data-ttu-id="5acc8-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5acc8-126">Visual Basic</span></span>|<span data-ttu-id="5acc8-127">C++</span><span class="sxs-lookup"><span data-stu-id="5acc8-127">C++</span></span>|<span data-ttu-id="5acc8-128">CLR</span><span class="sxs-lookup"><span data-stu-id="5acc8-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="5acc8-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-129">**sbyte**</span></span>|<span data-ttu-id="5acc8-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-130">**SByte**</span></span>|<span data-ttu-id="5acc8-131">**char**</span><span class="sxs-lookup"><span data-stu-id="5acc8-131">**char**</span></span>|<span data-ttu-id="5acc8-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-132">**SByte**</span></span>|  
|<span data-ttu-id="5acc8-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-133">**byte**</span></span>|<span data-ttu-id="5acc8-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-134">**Byte**</span></span>|<span data-ttu-id="5acc8-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="5acc8-135">**unsigned char**</span></span>|<span data-ttu-id="5acc8-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5acc8-136">**Byte**</span></span>|  
|<span data-ttu-id="5acc8-137">**short**</span><span class="sxs-lookup"><span data-stu-id="5acc8-137">**short**</span></span>|<span data-ttu-id="5acc8-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="5acc8-138">**Short**</span></span>|<span data-ttu-id="5acc8-139">**short**</span><span class="sxs-lookup"><span data-stu-id="5acc8-139">**short**</span></span>|<span data-ttu-id="5acc8-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="5acc8-140">**Int16**</span></span>|  
|<span data-ttu-id="5acc8-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="5acc8-141">**ushort**</span></span>|<span data-ttu-id="5acc8-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5acc8-142">**UInt16**</span></span>|<span data-ttu-id="5acc8-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="5acc8-143">**unsigned short**</span></span>|<span data-ttu-id="5acc8-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5acc8-144">**UInt16**</span></span>|  
|<span data-ttu-id="5acc8-145">**int**</span><span class="sxs-lookup"><span data-stu-id="5acc8-145">**int**</span></span>|<span data-ttu-id="5acc8-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="5acc8-146">**Integer**</span></span>|<span data-ttu-id="5acc8-147">**int**</span><span class="sxs-lookup"><span data-stu-id="5acc8-147">**int**</span></span>|<span data-ttu-id="5acc8-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="5acc8-148">**Int32**</span></span>|  
|<span data-ttu-id="5acc8-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="5acc8-149">**uint**</span></span>|<span data-ttu-id="5acc8-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5acc8-150">**UInt32**</span></span>|<span data-ttu-id="5acc8-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="5acc8-151">**unsigned int**</span></span>|<span data-ttu-id="5acc8-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5acc8-152">**UInt32**</span></span>|  
|<span data-ttu-id="5acc8-153">**long**</span><span class="sxs-lookup"><span data-stu-id="5acc8-153">**long**</span></span>|<span data-ttu-id="5acc8-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="5acc8-154">**Long**</span></span>|<span data-ttu-id="5acc8-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="5acc8-155">**__int64**</span></span>|<span data-ttu-id="5acc8-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="5acc8-156">**Int64**</span></span>|  
|<span data-ttu-id="5acc8-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="5acc8-157">**ulong**</span></span>|<span data-ttu-id="5acc8-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5acc8-158">**UInt64**</span></span>|<span data-ttu-id="5acc8-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="5acc8-159">**unsigned __int64**</span></span>|<span data-ttu-id="5acc8-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5acc8-160">**UInt64**</span></span>|  
|<span data-ttu-id="5acc8-161">**float**</span><span class="sxs-lookup"><span data-stu-id="5acc8-161">**float**</span></span>|<span data-ttu-id="5acc8-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="5acc8-162">**Single**</span></span>|<span data-ttu-id="5acc8-163">**float**</span><span class="sxs-lookup"><span data-stu-id="5acc8-163">**float**</span></span>|<span data-ttu-id="5acc8-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="5acc8-164">**Single**</span></span>|  
|<span data-ttu-id="5acc8-165">**double**</span><span class="sxs-lookup"><span data-stu-id="5acc8-165">**double**</span></span>|<span data-ttu-id="5acc8-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="5acc8-166">**Double**</span></span>|<span data-ttu-id="5acc8-167">**double**</span><span class="sxs-lookup"><span data-stu-id="5acc8-167">**double**</span></span>|<span data-ttu-id="5acc8-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="5acc8-168">**Double**</span></span>|  
|<span data-ttu-id="5acc8-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="5acc8-169">**bool**</span></span>|<span data-ttu-id="5acc8-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5acc8-170">**Boolean**</span></span>|<span data-ttu-id="5acc8-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="5acc8-171">**bool**</span></span>|<span data-ttu-id="5acc8-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5acc8-172">**Boolean**</span></span>|  
|<span data-ttu-id="5acc8-173">**char**</span><span class="sxs-lookup"><span data-stu-id="5acc8-173">**char**</span></span>|<span data-ttu-id="5acc8-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="5acc8-174">**Char**</span></span>|<span data-ttu-id="5acc8-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="5acc8-175">**wchar_t**</span></span>|<span data-ttu-id="5acc8-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="5acc8-176">**Char**</span></span>|  
|<span data-ttu-id="5acc8-177">**string**</span><span class="sxs-lookup"><span data-stu-id="5acc8-177">**string**</span></span>|<span data-ttu-id="5acc8-178">**String**</span><span class="sxs-lookup"><span data-stu-id="5acc8-178">**String**</span></span>|<span data-ttu-id="5acc8-179">**String**</span><span class="sxs-lookup"><span data-stu-id="5acc8-179">**String**</span></span>|<span data-ttu-id="5acc8-180">**String**</span><span class="sxs-lookup"><span data-stu-id="5acc8-180">**String**</span></span>|  
|<span data-ttu-id="5acc8-181">**object**</span><span class="sxs-lookup"><span data-stu-id="5acc8-181">**object**</span></span>|<span data-ttu-id="5acc8-182">**Объект**</span><span class="sxs-lookup"><span data-stu-id="5acc8-182">**Object**</span></span>|<span data-ttu-id="5acc8-183">**Объект**</span><span class="sxs-lookup"><span data-stu-id="5acc8-183">**Object**</span></span>|<span data-ttu-id="5acc8-184">**Объект**</span><span class="sxs-lookup"><span data-stu-id="5acc8-184">**Object**</span></span>|  
  
 <span data-ttu-id="5acc8-185">**СДЕЛАТЬ ✓** использовать общее имя, например `value` или `item`, а не повторять имени типа в редких случаях, когда идентификатор не имеет семантического значения и тип параметра не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="5acc8-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="5acc8-186">Именование новых версий существующих API</span><span class="sxs-lookup"><span data-stu-id="5acc8-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="5acc8-187">**✓ СДЕЛАТЬ** использовать аналогичный API, старое имя, при создании новых версий существующих API.</span><span class="sxs-lookup"><span data-stu-id="5acc8-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="5acc8-188">Это поможет выделить связь между API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="5acc8-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="5acc8-189">**✓ СДЕЛАТЬ** предпочтение Добавление суффикса вместо префикса для указания новой версии существующего API.</span><span class="sxs-lookup"><span data-stu-id="5acc8-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="5acc8-190">Это поможет обнаружения при просмотре документации, или с помощью Intellisense.</span><span class="sxs-lookup"><span data-stu-id="5acc8-190">This will assist discovery when browsing documentation, or using Intellisense.</span></span> <span data-ttu-id="5acc8-191">Старые версии API-интерфейса будут организованы близко к новые интерфейсы API, так как большинство браузеров и Intellisense Показать идентификаторы в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="5acc8-191">The old version of the API will be organized close to the new APIs, because most browsers and Intellisense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="5acc8-192">**✓ Попробуйте** с помощью идентификатора совершенно новый, но может применяться, вместо добавления суффикса и префикса.</span><span class="sxs-lookup"><span data-stu-id="5acc8-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="5acc8-193">**✓ СДЕЛАТЬ** Используйте числовой суффикс для указания новой версии существующего API, особенно в том случае, если имя существующего API-интерфейса только имя, которое имеет смысл (т. е. Если это отраслевой стандарт) и при добавлении любое значимое суффикс (или изменить имя) не приложения параметр ropriate.</span><span class="sxs-lookup"><span data-stu-id="5acc8-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="5acc8-194">**X не** «Ex» (или аналогичный) суффикс идентификатора позволяет отличать его от более ранней версии, такой же API.</span><span class="sxs-lookup"><span data-stu-id="5acc8-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="5acc8-195">**✓ СДЕЛАТЬ** используйте суффикс «64» при внедрении версии API-интерфейсов, работающие с 64-разрядное целое (длинное целое) вместо 32-разрядное целое число.</span><span class="sxs-lookup"><span data-stu-id="5acc8-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="5acc8-196">Необходимо применить такой подход при наличии существующих API 32-разрядной; не делайте этого для нового API-интерфейсов с 64-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="5acc8-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="5acc8-197">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="5acc8-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5acc8-198">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5acc8-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5acc8-199">См. также</span><span class="sxs-lookup"><span data-stu-id="5acc8-199">See Also</span></span>  
 [<span data-ttu-id="5acc8-200">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="5acc8-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="5acc8-201">Правила именования</span><span class="sxs-lookup"><span data-stu-id="5acc8-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
