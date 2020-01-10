---
title: Рекомендации по использованию взаимодействия на уровне машинного кода для .NET
description: Ознакомьтесь с рекомендациями по взаимодействию с компонентами на уровне машинного кода в .NET.
ms.date: 01/18/2019
ms.openlocfilehash: 7fe0dd0545f8ba800174f8be18bb2f11f39463f9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706404"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="53e50-103">Рекомендации по использованию взаимодействия на уровне машинного кода</span><span class="sxs-lookup"><span data-stu-id="53e50-103">Native interoperability best practices</span></span>

<span data-ttu-id="53e50-104">Платформа .NET предоставляет несколько способов настройки машинного кода для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="53e50-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="53e50-105">В этой статье приводятся рекомендации для команд .NET-разработчиков, которые сталкиваются с проблемами взаимодействия на уровне машинного кода.</span><span class="sxs-lookup"><span data-stu-id="53e50-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="53e50-106">Общие рекомендации</span><span class="sxs-lookup"><span data-stu-id="53e50-106">General guidance</span></span>

<span data-ttu-id="53e50-107">Рекомендации в этом разделе относятся ко всем сценариям взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="53e50-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="53e50-108">**✔️ РЕКОМЕНДУЕТСЯ** использовать такие же имена и написание для методов и параметров, как и для метода машинного кода, который вы хотите вызвать.</span><span class="sxs-lookup"><span data-stu-id="53e50-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="53e50-109">**✔️ ДОПУСТИМО** использовать такое же именование и написание для констант.</span><span class="sxs-lookup"><span data-stu-id="53e50-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="53e50-110">**✔️ РЕКОМЕНДУЕТСЯ** использовать типы .NET, которые наиболее сопоставимы с собственным типом.</span><span class="sxs-lookup"><span data-stu-id="53e50-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="53e50-111">Например, если собственный тип в C# — `unsigned int`, используйте `uint`.</span><span class="sxs-lookup"><span data-stu-id="53e50-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="53e50-112">**✔️ РЕКОМЕНДУЕТСЯ** использовать только атрибуты `[In]` и `[Out]`, если реакция на событие, которую нужно реализовать, отличается от реакции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53e50-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="53e50-113">**✔️ ДОПУСТИМО** использовать <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> для заполнения буферов собственного массива.</span><span class="sxs-lookup"><span data-stu-id="53e50-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="53e50-114">**✔️ ДОПУСТИМО** создавать оболочку для объявлений P/Invoke в классе с таким же именем и написанием, как в собственной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="53e50-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="53e50-115">Это позволяет использовать возможность языка C# `nameof` для атрибутов `[DllImport]`, чтобы передать имя собственной библиотеки и проверить правильность его написания.</span><span class="sxs-lookup"><span data-stu-id="53e50-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="53e50-116">Параметры атрибута DllImport</span><span class="sxs-lookup"><span data-stu-id="53e50-116">DllImport attribute settings</span></span>

