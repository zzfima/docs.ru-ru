---
title: Справочник по C#. Оператор try-catch
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 5289dbe3aff0a9e1f1024a293ff469df44d34a3b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713031"
---
# <a name="try-catch-c-reference"></a>try-catch (Справочник по C#)

Оператор try-catch состоит из блока `try`, за которым следует одно или несколько предложений `catch`, задающих обработчики для различных исключений.

При возникновении исключения общеязыковая среда выполнения (CLR) ищет оператор `catch`, который обрабатывает это исключение. Если текущий выполняемый метод не содержит такой блок `catch`, среда CLR выполняет поиск в методе, который вызвал текущий метод, и так далее вверх по стеку вызовов. Если блок `catch` не находится, то среда CLR отображает пользователю сообщение о необработанном исключении и останавливает выполнение программы.

Блок `try` содержит защищенный код, который может вызвать исключение. Этот блок выполняется, пока не возникнет исключение или пока он не будет успешно завершен. Например, следующая попытка приведения объекта `null` вызывает исключение <xref:System.NullReferenceException>:

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

Хотя предложение `catch` может использоваться без аргументов для перехвата любого типа исключения, такое использование не рекомендуется. В целом вы должны перехватывать только те исключения, после которых вы знаете, как выполнить восстановление. Поэтому всегда следует указывать аргумент объекта, производный от <xref:System.Exception?displayProperty=nameWithType>, например:

```csharp
catch (InvalidCastException e)
{
}
```

В одном блоке try-catch можно использовать несколько определенных предложений `catch`. В этом случае важен порядок предложений `catch`, поскольку предложения `catch` проверяются по порядку. Перехватывайте более конкретные исключения перед менее конкретными. Компилятор выдает ошибку, если вы расположили блоки catch в таком порядке, что последующий блок может быть никогда не достигнут.

Использование аргументов `catch` представляет один из способов фильтрации исключений, которые требуется обработать.  Вы также можете использовать фильтр исключений, который дополнительно проверяет исключение, чтобы решить, следует ли его обрабатывать.  Если фильтр исключений возвращает значение false, поиск обработчика продолжается.

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

Фильтры исключений предпочтительнее перехвата и повторного вызова (объясняется ниже), поскольку фильтры оставляют стек в целости и сохранности.  Если последующий обработчик разгружает стек, вы можете увидеть, откуда изначально произошло исключение, а не только последнее место, в котором оно было повторно вызвано.  Обычно выражения фильтра исключений используются для ведения журнала.  Вы можете создать фильтр, который всегда возвращает значение false, а также записывает выходной результат в журнал, чтобы регистрировать исключения в журнале по мере их поступления без необходимости их обработки и повторного вызова.

Оператор [throw](throw.md), включенный в блок `catch`, позволяет заново вызвать исключение, перехваченное блоком `catch`. В следующем примере извлекаются сведения об источнике из исключения <xref:System.IO.IOException>, а затем это исключение вызывается для родительского метода.

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then 
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

Вы можете перехватывать одно исключение и вызывать другое исключение. При этом следует указать перехватываемое исключение как внутреннее, как показано в следующем примере.

