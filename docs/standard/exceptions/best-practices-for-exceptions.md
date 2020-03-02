---
title: Лучшие методики обработки исключений — .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 1de231b01e3fa97e78a87ae6b0595a9b5536374e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160174"
---
# <a name="best-practices-for-exceptions"></a>Лучшие методики обработки исключений

Хорошо спроектированное приложение обрабатывает исключения и ошибки, чтобы предотвратить сбои приложения. В этом разделе описываются рекомендации по обработке и созданию исключений.

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a>Использование блоков try/catch/finally для восстановления после ошибок или высвобождения ресурсов

Используйте блоки `try`/`catch`, выделив с их помощью код, который потенциально может явиться источником исключения, ***таким образом*** можно будет выполнить восстановление кода после возникновения этого исключения. В блоках `catch` следует всегда упорядочивать исключения от более производных к менее производным. Все исключения, производные от <xref:System.Exception>. Более производные исключения не обрабатываются предложением catch, которому предшествует предложение catch для базового класса исключения. Если ваш код не удается восстановить после возникновения исключения, не перехватывайте это исключение. Включите методы выше по стеку вызовов для восстановления по мере возможности.

Очистите ресурсы, выделенные с помощью инструкций `using` или блоков `finally`. Рекомендуется использовать инструкции `using` для автоматической очистки ресурсов при возникновении исключений. Используйте блоки `finally`, чтобы очистить ресурсы, которые не реализуют <xref:System.IDisposable>. Код в предложении `finally` выполняется почти всегда — даже при возникновении исключений.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Обработка общих условий без выдачи исключений

Для условий, которые могут возникнуть, но способны вызвать исключение, рекомендуется реализовать обработку таким способом, который позволит избежать исключения. Например, при попытке закрыть уже закрытое подключение возникает `InvalidOperationException`. Этого можно избежать, используя оператор `if` для проверки состояния подключения перед попыткой закрыть его.

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

Если состояние подключения перед закрытием не проверяется, исключение `InvalidOperationException` можно перехватить.

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

Выбор конкретного способа зависит от того, насколько часто ожидается возникновение данного события.

- Используйте обработку исключений, если событие не происходит очень часто, то есть если событие носит действительно исключительный характер и указывает на ошибку (например, в случае неожиданного конца файла). При использовании обработки исключений в обычных условиях выполняется меньше кода.

- Если событие происходит регулярно в рамках нормальной работы программы, выполняйте проверку на наличие ошибок прямо в коде. Проверка на наличие распространенных условий ошибки позволяет выполнять меньший объем кода благодаря устранению исключений.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Устранение исключений при разработке классов

Класс может предоставлять методы и свойства, позволяющие избежать вызова, способного выдать исключение. Например, класс <xref:System.IO.FileStream> содержит методы, позволяющие определить, достигнут ли конец файла. Это позволяет избежать появления исключения, создаваемого в случае выполнения чтения после окончания файла. В следующем примере показан способ чтения до конца файла без выдачи исключения.

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

Другой способ устранения исключений заключается в том, что для наиболее общих и часто встречающихся ошибок следует возвращать значение NULL (или значение по умолчанию). Такие ошибки могут относиться к обычному потоку управления. Возвращая значение NULL (или значение по умолчанию) в таких случаях, можно уменьшить влияние на производительность приложения.

При выборе типа значения `Nullable<T>` или значения по умолчанию в качестве индикатора ошибки учитывайте особенности приложения. При использовании `Nullable<Guid>``default` принимает значение `null`, а не `Guid.Empty`. В некоторых случаях добавление `Nullable<T>` помогает более точно определить, присутствует или отсутствует значение. Но в определенных ситуациях добавление `Nullable<T>` может привести к созданию лишних необязательных случаев для проверки, что повышает вероятность ошибки.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Выдача исключений вместо возврата кода ошибки

Исключения гарантируют, что сбои не останутся незамеченными из-за того, что вызывающий код не проверил код возврата.

## <a name="use-the-predefined-net-exception-types"></a>Использование предопределенных типов исключений .NET

Создавайте новый класс исключений, только если предопределенное исключение не подходит. Пример:

- Вызывайте исключение <xref:System.InvalidOperationException>, если значение свойства или вызов метода не соответствуют текущему состоянию объекта.

- Порождайте исключение <xref:System.ArgumentException> или одного из предварительно определенных классов, которые являются производными от <xref:System.ArgumentException>, если передаются недопустимые параметры.

## <a name="end-exception-class-names-with-the-word-exception"></a>Завершайте имена классов исключений словом `Exception`

Если требуется пользовательское исключение, присвойте ему соответствующее имя и сделайте его производным от класса <xref:System.Exception>. Пример:

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a>Включение трех конструкторов в пользовательские классы исключений

При создании собственных классов исключений можно использовать по меньшей мере три общих конструктора: конструктор без параметров, конструктор, принимающий строковое сообщение, и конструктор, принимающий строковое сообщение и внутреннее исключение.