| <span data-ttu-id="53e50-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="53e50-117">Setting</span></span> | <span data-ttu-id="53e50-118">Default</span><span class="sxs-lookup"><span data-stu-id="53e50-118">Default</span></span> | <span data-ttu-id="53e50-119">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="53e50-119">Recommendation</span></span> | <span data-ttu-id="53e50-120">Подробности</span><span class="sxs-lookup"><span data-stu-id="53e50-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="53e50-121">Оставьте значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="53e50-121">keep default</span></span>  | <span data-ttu-id="53e50-122">Если для параметра явно задано значение false, в результате сбоя запроса HRESULT возвращаются значения, которые вызывают исключения (и в результате возвращаемое значение в месте определения становится пустым).</span><span class="sxs-lookup"><span data-stu-id="53e50-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="53e50-123">в зависимости от API</span><span class="sxs-lookup"><span data-stu-id="53e50-123">depends on the API</span></span>  | <span data-ttu-id="53e50-124">Присвойте этому параметру значение true, если для получения значения в API используется GetLastError и Marshal.GetLastWin32Error.</span><span class="sxs-lookup"><span data-stu-id="53e50-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="53e50-125">Если API устанавливает условие, указывающее на ошибку, перед тем как выполнить другие вызовы, получите информацию об ошибке, чтобы избежать ее непреднамеренной перезаписи.</span><span class="sxs-lookup"><span data-stu-id="53e50-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="53e50-126">`CharSet.None` с откатом к реакции на событие `CharSet.Ansi`</span><span class="sxs-lookup"><span data-stu-id="53e50-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="53e50-127">Если в определении есть строки или символы, используйте `CharSet.Unicode` или `CharSet.Ansi` в явном виде</span><span class="sxs-lookup"><span data-stu-id="53e50-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="53e50-128">Указывает реакцию на событие при маршалинге строк и то, как работает `ExactSpelling`, если задано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="53e50-128">This specifies marshaling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="53e50-129">Обратите внимание, что в Unix `CharSet.Ansi` имеет кодировку UTF8.</span><span class="sxs-lookup"><span data-stu-id="53e50-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="53e50-130">_Обычно_ в Windows используется Юникод, а в Unix — UTF8.</span><span class="sxs-lookup"><span data-stu-id="53e50-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="53e50-131">См. дополнительные сведения в [документации по кодировке](./charset.md).</span><span class="sxs-lookup"><span data-stu-id="53e50-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="53e50-132">Если присвоить этому параметру значение true, можно немного повысить производительность — среда выполнения не будет искать другие имена функций с суффиксом "A" или "W" в зависимости от значения параметра `CharSet` ("A" для `CharSet.Ansi` и "W" для `CharSet.Unicode`).</span><span class="sxs-lookup"><span data-stu-id="53e50-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="53e50-133">Строковые параметры</span><span class="sxs-lookup"><span data-stu-id="53e50-133">String parameters</span></span>

<span data-ttu-id="53e50-134">Если кодировка имеет кодировку Юникод или аргумент явно помечен как `[MarshalAs(UnmanagedType.LPWSTR)]` _и_ строка передается по значению (а не `ref` или `out`), строка закрепляется и используется непосредственно машинным кодом (а не копируется).</span><span class="sxs-lookup"><span data-stu-id="53e50-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="53e50-135">Если требуется обработка строк по стандарту Американского национального института стандартов (ANSI) в явном виде, не забудьте отметить параметр `[DllImport]` как `Charset.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="53e50-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="53e50-136">**❌ не** использовать параметры `[Out] string`.</span><span class="sxs-lookup"><span data-stu-id="53e50-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="53e50-137">Если эта строка интернирована, строковые параметры, передаваемые по значению с атрибутом `[Out]`, могут дестабилизировать среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="53e50-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="53e50-138">См. дополнительные сведения в документации по методу интернирования строк <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53e50-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="53e50-139">**❌ избежать** `StringBuilder` параметров.</span><span class="sxs-lookup"><span data-stu-id="53e50-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="53e50-140">`StringBuilder` во время маршалинга *всегда* создает копию собственного буфера.</span><span class="sxs-lookup"><span data-stu-id="53e50-140">`StringBuilder` marshaling *always* creates a native buffer copy.</span></span> <span data-ttu-id="53e50-141">Таким образом, маршалинг может оказаться крайне неэффективным.</span><span class="sxs-lookup"><span data-stu-id="53e50-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="53e50-142">Выполните обычный сценарий вызова API Windows, который принимает строку:</span><span class="sxs-lookup"><span data-stu-id="53e50-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="53e50-143">Создание SB требуемой емкости (выделяется управляемая емкость) **{1}** .</span><span class="sxs-lookup"><span data-stu-id="53e50-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="53e50-144">Вызвать</span><span class="sxs-lookup"><span data-stu-id="53e50-144">Invoke</span></span>
   1. <span data-ttu-id="53e50-145">Выделяется собственный буфер **{2}** .</span><span class="sxs-lookup"><span data-stu-id="53e50-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="53e50-146">Копирует содержимое, если `[In]` _(значение по умолчанию для параметра `StringBuilder`)_</span><span class="sxs-lookup"><span data-stu-id="53e50-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="53e50-147">Копирует собственный буфер в только что выделенный управляемый массив, если `[Out]` **{3}** _(также значение по умолчанию для `StringBuilder`)_</span><span class="sxs-lookup"><span data-stu-id="53e50-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="53e50-148">Выделение `ToString()` еще одного управляемого массива **{4}** .</span><span class="sxs-lookup"><span data-stu-id="53e50-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="53e50-149">Это *{4}*  распределения для получения строки из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="53e50-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="53e50-150">Чтобы уменьшить их количество, повторно используйте `StringBuilder` в другом вызове. Но это позволяет сэкономить только *одно* распределение.</span><span class="sxs-lookup"><span data-stu-id="53e50-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="53e50-151">Гораздо лучше использовать и кэшировать буфер символов из `ArrayPool` — так вы сможете ограничиться распределением для `ToString()` при последующих вызовах.</span><span class="sxs-lookup"><span data-stu-id="53e50-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="53e50-152">Еще одна проблема, связанная с `StringBuilder`, заключается в том, что этот атрибут всегда создает резервную копию буфера возврата к первому значению NULL.</span><span class="sxs-lookup"><span data-stu-id="53e50-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="53e50-153">Если возвращенная строка не завершена или завершается двумя символами NULL, атрибут P/Invoke задан неправильно (в лучшем случае).</span><span class="sxs-lookup"><span data-stu-id="53e50-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="53e50-154">Если вы все же *используете*`StringBuilder`, возникает еще одна проблема — емкость **не** включает скрытого значения NULL, которое всегда учитывается при взаимодействии.</span><span class="sxs-lookup"><span data-stu-id="53e50-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="53e50-155">Пользователи часто ошибаются, так как для многих API требуется, чтобы в размер буфера *включалось* значение NULL.</span><span class="sxs-lookup"><span data-stu-id="53e50-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="53e50-156">Это может привести к чрезмерному или ненужному распределению.</span><span class="sxs-lookup"><span data-stu-id="53e50-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="53e50-157">Кроме того, эта ошибка не позволяет среде выполнения оптимизировать маршалинг `StringBuilder` для минимизации количества копий.</span><span class="sxs-lookup"><span data-stu-id="53e50-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshaling to minimize copies.</span></span>

