---
title: Модель асинхронного программирования задач (TAP) с использованием ключевых слов async и await (C#)
ms.date: 05/22/2017
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
ms.openlocfilehash: 8f88ecc05fd21a3526478cf564dc4fa97f309f7e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969967"
---
# <a name="task-asynchronous-programming-model"></a>Асинхронная модель программирования

Асинхронное программирование позволяет избежать появления узких мест производительности и увеличить общую скорость реагирования приложения. Однако традиционные методы создания асинхронных приложений могут оказаться сложными, как в плане написания кода, так и в плане отладки и обслуживания.

[C# 5](../../../whats-new/csharp-version-history.md#c-version-50) вводит упрощенный подход асинхронного программирования, который использует асинхронные возможности .NET Framework 4.5 и более поздних версий, .NET Core и среды выполнения Windows. Компилятор выполняет сложную работу, которую раньше делал разработчик, при этом логическая структура кода приложения похожа на синхронный код. То есть можно пользоваться всеми преимуществами асинхронного программирования с гораздо меньшими, чем обычно, трудозатратами.

В этом разделе рассматриваются области и методы использования асинхронного программирования, а также приводятся ссылки на вспомогательные разделы с дополнительными сведениями и примерами.

## <a name="BKMK_WhentoUseAsynchrony"></a> Async повышает скорость реагирования

Асинхронность необходимо использовать при наличии потенциально блокирующих работу действий, например при осуществлении доступа к Интернету. Доступ к веб-ресурсу иногда осуществляется медленно или с задержкой. Если такое действие блокируется в синхронном процессе, все приложение вынуждено ожидать. В асинхронном процессе приложение может перейти к следующей операции, не зависящей от веб-ресурса, до завершения блокирующей задачи.

В следующей таблице показаны стандартные области, в которых асинхронное программирование повышает скорость реагирования. Перечисленные API-интерфейсы платформы .NET и среды выполнения Windows содержат методы, поддерживающие асинхронное программирование.

| Область приложения    | Типы .NET с методами Async     | Типы среды выполнения Windows с методами Async  |
|---------------------|-----------------------------------|-------------------------------------------|
|Веб-доступ|<xref:System.Net.Http.HttpClient>|<xref:Windows.Web.Syndication.SyndicationClient>|
|Работа с файлами|<xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader>|<xref:Windows.Storage.StorageFile>|
|Работа с образами||<xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder>|
|Программирование с использованием WCF|[Синхронные и асинхронные операции](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)||

Асинхронность особенно полезна в приложениях, которые обращаются к потоку пользовательского интерфейса, поскольку все связанные с пользовательским интерфейсом действия обычно используют один поток. В синхронном приложении блокировка одного процесса приводит к блокировке всех процессов. Приложение перестает отвечать, и это выглядит как сбой, а не как ожидание.

При использовании асинхронных методов приложение продолжает реагировать на действия в пользовательском интерфейсе. Например, можно изменить размер окна или свернуть его, либо закрыть приложение, если не требуется ждать завершения работы.

Асинхронный подход добавляет эквивалент автоматической передачи в список параметров, выбранных при создании асинхронных операций. То есть разработчик может пользоваться всеми преимуществами традиционного асинхронного программирования, прикладывая гораздо меньше усилий.

## <a name="BKMK_HowtoWriteanAsyncMethod"></a> Методы Async проще создавать

В C# основой асинхронного программирования. являются ключевые слова [async](../../../language-reference/keywords/async.md) и [await](../../../language-reference/operators/await.md). Они позволяют использовать ресурсы платформы .NET Framework, .NET Core или среды выполнения Windows для создания асинхронных методов, и это почти так же просто, как создавать синхронные методы. Асинхронные методы, которые определяются с помощью ключевого слова `async`, называются *методами async*.

Ниже приводится пример асинхронного метода. Почти все элементы кода должны быть вам знакомы.

Полный файл примера Windows Presentation Foundation представлен в конце раздела. Также его можно скачать на странице [примера асинхронной работы из руководства по использованию ключевых слов Async и Await](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-cs/).

```csharp
async Task<int> AccessTheWebAsync()
{
    // You need to add a reference to System.Net.Http to declare client.
    var client = new HttpClient();

    // GetStringAsync returns a Task<string>. That means that when you await the
    // task you'll get a string (urlContents).
    Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com/dotnet");

    // You can do work here that doesn't rely on the string from GetStringAsync.
    DoIndependentWork();

    // The await operator suspends AccessTheWebAsync.
    //  - AccessTheWebAsync can't continue until getStringTask is complete.
    //  - Meanwhile, control returns to the caller of AccessTheWebAsync.
    //  - Control resumes here when getStringTask is complete.
    //  - The await operator then retrieves the string result from getStringTask.
    string urlContents = await getStringTask;

    // The return statement specifies an integer result.
    // Any methods that are awaiting AccessTheWebAsync retrieve the length value.
    return urlContents.Length;
}
```

Из предыдущего примера вы можете узнать несколько полезных методик. Начните с сигнатуры метода. Она включает модификатор `async`. Типом возвращаемого значения является `Task<int>` (дополнительные параметры см. в разделе "Типы возвращаемых значений"). Имя метода заканчивается на `Async`. В теле метода `GetStringAsync` возвращает `Task<string>`. Это означает, что когда вы ожидаете (`await`) задачу, то получаете `string` (`urlContents`).  Прежде чем ожидать задачу, можно сделать работу, которая не зависит от `string` из `GetStringAsync`.

Обратите внимание на оператор `await`. Он приостанавливает `AccessTheWebAsync`.

- `AccessTheWebAsync` не может продолжить выполнение до завершения `getStringTask`.
- На это время управление возвращается вызывающему объекту метода `AccessTheWebAsync`.
- Управление возобновляется после завершения `getStringTask`.
- Оператор `await` извлекает результат `string` из `getStringTask`.

Оператор return указывает целочисленный результат. Все методы, ожидающие `AccessTheWebAsync`, получают значение длины.

Если метод `AccessTheWebAsync` не выполняет никакие операции между вызовом метода `GetStringAsync` и его завершением, можно упростить код, описав вызов и ожидание с помощью следующего простого оператора.

```csharp
string urlContents = await client.GetStringAsync("https://docs.microsoft.com/dotnet");
```

Далее поясняется, почему код предыдущего примера является асинхронным методом:

- Сигнатура метода включает модификатор `async`.
- Имя асинхронного метода, как правило, оканчивается суффиксом Async.
- Возвращаемое значение имеет один из следующих типов:

  - <xref:System.Threading.Tasks.Task%601>, если метод включает оператор return с операндом типа `TResult`.
  - <xref:System.Threading.Tasks.Task>, если метод не имеет оператора Return или имеет оператор Return без операнда.
  - `void`, если вы создаете асинхронный обработчик событий.
  - Любой другой тип, имеющий метод `GetAwaiter` (начиная с C# 7.0).

  Дополнительные сведения см. в [описании типов возвращаемого значения и параметров](#BKMK_ReturnTypesandParameters).

- Метод обычно содержит по меньшей мере одно выражение `await`, отмечающее точку, в которой метод не может продолжить выполнение до завершения асинхронной операции. На это время метод приостанавливается и управление возвращается к вызывающему объекту метода. В следующем подразделе показано, что происходит в точке приостановки.

В асинхронных методах с помощью соответствующих ключевых слов и типов указывается, что требуется сделать, а компилятор выполняет остальные задачи, в том числе отслеживает обязательные действия, когда управление возвращается в точку await в приостановленном методе. Некоторые программные процессы, такие как циклы и обработка исключений, сложно добавлять в традиционный асинхронный код. В асинхронном методе эти элементы пишутся почти так же, как в синхронном решении, что очень удобно.

Дополнительные сведения об асинхронности в предыдущих версиях платформы .NET Framework, см. в статье [TPL and Traditional .NET Framework Asynchronous Programming](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md) (Библиотека параллельных задач и традиционное асинхронное программирование в .NET Framework).

## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Что происходит в методе Async

В асинхронном программировании важнее всего понимать, как поток управления перемещается из метода в метод. Следующая схема описывает этот процесс.

![Трассировка асинхронной программы](./media/task-asynchronous-programming-model/navigation-trace-async-program.png "NavigationTrace")

Числа в схеме соответствуют следующим шагам, запускаемым при нажатии пользователем кнопки запуска.

1. Обработчик событий вызывает и ожидает асинхронный метод `AccessTheWebAsync`.

2. `AccessTheWebAsync` создает экземпляр <xref:System.Net.Http.HttpClient> и вызывает асинхронный метод <xref:System.Net.Http.HttpClient.GetStringAsync%2A>, чтобы загрузить содержимое веб-сайта в виде строки.

3. В `GetStringAsync` происходит событие, которое приостанавливает ход выполнения. Например, методу необходимо подождать завершения загрузки или произошло другое блокирующее действие. Чтобы избежать блокировки ресурсов, `GetStringAsync` передает управление вызывающему объекту `AccessTheWebAsync`.

     `GetStringAsync` возвращает <xref:System.Threading.Tasks.Task%601>, где `TResult` — строка, а `AccessTheWebAsync` присваивает задачу переменной `getStringTask`. Задача представляет собой непрерывный процесс для вызова `GetStringAsync` с обязательством создать фактическое значение строки, когда работа будет завершена.

4. Поскольку значение из процесса `getStringTask` еще не получено, метод `AccessTheWebAsync` может перейти к другим операциям, не зависящим от конечного результата`GetStringAsync`. Эти операции представлены вызовом синхронного метода `DoIndependentWork`.

5. `DoIndependentWork` — это синхронный метод, который выполняет свой код и возвращает управление вызывающему объекту.

6. Метод `AccessTheWebAsync` выполнил все операции, для которых не требуется результат процесса `getStringTask`. Далее метод `AccessTheWebAsync` должен вычислить длину загруженной строки и возвратить ее, но не может этого сделать, пока нет строки.

     Поэтому `AccessTheWebAsync` использует оператор await, чтобы приостановить свою работу и передать управление методу, вызвавшему `AccessTheWebAsync`. `AccessTheWebAsync` возвращает вызывающему объекту `Task<int>`. Задача представляет собой обещание создать целочисленный результат, являющийся длиной загруженной строки.

    > [!NOTE]
    > Если метод `GetStringAsync` (и, следовательно, процесс `getStringTask`) завершается прежде, чем этого дождется `AccessTheWebAsync`, управление остается у метода `AccessTheWebAsync`. На приостановку метода `AccessTheWebAsync` и последующий возврат к нему были бы потрачены лишние ресурсы, если вызываемый асинхронный процесс (`getStringTask`) уже завершен и `AccessTheWebAsync` не нужно ждать окончательного результата.

     Внутри вызывающего объекта (в данном примере — обработчика событий) шаблон обработки повторяется. Вызывающий объект может выполнять другие операции, не зависящие от результата `AccessTheWebAsync`, во время ожидания этого результата, или сразу ожидать результата.   Обработчик событий ожидает `AccessTheWebAsync`, а `AccessTheWebAsync` ожидает `GetStringAsync`.

7. `GetStringAsync` завершается и создает строковый результат. Вызов возвращает строковый результат в метод `GetStringAsync`, но не так, как, возможно, ожидалось. (Помните, что метод уже возвратил задачу в шаге 3.) Вместо этого строковый результат хранится в задаче `getStringTask`, которая представляет собой завершение метода. Оператор await извлекает результат из `getStringTask`. Оператор присваивания назначает извлеченный результат `urlContents`.

8. Если `AccessTheWebAsync` содержит строковый результат, метод может вычислить длину строки. Затем работа `AccessTheWebAsync` также завершена, и ожидающий обработчик событий может возобновить работу. В полном примере в конце этого раздела видно, что обработчик событий извлекает значение длины и выводит результат.
Если вы недавно занимаетесь асинхронным программированием, рекомендуем обратить внимание на различия между синхронным и асинхронным поведением. Синхронный метод возвращает управление, когда его работа завершается (шаг 5), тогда как асинхронный метод возвращает значение задачи, когда его работа приостанавливается (шаги 3 и 6). Когда асинхронный метод в конечном счете завершает работу, задача помечается как завершенная и результат, при его наличии, сохраняется в задаче.

Дополнительные сведения о потоке управления см. в статье [Control Flow in Async Programs (C#)](control-flow-in-async-programs.md) (Поток управления в асинхронных программах на C#).

## <a name="BKMK_APIAsyncMethods"></a> Async-методы API-интерфейсов

Где же найти методы для асинхронного программирования (такие как `GetStringAsync`)? Платформа .NET Framework 4.5 и более поздние версии, а также .NET Core содержат большое количество элементов, совместимых с `async` и `await`. Они содержат суффикс Async в имени элемента и возвращают тип <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Например, класс `System.IO.Stream` имеет такие методы, как <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> и <xref:System.IO.Stream.WriteAsync%2A>, наряду с синхронными методами <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> и <xref:System.IO.Stream.Write%2A>.

Среда выполнения Windows также содержит множество методов, которые можно использовать в сочетании с `async` и `await` в приложениях Windows. См. дополнительные сведения о [потоковом и асинхронном программировании](/windows/uwp/threading-async/) для разработки UWP, [асинхронном программировании (приложения Магазина Windows)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)), а также [вызове асинхронных API в C# или Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/hh452713(v=win.10)), если вы используете предыдущие версии среды выполнения Windows.

## <a name="BKMK_Threads"></a> Потоки

Асинхронные методы используются для неблокирующих операций. Выражение `await` в асинхронном методе не блокирует текущий поток на время выполнения ожидаемой задачи. Вместо этого выражение регистрирует остальную часть метода как продолжение и возвращает управление вызывающему объекту асинхронного метода.

Ключевые слова `async` и `await` не вызывают создания дополнительных потоков. Асинхронные методы не требуют многопоточности, поскольку асинхронный метод не выполняется в собственном потоке. Метод выполняется в текущем контексте синхронизации и использует время в потоке, только когда метод активен. Метод <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> можно применять для перемещения операций, использующих ресурсы ЦП, в фоновый поток, однако фоновый поток не имеет смысла применять для процесса, который просто ждет результата.

Асинхронный подход к асинхронному программированию практически по всем параметрам имеет преимущество перед другими подходами. В частности, такой подход эффективнее, чем использование класса <xref:System.ComponentModel.BackgroundWorker> для привязанных к вводу-выводу операций, так как используется более простой код и вам не нужно специально предотвращать состояние гонки. В сочетании с методом <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> асинхронное программирование лучше <xref:System.ComponentModel.BackgroundWorker> для операций, использующих ресурсы процессора, так как оно отделяет координацию выполнения кода от действий, которые `Task.Run` перемещает в пул потоков.

## <a name="BKMK_AsyncandAwait"></a> Async и Await

Если с помощью модификатора [async](../../../language-reference/keywords/async.md) указать, что метод является асинхронным, у вас появятся следующие две возможности.

- Асинхронный метод сможет использовать [await](../../../language-reference/operators/await.md) для обозначения точек приостановки. Оператор `await` сообщает компилятору, что асинхронный метод не может выполняться после этой точки до завершения ожидаемого асинхронного процесса. На это время управление возвращается вызывающему объекту асинхронного метода.

     Приостановка асинхронного метода на выражении `await` не считается выходом из метода, и блоки `finally` не выполняются.

- Сам обозначенный асинхронный метод может ожидаться вызывающими его методами.

Асинхронный метод обычно содержит одно или несколько вхождений оператора `await`, но отсутствие выражений `await` не вызывает ошибок компилятора. Если асинхронный метод не использует оператор `await` для обозначения точки приостановки, метод выполняется как синхронный независимо от наличия модификатора `async`. При компиляции таких методов выдается предупреждение.

`async` и `await` являются контекстными ключевыми словами. Дополнительные сведения и примеры см. в следующих разделах:

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)

## <a name="BKMK_ReturnTypesandParameters"></a> Типы и параметры возвращаемого значения

В результате работы асинхронного метода обычно возвращается <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>. Внутри асинхронного метода оператор `await` применяется к задаче, возвращаемой из вызова другого асинхронного метода.

В качестве возвращаемого типа указывается <xref:System.Threading.Tasks.Task%601>, если метод содержит оператор [`return`](../../../language-reference/keywords/return.md), который задает операнд типа `TResult`.

Используйте <xref:System.Threading.Tasks.Task> в качестве возвращаемого типа, если метод не содержит операторов return или содержит оператор return, который не возвращает операнд.

В C# начиная с версии 7.0 также можно указывать любые другие типы операторов return, при условии, что тип содержит метод `GetAwaiter`. Пример такого типа — <xref:System.Threading.Tasks.ValueTask%601>. Он доступен в NuGet-пакете [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/).

В следующем примере показано объявление и вызов метода, который возвращает <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>:

```csharp
// Signature specifies Task<TResult>
async Task<int> GetTaskOfTResultAsync()
{
    int hours = 0;
    await Task.Delay(0);
    // Return statement specifies an integer result.
    return hours;
}

// Calls to GetTaskOfTResultAsync
Task<int> returnedTaskTResult = GetTaskOfTResultAsync();
int intResult = await returnedTaskTResult;
// or, in a single statement
int intResult = await GetTaskOfTResultAsync();

// Signature specifies Task
async Task GetTaskAsync()
{
    await Task.Delay(0);
    // The method has no return statement.
}

// Calls to GetTaskAsync
Task returnedTask = GetTaskAsync();
await returnedTask;
// or, in a single statement
await GetTaskAsync();
```

Каждая возвращенная задача представляет выполняющуюся работу. Задача инкапсулирует информацию о состоянии асинхронного процесса и, в итоге, либо конечный результат процесса, либо исключение, созданное процессом в случае его сбоя.

Асинхронный метод может иметь тип возвращаемого значения `void`. Возвращаемый тип в основном используется для определения обработчиков событий, где требуется возвращать тип `void`. Асинхронные обработчики событий часто служат в качестве отправной точки для асинхронных программ.

Асинхронный метод, который имеет тип возвращаемого значения `void`, невозможно ожидать методом await. Вызывающий объект не может перехватывать исключения, которые выдает такой метод.

Асинхронный метод не может объявлять параметры [in](../../../language-reference/keywords/in-parameter-modifier.md), [ref](../../../language-reference/keywords/ref.md) или [out](../../../language-reference/keywords/out-parameter-modifier.md), но может вызывать методы с этими параметрами. Аналогичным образом, асинхронный метод не может возвращать значение по ссылке, несмотря на то, что он может вызывать методы с возвращаемыми значениями ref.

Дополнительные сведения и примеры см. в статье [о типах возвращаемых значений асинхронных операций](./async-return-types.md). Дополнительные сведения о перехвате исключений в асинхронных методах см. в описании механизма [try-catch](../../../language-reference/keywords/try-catch.md).

При программировании в среде выполнения Windows асинхронные API-интерфейсы имеют один из следующих возвращаемых типов, которые похожи на задачи.

- <xref:Windows.Foundation.IAsyncOperation%601>, что соответствует <xref:System.Threading.Tasks.Task%601>
- <xref:Windows.Foundation.IAsyncAction>, что соответствует <xref:System.Threading.Tasks.Task>
- <xref:Windows.Foundation.IAsyncActionWithProgress%601>
- <xref:Windows.Foundation.IAsyncOperationWithProgress%602>

## <a name="BKMK_NamingConvention"></a> Соглашение об именовании

По соглашению имена методов, возвращающих обычно поддерживающие ожидание типы (например, `Task`, `Task<T>`, `ValueTask` и `ValueTask<T>`), должны заканчиваться на Async. Имена методов, которые запускают асинхронную операцию, но не возвращают поддерживающий ожидание тип, не должны заканчиваться на Async, но могут начинаться с Begin, Start или другой команды, предполагающей, что метод не возвращает и не выдает результат операции.

Соглашение можно игнорировать в тех случаях, когда событие, базовый класс или контракт интерфейса предлагает другое имя. Например, не следует переименовывать общие обработчики событий, такие как `Button1_Click`.

## <a name="BKMK_RelatedTopics"></a> Связанные разделы и примеры (Visual Studio)

|Заголовок|Описание|Пример|
|-----------|-----------------|------------|
|[Пошаговое руководство. Доступ к Интернету с помощью модификатора Async и оператора Await в C#](./walkthrough-accessing-the-web-by-using-async-and-await.md)|Иллюстрирует преобразование синхронного решения WPF в асинхронное. Приложение загружает ряд веб-сайтов.|[Пример использования Async. Пошаговое руководство по обращению к веб-сайтам](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|
|[Практическое руководство. Расширение пошагового руководства по асинхронным процедурам с использованием метода Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Добавляет <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> к предыдущему пошаговому руководству. Использование `WhenAll` запускает все загрузки одновременно.||
|[Практическое руководство. Параллельное выполнение нескольких веб-запросов с использованием Async и Await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Иллюстрирует, как запустить несколько задач одновременно.|[Пример использования Async. Параллельное выполнение нескольких веб-запросов](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|
|[Async Return Types (C#)](./async-return-types.md) (Типы возвращаемых значений асинхронных операций в C#)|Иллюстрирует типы, которые могут возвращать асинхронные методы, и поясняет, когда следует использовать каждый из этих типов.||
|[Control Flow in Async Programs (C#)](./control-flow-in-async-programs.md) (Поток управления в асинхронных программах C#)|Выполняет подробную трассировку потока управления через последовательность выражений ожидания в асинхронной программе.|[Пример использования Async. Поток управления в асинхронных программах](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|
|[Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) (Тонкая настройка асинхронного приложения в C#)|Иллюстрирует добавление следующих функциональных возможностей в асинхронное решение:<br /><br /> - [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) (Отмена асинхронной задачи или списка задач в C#)<br />- [Cancel Async Tasks after a Period of Time (C#)](./cancel-async-tasks-after-a-period-of-time.md) (Отмена асинхронных задач после определенного периода времени в C#)<br />- [Cancel Remaining Async Tasks after One Is Complete (C#)](./cancel-remaining-async-tasks-after-one-is-complete.md) (Отмена оставшихся асинхронных задач после завершения одной из них в C#)<br />- [Start Multiple Async Tasks and Process Them As They Complete (C#)](./start-multiple-async-tasks-and-process-them-as-they-complete.md) (Запуск нескольких асинхронных задач и их обработка по мере завершения в C#)|[Пример использования Async. Настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|
|[Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md) (Обработка повторного входа в асинхронных приложениях C#)|Иллюстрирует обработку случаев, в которых активная асинхронная операция перезапускается при выполнении.||
|[WhenAny. Связывание .NET Framework и среды выполнения Windows в C# и Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|Иллюстрирует, как создать мост между типами задач на платформе .NET Framework и IAsyncOperations в среде выполнения Windows, чтобы можно было использовать <xref:System.Threading.Tasks.Task.WhenAny%2A> с методом среды выполнения Windows.|[Пример использования Async. Связывание .NET и среды выполнения Windows с помощью AsTask и WhenAny](https://code.msdn.microsoft.com/Async-Sample-Bridging-d6a2f739)|
|Отмена Async. Связывание .NET Framework и среды выполнения Windows|Иллюстрирует, как создать мост между типами задач на платформе .NET Framework и IAsyncOperations в среде выполнения Windows, чтобы можно было использовать <xref:System.Threading.CancellationTokenSource> с методом среды выполнения Windows.|[Пример использования Async. Связывание .NET и среды выполнения Windows с помощью AsTask и Cancellation](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|
|[Using Async for File Access (C#)](./using-async-for-file-access.md) (Использование метода async для доступа к файлам в C#)|Иллюстрирует преимущества использования асинхронности и ожидания для доступа к файлам.||
|[Task-based Asynchronous Pattern (TAP)](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))|Описывает новый шаблон для асинхронности в платформе .NET Framework. Шаблон основан на типах <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>.||
|[Видеоролики об async на канале Channel 9](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en)|Предоставляет ссылки на различные видеоролики об асинхронном программировании.||

## <a name="BKMK_CompleteExample"></a> Полный пример

Ниже представлен код файла *MainWindow.xaml.cs* из приложения WPF, которое обсуждается в этой статье. Вы можете скачать [пример использования Async из руководства по использованию ключевых слов Async и Await](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-cs/).

[!code-csharp[async](~/samples/async/async-and-await/cs/MainWindow.xaml.cs)]

## <a name="see-also"></a>См. также

- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
- [Асинхронное программирование](../../../async.md)
- [Общие сведения об асинхронной модели](../../../../standard/async.md)