```csharp
catch (InvalidCastException e) 
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

Вы также можете повторно вызывать исключение при выполнении указанного условия, как показано в следующем примере.

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> Вы можете использовать фильтр исключений, чтобы получить тот же результат, но проще (при этом не изменяя стек, как описано ранее в этом документе). В следующем примере показано такое же поведение для вызывающих объектов, как и в предыдущем примере. Эта функция отправляет исключение `InvalidCastException` обратно вызывающему объекту, если `e.Data` имеет значение `null`.
> 
> ```csharp
> catch (InvalidCastException e) when (e.Data != null) 
> {
>     // Take some action.
> }
> ``` 

В блоке `try` инициализируйте только те переменные, которые в нем объявлены. В противном случае до завершения выполнения блока может возникнуть исключение. Например, в следующем примере кода переменная `n` инициализируется внутри блока `try`. Попытка использовать данную переменную вне этого блока `try` в инструкции `Write(n)` приведет к ошибке компилятора.

```csharp
static void Main() 
{
    int n;
    try 
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

Дополнительные сведения о перехвате исключений см. в разделе [try-catch-finally](try-catch-finally.md).

## <a name="exceptions-in-async-methods"></a>Исключения в асинхронных методах

Асинхронный метод помечается модификатором [async](async.md) и обычно содержит одно или несколько выражений или инструкций await. Выражение await применяет оператор [await](../operators/await.md) к <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.

Когда управление достигает `await` в асинхронном методе, выполнение метода приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи выполнение в методе может быть возобновлено. Дополнительные сведения см. в разделах [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md) и [Поток управления в асинхронных программах](../../programming-guide/concepts/async/control-flow-in-async-programs.md).

Завершенная задача, к которой применяется `await`, может находиться в состоянии сбоя из-за необработанного исключения в методе, который возвращает эту задачу. Ожидание задачи вызывает исключение. Задача также может завершиться в отмененном состоянии, если отменяется асинхронный процесс, возвращающий эту задачу. Ожидание отмененной задачи вызывает `OperationCanceledException`. Дополнительные сведения о том, как отменить асинхронный процесс, см. в разделе [Точная настройка асинхронного приложения (C# и Visual Basic)](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).

Для перехвата исключения ожидайте задачу в блоке `try` и перехватывайте это исключение в соответствующем блоке `catch`. См. пример в разделе [Пример асинхронного метода](#async-method-example).

Задача может быть в состоянии сбоя, если в ожидаемом асинхронном методе произошло несколько исключений. Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. При ожидании такой задачи перехватывается только одно из исключений и невозможно предсказать, какое исключение будет перехвачено. См. пример в разделе [Пример Task.WhenAll](#taskwhenall-example).

## <a name="example"></a>Пример

В следующем примере блок `try` содержит вызов метода `ProcessString`, который может вызвать исключение. Предложение `catch` содержит обработчик исключений, который просто отображает сообщение на экране. Когда оператор `throw` вызывается из `MyMethod`, система осуществляет поиск оператора `catch` и отображает сообщение `Exception caught`.

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a>Пример двух блоков catch

В следующем примере используются два блока catch и перехватывается наиболее конкретное исключение, поступившее первым.

Чтобы перехватить наименее конкретное исключение, можно заменить оператор throw в `ProcessString` следующим оператором: `throw new Exception()`.

Если в этом примере первым поместить блок catch для перехвата наименее конкретного исключения, то появится следующее сообщение об ошибке: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a>Пример асинхронного метода

В следующем примере демонстрируется обработка исключений для асинхронных методов. Для перехвата исключения, вызванного асинхронной задачей, поместите выражение `await` в блок `try` и перехватывайте это исключение в блоке `catch`.

Раскомментируйте строку `throw new Exception` в этом примере для демонстрации обработки исключений. Для свойства `IsFaulted` задачи установлено значение `True`, для свойства `Exception.InnerException` задачи установлено это исключение, а исключение перехватывается в блоке `catch`.

Раскомментируйте строку `throw new OperationCanceledException`, чтобы показать, что происходит при отмене асинхронного процесса. Для свойства `IsCanceled` задачи устанавливается значение `true`, и исключение перехватывается в блоке `catch`. В некоторых условиях, которые неприменимы в данном примере, для свойства `IsFaulted` задачи устанавливается значение `true`, а для `IsCanceled` устанавливается значение `false`.

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a>Пример Task.WhenAll

В следующем примере демонстрируется обработка исключений, когда несколько задач могут привести к нескольким исключениям. Блок `try` ожидает задачу, которая возвращается вызовом метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Эта задача завершается после завершения трех задач, к которым применяется WhenAll.

Каждая из трех задач вызывает исключение. Блок `catch` выполняет итерацию по исключениям, которые обнаруживаются в свойстве `Exception.InnerExceptions` задачи, возвращенной методом <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор try](~/_csharplang/spec/statements.md#the-try-statement) в документации [Спецификация C# 6.0](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Операторы try, throw и catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-finally](try-finally.md)
- [Практическое руководство. Явное создание исключений](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