<span data-ttu-id="53e50-158">**✔️ ДОПУСТИМО** использовать массивы `char[]` из `ArrayPool`.</span><span class="sxs-lookup"><span data-stu-id="53e50-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="53e50-159">Дополнительные сведения см. в статье [Маршалинг по умолчанию для строк](../../framework/interop/default-marshaling-for-strings.md) и разделе [Customizing string parameters](customize-parameter-marshaling.md#customizing-string-parameters) (Настройка строковых параметров).</span><span class="sxs-lookup"><span data-stu-id="53e50-159">For more information on string marshaling, see [Default Marshaling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshaling](customize-parameter-marshaling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="53e50-160">__Особые параметры Windows__</span><span class="sxs-lookup"><span data-stu-id="53e50-160">__Windows Specific__</span></span>  
> <span data-ttu-id="53e50-161">Для строк `[Out]` в среде выполнения по умолчанию используется `CoTaskMemFree` (для свободных строк) или `SysStringFree` (для строк, обозначенных как `UnmanagedType.BSTR`).</span><span class="sxs-lookup"><span data-stu-id="53e50-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="53e50-162">**В большинстве API с буфером выходной строки:**</span><span class="sxs-lookup"><span data-stu-id="53e50-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="53e50-163">Количество переданных символов должно включать значение NULL.</span><span class="sxs-lookup"><span data-stu-id="53e50-163">The passed in character count must include the null.</span></span> <span data-ttu-id="53e50-164">Если возвращаемое значение меньше, чем количество переданных символов, значит, вызов завершился успешно. В таком случае значение — это количество символов *без* NULL в конце.</span><span class="sxs-lookup"><span data-stu-id="53e50-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="53e50-165">В противном случае это требуемый размер буфера, *включая* нуль-символ.</span><span class="sxs-lookup"><span data-stu-id="53e50-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
>
> - <span data-ttu-id="53e50-166">Передайте 5, Get 4: строка имеет 4 символа с завершающим значением NULL.</span><span class="sxs-lookup"><span data-stu-id="53e50-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="53e50-167">Передайте 5, Get 6: длина строки составляет 5 символов, для хранения значения NULL требуется буфер из 6 символов.</span><span class="sxs-lookup"><span data-stu-id="53e50-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> <span data-ttu-id="53e50-168">[Windows Data Types for Strings](/windows/desktop/Intl/windows-data-types-for-strings) (Типы данных Windows для работы со строками)</span><span class="sxs-lookup"><span data-stu-id="53e50-168">[Windows Data Types for Strings](/windows/desktop/Intl/windows-data-types-for-strings)</span></span>

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="53e50-169">Логические параметры и поля</span><span class="sxs-lookup"><span data-stu-id="53e50-169">Boolean parameters and fields</span></span>

