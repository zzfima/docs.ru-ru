---
title: Миграция приложения для магазина Windows в машинный код .NET
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 1942574e832ca7593d91c71370cc0af0c3051617
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455615"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a>Перенос приложения из Магазина Windows в .NET Native

.NET Native обеспечивает статическую компиляцию приложений в магазине Windows или на компьютере разработчика. В отличие от динамической компиляции, выполняемой JIT-компилятором для приложений магазина Windows или [Генератором машинных образов (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) на устройстве. Несмотря на различия, .NET Native пытается обеспечить совместимость с [.NET для приложений Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29). В большинстве случаев все, что работает с .NET для приложений Магазина Windows, также работает с .NET Native.  Тем не менее в некоторых случаях могут произойти изменения поведения. В этом документе обсуждаются различия между стандартом .NET для приложений Магазина Windows и .NET Native в следующих областях:

- [Общие различия среды выполнения](#Runtime)

- [Различия динамического программирования](#Dynamic)

- [Другие различия, связанным с отражением](#Reflection)

- [Неподдерживаемые сценарии и API-интерфейсы](#Unsupported)

- [Различия в Visual Studio](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a>Общие различия среды выполнения

- Исключения, такие как <xref:System.TypeLoadException>, которые выдаются JIT-компилятором при выполнении приложения в среде CLR, обычно приводят к ошибкам во время компиляции при обработке .NET Native.

- Не вызывайте метод <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> из потока пользовательского интерфейса приложения. Это может привести к взаимоблокировке .NET Native.

- Не полагайтесь на порядок вызова конструктора статического класса. В .NET Native порядок вызова отличается от порядка в стандартной среде выполнения. (Даже со стандартной средой выполнения, не следует рассчитывать на порядок выполнения конструкторов статических классов.)

- Бесконечный цикл без вызовов (например, `while(true);`) на любом потоке может привести к остановке приложения. Аналогичным образом, большие или бесконечные ожидания могут также привести приложение к остановке.

- Некоторые базовые циклы инициализации не создают исключения в .NET Native. Например, следующий код создает исключение <xref:System.TypeLoadException> исключений в стандартной среде CLR. В .NET Native это не так.

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- В некоторых случаях .NET Native предоставляет различные реализации библиотек классов .NET Framework. Объект, возвращенный из метода, всегда будет реализовать члены возвращаемого типа. Тем не менее, поскольку его резервная реализация отличается, может оказаться невозможным привести его к тому же набору типов, как это можно было бы сделать на платформах .NET Framework. Например, в некоторых случаях может оказаться невозможным привести объект интерфейса <xref:System.Collections.Generic.IEnumerable%601> , возвращенный такими методами как <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> или <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> , к `T[]`.

- Кэш WinInet не включен по умолчанию в .NET для приложений Магазина Windows, но находится на .NET Native. Это повышает производительность, но сказывается на рабочем наборе. Не требуется никаких действий разработчика.

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a>Различия динамического программирования

.NET Native статические ссылки в коде из .NET Framework, чтобы сделать код локальным для приложения, чтобы обеспечить максимальную производительность. Тем не менее, двоичные размеры должны оставаться небольшими, поэтому не удается подключить всю платформу .NET Framework. Компилятор .NET Native разрешает это ограничение с помощью средства уменьшения зависимостей, которое удаляет ссылки на неиспользуемый код. Однако .NET Native может не поддерживать или генерировать некоторую информацию о типе и код, если эти сведения не могут быть выводиться статически во время компиляции, а вместо этого извлекаются динамически в среде выполнения.

.NET Native включает отражение и динамическое программирование. При этом, не все типы могут быть помечены для отражения, так как это сделает размер созданного кода слишком большим (особенно потому, что поддерживается отражение на общедоступных API в платформе .NET Framework). Компилятор .NET Native делает разумные варианты того, какие типы должны поддерживать отражение, и сохраняет метаданные и создает код только для этих типов.

Например, привязка данных требует, чтобы приложение обеспечивало сопоставление имен свойств с функциями. В приложениях .NET для магазина Windows среда CLR автоматически использует отражение для обеспечения этой возможности для управляемых и общедоступных собственных типов. В .NET Native компилятор автоматически включает метаданные для типов, к которым привязываются данные.

Компилятор .NET Native также может работать с часто используемыми универсальными типами, такими как <xref:System.Collections.Generic.List%601> и <xref:System.Collections.Generic.Dictionary%602>, которые работают без указания каких либо указаний или директив. Ключевое слово [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) также поддерживается в заданных пределах.

> [!NOTE]
> При переносе приложения в .NET Native необходимо тщательно протестировать все динамические пути к коду.

Конфигурация по умолчанию для .NET Native достаточна для большинства разработчиков, но некоторым разработчикам может потребоваться точная настройка конфигурации с помощью файла директив среды выполнения (. Rd. XML). Кроме того, в некоторых случаях компилятору .NET Native не удается определить, какие метаданные должны быть доступны для отражения, и полагаются на указания, особенно в следующих случаях:

- Некоторые конструкции, такие как <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> и <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> не удается определить статически.

- Поскольку компилятор не может определить экземпляры, универсальный тип, который требуется отразить на нем должен быть указан директивами среды выполнения. Это необходимо не только потому, что весь код должен быть включен, но так же и вследствие того, что отражение на универсальных типах могут образовывать бесконечный цикл (например, при вызове универсального метода для универсального типа).

> [!NOTE]
> Директивы среды выполнения определяются в файле директив среды выполнения (. rd.xml). Общие сведения об использовании этого файла см. в разделе [Приступая к работе](getting-started-with-net-native.md). Сведения о директивах среды выполнения см. в разделе [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).

.NET Native также включает средства профилирования, помогающие разработчику определить, какие типы за пределами набора по умолчанию должны поддерживать отражение.

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a>Другие различия, связанным с отражением

Существует ряд других отличий, связанных с отражением в работе .NET для приложений Магазина Windows и .NET Native.

В .NET Native:

- Отражение закрытых типов и членов в библиотеке классов платформы .NET Framework не поддерживается. Тем не менее, можно выполнить отражение на собственных закрытых типах и членах, а также типах и членах библиотек сторонних поставщиков.

- Свойство <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> корректно возвращает `false` для объекта <xref:System.Reflection.ParameterInfo> , который представляет возвращаемое значение. В приложениях .NET для магазина Windows, будет возвращено значение `true`. Промежуточный язык (IL) не поддерживает это непосредственно, и интерпретация выполняется языком.

- Открытые члены на структурах <xref:System.RuntimeFieldHandle> и <xref:System.RuntimeMethodHandle> не поддерживаются. Эти типы поддерживаются только для LINQ, деревьев выражений и инициализации статического массива.

- <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> и <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> включают скрытые члены в базовых классах и поэтому могут переопределяться без явного переопределения. Это также справедливо для других методов [RuntimeReflectionExtensions.GetRuntime*](xref:System.Reflection.RuntimeReflectionExtensions) .

- <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> и <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> не дают сбой при попытке создать определенные комбинации (например, массив byrefs).

- Нельзя использовать отражение для вызова членов, которые содержат параметры указателя.

- Чтобы получить или задать поле указателя, нельзя использовать отражение.

- Если счетчик аргументов неправильный и тип одного из аргументов неверен, .NET Native создает <xref:System.ArgumentException> вместо <xref:System.Reflection.TargetParameterCountException>.

- Обычно двоичная сериализация исключений не поддерживается. В результате несериализуемые объекты могут быть добавлены к словарю <xref:System.Exception.Data%2A?displayProperty=nameWithType> .

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a>Неподдерживаемые сценарии и API-интерфейсы

В следующих разделах перечислены неподдерживаемые сценарии и интерфейсы API для общей разработки, взаимодействия и таких технологий, как HTTPClient и Windows Communication Foundation (WCF):

- [Общая разработка](#General)

- [HttpClient](#HttpClient)

- [Interop](#Interop)

- [Неподдерживаемые API](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a>Различия общей разработки

**Типы значений**

- При переопределении методов <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> и <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> для типа значения не вызывайте реализации базового класса. В приложениях .NET для магазина Windows эти методы основаны на отражении. Во время компиляции .NET Native создает реализацию, которая не зависит от отражения среды выполнения. Это означает, что если вы не переопределяете эти два метода, они будут работать должным образом, так как .NET Native создает реализацию во время компиляции. Однако, переопределение этих методов с помощью вызова реализации базового класса приводит к возникновению исключения.

- Типы значений больше одного мегабайта не поддерживаются.

- Типы значений не могут иметь конструктор без параметров в .NET Native. (C# и Visual Basic запрещает конструкторы без параметров для типов значений. Тем не менее их можно создать в IL.)

**Массивы**

- Массивы с нижней границей, отличной от нуля, не поддерживаются. Как правило, эти массивы создаются путем вызова перегрузки <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .

- Динамическое создание многомерных массивов не поддерживается. Такие массивы обычно создаются путем вызова перегрузки метода <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> , который включает в себя параметр `lengths` , или же путем вызова метода <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .

- Многомерные массивы, имеющие четыре или более измерений не поддерживаются; т.е. их значение свойства <xref:System.Array.Rank%2A?displayProperty=nameWithType> равно или больше четырех. Вместо этого используйте [ступенчатые массивы](../../csharp/programming-guide/arrays/jagged-arrays.md) (массива массивов). Например `array[x,y,z]` является недопустимым, но `array[x][y][z]` нет.

- Вариативность для многомерных массивов не поддерживается и вызывает исключение <xref:System.InvalidCastException> во время выполнения.

**Универсальные шаблоны**

- Расширения бесконечного универсального типа приводят к ошибке компилятора. Например, этот код вызывает ошибку при компиляции:

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

**Pointers**

- Массивы указателей не поддерживается.

- Чтобы получить или задать поле указателя, нельзя использовать отражение.

**Сериализация**

Атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> не поддерживается. Вместо этого используйте атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .

**Ресурсы**

Использование локализованных ресурсов с классом <xref:System.Diagnostics.Tracing.EventSource> не поддерживается. Свойство <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> не определяет локализованные ресурсы.

**Делегаты**

`Delegate.BeginInvoke` и `Delegate.EndInvoke` не поддерживаются.

**Различные API**

- Свойство [typeInfo. GUID](xref:System.Type.GUID) вызывает исключение <xref:System.PlatformNotSupportedException>, если атрибут <xref:System.Runtime.InteropServices.GuidAttribute> не применяется к типу. Идентификатор GUID используется в основном для поддержки модели COM.

- Метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> правильно выполняет синтаксический анализ строк, содержащих короткие даты в .NET Native. Тем не менее он не поддерживает совместимость с синтаксическим анализом изменений даты и времени, описанным в статьях базы знаний Microsoft: [KB2803771](https://support.microsoft.com/kb/2803771) и [KB2803755](https://support.microsoft.com/kb/2803755).

- <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` правильно округляются в .NET Native. В некоторых версиях среды CLR, результирующая строка усекается вместо округления.

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a>Различия HttpClient

В .NET Native класс <xref:System.Net.Http.HttpClientHandler> внутренне использует WinINet (через класс <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter>) вместо классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, используемых в стандартном .NET для приложений Магазина Windows.  WinINet не поддерживает все параметры конфигурации, которые поддерживает класс <xref:System.Net.Http.HttpClientHandler> .  Это приводит к следующим результатам.

- Некоторые свойства возможностей в <xref:System.Net.Http.HttpClientHandler> возвращают `false` в .NET Native, тогда как они возвращают `true` в стандартном .NET для приложений Магазина Windows.

- Некоторые свойства конфигурации `get` методы доступа всегда возвращают фиксированное значение для .NET Native, которое отличается от настраиваемого значения по умолчанию в .NET для приложений Магазина Windows.

В следующих подразделах описаны некоторые дополнительные различия в поведении.

**Прокси-сервер**

Класс <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> не поддерживает настройку или переопределение прокси-сервера для каждого запроса.  Это означает, что все запросы на .NET Native используют настроенный в системе прокси-сервер или не использует прокси-сервер в зависимости от значения свойства <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType>.  В приложениях .NET для магазина Windows, прокси-сервер определяется свойством <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .  В .NET Native при установке <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> в значение, отличное от `null`, вызывает исключение <xref:System.PlatformNotSupportedException>.  Свойство <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> возвращает `false` на .NET Native, в то время как оно возвращает `true` в стандартном .NET Framework для приложений Магазина Windows.

**Автоматическое перенаправление**

Класс <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> не допускает настройку максимального числа автоматических перенаправлений.  Значение свойства <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> равно 50 по умолчанию в стандартных приложениях .NET для магазина Windows и может быть изменено. В .NET Native значение этого свойства равно 10, и при попытке изменить его будет создано исключение <xref:System.PlatformNotSupportedException>.  Свойство <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> возвращает `false` на .NET Native, в то время как оно возвращает `true` в .NET для приложений Магазина Windows.

**Автоматическая распаковка**

Приложения .NET для магазина Windows позволяют задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> на <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>или <xref:System.Net.DecompressionMethods.None>.  .NET Native поддерживает только <xref:System.Net.DecompressionMethods.Deflate> вместе с <xref:System.Net.DecompressionMethods.GZip>или <xref:System.Net.DecompressionMethods.None>.  При попытке задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> только на <xref:System.Net.DecompressionMethods.Deflate> или <xref:System.Net.DecompressionMethods.GZip> происходит его автоматическое задание на оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>.

**Файлы cookie**

Обработка файлов cookie выполняется одновременно с <xref:System.Net.Http.HttpClient> и WinINet.  Файлы cookie из <xref:System.Net.CookieContainer> объединяются вместе файла cookie в кэше WinINet cookie.  Удаление файла cookie из <xref:System.Net.CookieContainer> запрещает <xref:System.Net.Http.HttpClient> отправлять файл cookie, но если файл cookie уже был просмотрен WinINet и файлы "cookie" не были удалены пользователем, WinINet отправляет его.  Не существует средств программного удаления файла cookie из WinINet с использованием API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>или <xref:System.Net.CookieContainer> .  Задание свойства <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> на `false` вызывает только <xref:System.Net.Http.HttpClient> , чтобы остановить отправку файлов "cookie"; WinINet может по-прежнему включить свои файлы cookie в запрос.

**Учетные данные**

В приложениях .NET для магазина Windows свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> и <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> работают независимо друг от друга.  Кроме того, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> принимает любой объект, реализующий интерфейс <xref:System.Net.ICredentials> .  В .NET Native установка свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> в значение `true` приводит к тому, что свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> становится `null`.  Кроме этого, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> может быть задано только в `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>или объект типа <xref:System.Net.NetworkCredential>.  Назначение любого другого объекта <xref:System.Net.ICredentials> , наиболее популярный из которых <xref:System.Net.CredentialCache>, свойству <xref:System.Net.Http.HttpClientHandler.Credentials%2A> вызывает исключение <xref:System.PlatformNotSupportedException>.

**Другие неподдерживаемые и ненастраиваемые функции**

В .NET Native:

- Значение свойства <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> всегда <xref:System.Net.Http.ClientCertificateOption.Automatic>.  В приложения .NET для магазина Windows, по умолчанию используется <xref:System.Net.Http.ClientCertificateOption.Manual>.

- Свойство <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> не настраивается.

- Свойство <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> всегда имеет значение `true`.  В приложения .NET для магазина Windows, по умолчанию используется `false`.

- Заголовок `SetCookie2` в ответах игнорируется как устаревший.

<a name="Interop"></a>
### <a name="interop-differences"></a>Различия взаимодействия
 **Устаревшие интерфейсы API**

 Не рекомендуется использовать несколько редко применяемых API-интерфейсов для взаимодействия с управляемым кодом. При использовании с .NET Native эти API-интерфейсы могут вызывать исключение <xref:System.NotImplementedException> или <xref:System.PlatformNotSupportedException> или привести к ошибке компилятора. В приложениях .NET для магазина Windows эти API-интерфейсы отмечены как устаревшие, хотя их вызов создает предупреждение компилятора, а не ошибку компилятора.

 Устаревшие API-интерфейсы для `VARIANT`ного маршалирования включают:

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> поддерживается, но создает исключение в некоторых сценариях, например когда используется с вариантами [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) или byref.

 Устаревшие API-интерфейсы для поддержки [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) включают:

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

Устаревшие API-интерфейсы для классических событий COM включают:

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

Устаревшие API-интерфейсы в интерфейсе <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>, который не поддерживается в .NET Native, включают:

- <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (все элементы)
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (все элементы)
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (все элементы)
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

К другим неподдерживаемым функциям взаимодействия относятся:

- <xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (все элементы)
- <xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (все элементы)
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 Редко используемые API-интерфейсы для маршалирования:

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 **Вызов неуправляемого кода и совместимость взаимодействия COM**

 В .NET Native по-прежнему поддерживаются большинство сценариев вызова неуправляемого кода и COM-взаимодействия. В частности, поддерживаются все взаимодействия с API среды выполнения Windows (WinRT) и весь необходимый маршалинг для среды выполнения Windows. Это включает поддержку маршалинга:

- Массивы (включая <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)

- `BStr`

- Делегаты

- Строки (Юникод, Ansi и HSTRING)

- Структуры (`byref` и `byval`)

- Объединения

- Дескрипторы Win32

- Все конструкции WinRT

- Частичная поддержка маршалинга типов variant. Поддерживаются следующие функции:

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

Однако .NET Native не поддерживает следующие действия:

- использование классических COM-событий

- Реализация интерфейса <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> на управляемом типе

- Реализация интерфейса [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) в управляемом типе через атрибут <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> . Однако, обратите внимание, что нельзя вызывать COM-объекты через `IDispatch`, а управляемый объект не может реализовать `IDispatch`.

Использование отражения для вызова метода неуправляемого кода не поддерживается. Это ограничение можно обойти путем заключения вызова метода в другой метод, вместо этого используя вызов оболочки.

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Другие отличия от API-интерфейсов приложений .NET для магазина Windows

В этом разделе перечислены остальные API, которые не поддерживаются в .NET Native. Самый большой набор неподдерживаемых интерфейсов API — это API-интерфейсы Windows Communication Foundation (WCF).

**DataAnnotations (System.ComponentModel.DataAnnotations)**

Типы в пространствах имен <xref:System.ComponentModel.DataAnnotations> и <xref:System.ComponentModel.DataAnnotations.Schema> не поддерживаются в .NET Native. К ним относятся следующие типы, которые имеются в .NET для приложений Магазина Windows для Windows 8:

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 **Visual Basic**

Visual Basic в настоящее время не поддерживается в .NET Native. Следующие типы в пространствах имен <xref:Microsoft.VisualBasic> и <xref:Microsoft.VisualBasic.CompilerServices> недоступны в .NET Native:

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

**Контекст отражения (пространство имен System.Reflection.Context)**

Класс <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> не поддерживается в .NET Native.

**Часы реального времени (System.Net.Http.Rtc)**

Класс `System.Net.Http.RtcRequestFactory` не поддерживается в .NET Native.

**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**

Типы в [пространствах имен System. ServiceModel. *](xref:System.ServiceModel) не поддерживаются в .NET Native. В число этих типов входят следующие:

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a>Различия в сериализаторах

Существуют следующие различия, касающиеся сериализации и десериализации с классами <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer> :

- В .NET Native <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не могут сериализовать или десериализовать производный класс, имеющий член базового класса, тип которого не является корневым типом сериализации. Например, в следующем коде при сериализации или десериализации `Y` возникает ошибка:

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  Тип `InnerType` не известен сериализатору, так как члены базового класса не передаются во время сериализации.

- <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать класс или структуру, которая реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> . Например, не удается сериализовать или десериализовать следующие типы:

- <xref:System.Xml.Serialization.XmlSerializer> не удается сериализовать следующие значения объекта, так как он не знает точный тип объекта для сериализации:

- <xref:System.Xml.Serialization.XmlSerializer> не удается сериализация или десериализация, если тип сериализованного объекта <xref:System.Xml.XmlQualifiedName>.

- Все сериализаторам (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer>) не удается создать код сериализации для типа <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> или типа, содержащего <xref:System.Xml.Linq.XElement>. Вместо этого они отображают ошибки во время построения.

- Следующие конструкторы типов сериализации не обязательно работают, как должны:

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>

- <xref:System.Xml.Serialization.XmlSerializer> не удается создать код для типа, который содержит методы, определенные любым из следующих атрибутов:

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <xref:System.Xml.Serialization.XmlSerializer> не поддерживает настраиваемый интерфейс сериализации <xref:System.Xml.Serialization.IXmlSerializable> . Если имеется класс, реализующий этот интерфейс, <xref:System.Xml.Serialization.XmlSerializer> рассматривает тип, как тип объекта (POCO) простой старой среды CLR и сериализует только его открытые свойства.

- Сериализация объекта обычного <xref:System.Exception> не работает с <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

<a name="VS"></a>

## <a name="visual-studio-differences"></a>Различия в Visual Studio

**Исключения и отладка**

При запуске приложений, скомпилированных с помощью .NET Native в отладчике, для исключений First-шанса включаются следующие типы исключений:

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

**Создание приложений**

Используйте средства построения x 86, которые используются по умолчанию в Visual Studio. Не рекомендуется использование средств AMD64 MSBuild, которые находятся в C:\Program Files (x86)\MSBuild\12.0\bin\amd64; Это может создать проблемы построения.

**Профилировщики**

- Профилировщик ЦП в Visual Studio и профилировщик памяти XAML неправильно отображают «только мой код».

- Профилировщик памяти XAML неточно отображает данные управляемой кучи.

- Профилировщик ЦП неправильно идентифицирует модули и отображает имена функций с префиксами.

**Проекты модульных тестов библиотеки**

Включение .NET Native в библиотеке модульных тестов для проекта приложений Магазина Windows не поддерживается и приводит к сбою сборки проекта.

## <a name="see-also"></a>См. также

- [Начало работы](getting-started-with-net-native.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Общие сведения о приложениях .NET для Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [Поддержка платформы .NET Framework для приложений магазина Windows и среды выполнения Windows](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