- <xref:System.Exception.%23ctor>, использующий значения по умолчанию.

- <xref:System.Exception.%23ctor%28System.String%29>, принимающий строковое сообщение.

- <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, принимающий строковое сообщение и внутреннее исключение.

Пример см. в статье [Практическое руководство. Создание пользовательских исключений](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Обеспечение доступности данных об исключении при удаленном выполнении кода

При создании пользовательских исключений следует обеспечить доступность метаданных исключений для удаленно исполняемого кода.

Например, для реализаций .NET, которые поддерживают домены приложений, могут возникать исключения для этих доменов. Предположим, что домен приложения А создает домен приложения В, который выполняет код, вызывающий исключение. Чтобы домен приложения A правильно перехватил и обработал исключение, он должен найти сборку, которая содержит исключение, порожденное доменом приложения B. Если домен приложения B порождает исключение, содержащееся в сборке в его базовой папке приложения, но не в базовой папке приложения домена A, то домен приложения A не сможет найти исключение и среда CLR породит исключение <xref:System.IO.FileNotFoundException>. Чтобы избежать такой ситуации, можно развернуть сборку, содержащую сведения об исключении, двумя способами:

- Поместите эту сборку в общую базу приложения, совместно используемую обоими доменами приложений.

    \- или -

- Если у этих доменов нет общей базы приложения, то подпишите сборку, содержащую сведения об исключении, строгим именем и разверните ее в глобальном кэше сборок.

## <a name="use-grammatically-correct-error-messages"></a>Использование грамматически правильных сообщений об ошибке

Составляйте понятные предложения, указывая в конце знаки препинания. Каждое предложение в строке, назначенной свойству <xref:System.Exception.Message?displayProperty=nameWithType>, должно заканчиваться точкой. Например, "Таблица журнала переполнена." будет подходящей строкой сообщения.

## <a name="include-a-localized-string-message-in-every-exception"></a>Включение локализованной строки сообщения в каждое исключение

Сообщение об ошибке, показываемое пользователю, извлекается из свойства <xref:System.Exception.Message?displayProperty=nameWithType> созданного исключения, а не из имени класса исключения. Как правило, вы присваиваете значение свойству <xref:System.Exception.Message?displayProperty=nameWithType>, передав строку сообщения аргументу `message`[конструктора исключений](xref:System.Exception.%23ctor%2A).

Для локализованных приложений необходимо предоставить строку локализованного сообщения для всех исключений, которые может создавать приложение. Используйте файлы ресурсов для предоставления локализованных сообщений об ошибках. Сведения о локализации приложений и извлечении локализованных строк см. в следующих статьях:

- [Пошаговое руководство. Создание пользовательских исключений с локализованными сообщениями об исключениях](how-to-create-localized-exception-messages.md)
- [Ресурсы в приложениях для настольных систем](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Предоставление дополнительных свойств в пользовательских исключениях по мере необходимости

Дополнительные сведения (кроме строки настраиваемого сообщения) включайте в исключение только в случаях, когда в соответствии со сценарием программирования такие дополнительные сведения могут оказаться полезными. Например, исключение <xref:System.IO.FileNotFoundException> предоставляет свойство <xref:System.IO.FileNotFoundException.FileName>.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Размещение операторов throw для удобной трассировки стека

Трассировка стека начинается в операторе, породившем исключение, и завершается оператором `catch`, перехватывающим это исключение.

## <a name="use-exception-builder-methods"></a>Использование методов построителя исключений

Обычно класс генерирует одно и то же исключение из различных мест своей реализации. Чтобы избежать повторения кода, используйте вспомогательные методы, создающие исключение и затем возвращающие его. Пример:

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

В некоторых случаях для создания исключения лучше воспользоваться конструктором исключений. В качестве примера можно привести класс глобальных исключений, например <xref:System.ArgumentException>.

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a>Восстановление состояния, если методы не выполняются из-за исключения

Вызывающие объекты должны предполагать, что при создании исключения из метода не возникают побочные эффекты. Например, если у вас есть код, который передает деньги, списывая их с одного счета и внося на другой, и при начислении средств возникает исключение, списание средств применяться не должно.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

Описанный выше метод непосредственно не создает исключения, однако при его написании необходимо соблюдать осторожность, чтобы при сбое операции начисления списание отменялось.

Один из способов обработки в этой ситуации заключается в перехвате всех исключений, выданных транзакцией начисления средств, и откате транзакции списания средств.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

В этом примере показано использование `throw` для повторного порождения исходного исключения. Это позволяет вызывающим объектам проще установить фактическую причину проблемы, не обращаясь к свойству <xref:System.Exception.InnerException>. Альтернативным способом является выдача нового исключения с включением исходного исключения в качестве внутреннего:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a>См. также раздел

- [Исключения](index.md)