<span data-ttu-id="53e50-170">Логические значения можно легко спутать.</span><span class="sxs-lookup"><span data-stu-id="53e50-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="53e50-171">По умолчанию тип .NET `bool` маршалируется в тип Windows `BOOL`, где имеет 4-байтовое значение.</span><span class="sxs-lookup"><span data-stu-id="53e50-171">By default, a .NET `bool` is marshaled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="53e50-172">Но типы `_Bool` и `bool` в C и C++ имеют размер *один* байт.</span><span class="sxs-lookup"><span data-stu-id="53e50-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="53e50-173">Это может усложнить поиск ошибок, так как половина возвращаемого значения может не учитываться, что, *возможно*, изменит результат.</span><span class="sxs-lookup"><span data-stu-id="53e50-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="53e50-174">См. дополнительные сведения о маршалинге значений .NET `bool` для типов C или C++ `bool` в документации по [настройке маршалинга логического поля](customize-struct-marshaling.md#customizing-boolean-field-marshaling).</span><span class="sxs-lookup"><span data-stu-id="53e50-174">For more for information on marshaling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshaling](customize-struct-marshaling.md#customizing-boolean-field-marshaling).</span></span>

## <a name="guids"></a><span data-ttu-id="53e50-175">Идентификаторы GUID</span><span class="sxs-lookup"><span data-stu-id="53e50-175">GUIDs</span></span>

<span data-ttu-id="53e50-176">Идентификаторы GUID используются непосредственно в сигнатурах.</span><span class="sxs-lookup"><span data-stu-id="53e50-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="53e50-177">Многие API Windows принимают такие псевдонимы типа `GUID&`, как `REFIID`.</span><span class="sxs-lookup"><span data-stu-id="53e50-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="53e50-178">При их передаче по ссылке можно воспользоваться атрибутом `ref` или `[MarshalAs(UnmanagedType.LPStruct)]`.</span><span class="sxs-lookup"><span data-stu-id="53e50-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="53e50-179">GUID</span><span class="sxs-lookup"><span data-stu-id="53e50-179">GUID</span></span> | <span data-ttu-id="53e50-180">Идентификатор GUID для передачи по ссылке</span><span class="sxs-lookup"><span data-stu-id="53e50-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="53e50-181">**❌ не** Используйте `[MarshalAs(UnmanagedType.LPStruct)]` для любого, кроме `ref` параметров GUID.</span><span class="sxs-lookup"><span data-stu-id="53e50-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="53e50-182">Непреобразуемые типы данных</span><span class="sxs-lookup"><span data-stu-id="53e50-182">Blittable types</span></span>

<span data-ttu-id="53e50-183">Непреобразуемые типы — это типы данных с одинаковым представлением на битовом уровне в управляемом и машинном коде.</span><span class="sxs-lookup"><span data-stu-id="53e50-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="53e50-184">Для маршалинга в машинный код и из него эти типы не обязательно преобразовывать в другой формат, что повышает производительность. Поэтому им следует отдавать предпочтение.</span><span class="sxs-lookup"><span data-stu-id="53e50-184">As such they do not need to be converted to another format to be marshaled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="53e50-185">**Непреобразуемые типы данных:**</span><span class="sxs-lookup"><span data-stu-id="53e50-185">**Blittable types:**</span></span>

- <span data-ttu-id="53e50-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="53e50-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="53e50-187">невложенные одномерные массивы непреобразуемых типов (например, `int[]`);</span><span class="sxs-lookup"><span data-stu-id="53e50-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="53e50-188">структуры и классы с фиксированной структурой, содержащие только непреобразуемые значения, например типы полей;</span><span class="sxs-lookup"><span data-stu-id="53e50-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="53e50-189">чтобы обеспечить фиксированную структуру, необходимо указать `[StructLayout(LayoutKind.Sequential)]` или `[StructLayout(LayoutKind.Explicit)]`;</span><span class="sxs-lookup"><span data-stu-id="53e50-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="53e50-190">по умолчанию для структур указывается `LayoutKind.Sequential`, а для классов — `LayoutKind.Auto`</span><span class="sxs-lookup"><span data-stu-id="53e50-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="53e50-191">**Преобразуемые типы данных:**</span><span class="sxs-lookup"><span data-stu-id="53e50-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="53e50-192">**ПЕРИОДИЧЕСКИ преобразуемые типы данных:**</span><span class="sxs-lookup"><span data-stu-id="53e50-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="53e50-193">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="53e50-193">`char`, `string`</span></span>

<span data-ttu-id="53e50-194">Если непреобразуемые типы передаются по ссылке, маршалер просто закрепляет их вместо копирования в промежуточный буфер</span><span class="sxs-lookup"><span data-stu-id="53e50-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="53e50-195">(классы изначально передаются по ссылке, структуры данных передаются по ссылке при использовании атрибутов `ref` или `out`).</span><span class="sxs-lookup"><span data-stu-id="53e50-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="53e50-196">Тип `char` является непреобразуемым в одномерном массиве **или**, если он является частью другого типа, явным образом помечается `[StructLayout]` с `CharSet = CharSet.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="53e50-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="53e50-197">Тип `string` является непреобразуемым, если не содержится в другом типе, и передается как аргумент с атрибутом `[MarshalAs(UnmanagedType.LPWStr)]` или `[DllImport]` имеет набор `CharSet = CharSet.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="53e50-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="53e50-198">Чтобы проверить, является ли тип непреобразуемым, попытайтесь создать закрепленный атрибут `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="53e50-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="53e50-199">Если тип не является строкой или считается непреобразуемым, `GCHandle.Alloc` вызовет `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="53e50-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="53e50-200">**✔️ РЕКОМЕНДУЕТСЯ** по возможности сделать свои структуры данных непреобразуемыми.</span><span class="sxs-lookup"><span data-stu-id="53e50-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="53e50-201">Дополнительные сведения см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="53e50-201">For more information, see:</span></span>

- [<span data-ttu-id="53e50-202">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="53e50-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="53e50-203">Маршалинг типов</span><span class="sxs-lookup"><span data-stu-id="53e50-203">Type Marshaling</span></span>](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="53e50-204">Сохранение управляемых объектов активными</span><span class="sxs-lookup"><span data-stu-id="53e50-204">Keeping managed objects alive</span></span>

<span data-ttu-id="53e50-205">`GC.KeepAlive()` гарантирует, что объект остается в области видимости, пока не будет завершен метод проверки активности KeepAlive.</span><span class="sxs-lookup"><span data-stu-id="53e50-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="53e50-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) позволяет маршалеру сохранять объект активным во время выполнения P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="53e50-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="53e50-207">Его можно использовать вместо `IntPtr` в сигнатурах метода.</span><span class="sxs-lookup"><span data-stu-id="53e50-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="53e50-208">`SafeHandle` фактически заменяет этот класс и должен использоваться вместо него.</span><span class="sxs-lookup"><span data-stu-id="53e50-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="53e50-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) разрешает закреплять управляемый объект и получать собственный указатель на него.</span><span class="sxs-lookup"><span data-stu-id="53e50-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="53e50-210">Базовый шаблон приведен ниже:</span><span class="sxs-lookup"><span data-stu-id="53e50-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="53e50-211">Для `GCHandle` по умолчанию не задано закрепление.</span><span class="sxs-lookup"><span data-stu-id="53e50-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="53e50-212">Еще один основной шаблон предназначен для передачи ссылки на управляемый объект через машинный код и обратно на управляемый код, обычно с обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="53e50-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="53e50-213">Вот этот шаблон:</span><span class="sxs-lookup"><span data-stu-id="53e50-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="53e50-214">Не забывайте, что `GCHandle` необходимо явно освобождать, чтобы избежать утечек памяти.</span><span class="sxs-lookup"><span data-stu-id="53e50-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="53e50-215">Общие типы данных Windows</span><span class="sxs-lookup"><span data-stu-id="53e50-215">Common Windows data types</span></span>

<span data-ttu-id="53e50-216">Ниже приведен список типов данных, часто используемых в API Windows, и типов данных C#, используемых при вызове в виде кода Windows.</span><span class="sxs-lookup"><span data-stu-id="53e50-216">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="53e50-217">Указанные ниже типы имеют одинаковый размер в 32-разрядной и 64-разрядной версиях Windows независимо от их имен.</span><span class="sxs-lookup"><span data-stu-id="53e50-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="53e50-218">Ширина</span><span class="sxs-lookup"><span data-stu-id="53e50-218">Width</span></span> | <span data-ttu-id="53e50-219">Портал</span><span class="sxs-lookup"><span data-stu-id="53e50-219">Windows</span></span>          | <span data-ttu-id="53e50-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="53e50-220">C (Windows)</span></span>          | <span data-ttu-id="53e50-221">C#</span><span class="sxs-lookup"><span data-stu-id="53e50-221">C#</span></span>       | <span data-ttu-id="53e50-222">Альтернатива</span><span class="sxs-lookup"><span data-stu-id="53e50-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="53e50-223">32</span><span class="sxs-lookup"><span data-stu-id="53e50-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="53e50-224">8</span><span class="sxs-lookup"><span data-stu-id="53e50-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="53e50-225">8</span><span class="sxs-lookup"><span data-stu-id="53e50-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="53e50-226">8</span><span class="sxs-lookup"><span data-stu-id="53e50-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="53e50-227">8</span><span class="sxs-lookup"><span data-stu-id="53e50-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="53e50-228">16</span><span class="sxs-lookup"><span data-stu-id="53e50-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="53e50-229">16</span><span class="sxs-lookup"><span data-stu-id="53e50-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="53e50-230">16</span><span class="sxs-lookup"><span data-stu-id="53e50-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="53e50-231">16</span><span class="sxs-lookup"><span data-stu-id="53e50-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="53e50-232">16</span><span class="sxs-lookup"><span data-stu-id="53e50-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="53e50-233">32</span><span class="sxs-lookup"><span data-stu-id="53e50-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="53e50-234">32</span><span class="sxs-lookup"><span data-stu-id="53e50-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="53e50-235">32</span><span class="sxs-lookup"><span data-stu-id="53e50-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="53e50-236">32</span><span class="sxs-lookup"><span data-stu-id="53e50-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="53e50-237">64</span><span class="sxs-lookup"><span data-stu-id="53e50-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="53e50-238">64</span><span class="sxs-lookup"><span data-stu-id="53e50-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="53e50-239">64</span><span class="sxs-lookup"><span data-stu-id="53e50-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="53e50-240">64</span><span class="sxs-lookup"><span data-stu-id="53e50-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="53e50-241">64</span><span class="sxs-lookup"><span data-stu-id="53e50-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="53e50-242">32</span><span class="sxs-lookup"><span data-stu-id="53e50-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="53e50-243">32</span><span class="sxs-lookup"><span data-stu-id="53e50-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |

<span data-ttu-id="53e50-244">Следующие типы являются указателями и зависят от ширины платформы.</span><span class="sxs-lookup"><span data-stu-id="53e50-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="53e50-245">Для них используйте `IntPtr`/`UIntPtr`.</span><span class="sxs-lookup"><span data-stu-id="53e50-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="53e50-246">Типы указателей со знаком (используйте `IntPtr`)</span><span class="sxs-lookup"><span data-stu-id="53e50-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="53e50-247">Типы указателей без знака (используйте `UIntPtr`)</span><span class="sxs-lookup"><span data-stu-id="53e50-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="53e50-248">`PVOID` в Windows — это аналог `void*` в C, который можно маршалировать как `IntPtr` или `UIntPtr`, но рекомендуется по возможности выбирать `void*`.</span><span class="sxs-lookup"><span data-stu-id="53e50-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="53e50-249">Типы данных Windows</span><span class="sxs-lookup"><span data-stu-id="53e50-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="53e50-250">Диапазоны типов данных</span><span class="sxs-lookup"><span data-stu-id="53e50-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="53e50-251">структурам;</span><span class="sxs-lookup"><span data-stu-id="53e50-251">Structs</span></span>

<span data-ttu-id="53e50-252">Управляемые структуры создаются в стеке и не удаляются, пока метод не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="53e50-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="53e50-253">Таким образом, по определению, эти структуры "закреплены" (не перемещаются службой сборки мусора).</span><span class="sxs-lookup"><span data-stu-id="53e50-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="53e50-254">Кроме того, если в машинном коде не используется указатель, по завершении этого метода вы можете получить адрес из блоков неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="53e50-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="53e50-255">Непреобразуемые структуры обеспечивают высокую производительность, так как их можно использовать непосредственно на слое маршалинга.</span><span class="sxs-lookup"><span data-stu-id="53e50-255">Blittable structs are much more performant as they can simply be used directly by the marshaling layer.</span></span> <span data-ttu-id="53e50-256">Попробуйте сделать структуры непреобразуемыми (например, не используйте атрибут `bool`).</span><span class="sxs-lookup"><span data-stu-id="53e50-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="53e50-257">См. дополнительные сведения в разделе [Непреобразуемые типы данных](#blittable-types).</span><span class="sxs-lookup"><span data-stu-id="53e50-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="53e50-258">*Если* структура является непреобразуемой, используйте атрибут `sizeof()` вместо `Marshal.SizeOf<MyStruct>()`, чтобы повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="53e50-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="53e50-259">Как описано выше, чтобы проверить, является ли тип непреобразуемым, попытайтесь создать закрепленный атрибут `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="53e50-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="53e50-260">Если тип не является строкой или считается непреобразуемым, атрибут `GCHandle.Alloc` вызовет `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="53e50-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="53e50-261">Указатели структур в определениях необходимо передавать в `ref` или с помощью `unsafe` и `*`.</span><span class="sxs-lookup"><span data-stu-id="53e50-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="53e50-262">**✔️ РЕКОМЕНДУЕТСЯ** сопоставить управляемую структуру как можно точнее по форме и именам, которые используются в официальной документации платформы или заголовке.</span><span class="sxs-lookup"><span data-stu-id="53e50-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="53e50-263">**✔️ РЕКОМЕНДУЕТСЯ** использовать C# `sizeof()` вместо `Marshal.SizeOf<MyStruct>()` для непреобразуемых структур, чтобы повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="53e50-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="53e50-264">Массив `INT_PTR Reserved1[2]` необходимо маршалировать в два поля `IntPtr`: `Reserved1a` и `Reserved1b`.</span><span class="sxs-lookup"><span data-stu-id="53e50-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="53e50-265">Если собственный массив имеет простой тип, используйте ключевое слово `fixed`, чтобы записать его более точно.</span><span class="sxs-lookup"><span data-stu-id="53e50-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="53e50-266">Например, `SYSTEM_PROCESS_INFORMATION` в заголовке машинного кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="53e50-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="53e50-267">В C# можно написать такой код:</span><span class="sxs-lookup"><span data-stu-id="53e50-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="53e50-268">Но с буферами фиксированного размера возникают некоторые ошибки.</span><span class="sxs-lookup"><span data-stu-id="53e50-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="53e50-269">Буферы фиксированного размера преобразуемых типов не маршалируются правильно, поэтому локальный массив следует развернуть до нескольких отдельных полей.</span><span class="sxs-lookup"><span data-stu-id="53e50-269">Fixed buffers of non-blittable types won't be correctly marshaled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="53e50-270">Кроме того, в .NET Framework и .NET Core версий, предшествующих 3.0, если структура содержит поле буфера фиксированного размера и вложена в преобразуемую структуру, поле буфера фиксированного размера не маршалируется правильно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="53e50-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshaled to native code.</span></span>
