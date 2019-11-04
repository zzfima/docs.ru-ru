---
title: Обработка ошибок ввода-вывода в .NET
ms.date: 08/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, exception handling
- I/O, errors
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 51eb0e758f1ae8fb41c842ef9b32a9f8928af9ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120746"
---
# <a name="handling-io-errors-in-net"></a>Обработка ошибок ввода-вывода в .NET

Помимо тех исключений, которые могут быть созданы в любом вызове метода (например, <xref:System.OutOfMemoryException> при высокой нагрузке на систему или <xref:System.NullReferenceException> при ошибке в программе), методы файловой системы .NET могут создавать следующие исключения:

- <xref:System.IO.IOException?displayProperty=nameWithType> — служит базовым классом для всех типов исключений <xref:System.IO>. Это исключение создается для ошибок, у которых код возврата из операционной системы не сопоставляется напрямую с другим типом исключения.
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DriveNotFoundException??displayProperty=nameWithType>.
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType>.
- <xref:System.OperationCanceledException?displayProperty=nameWithType>.
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType>.
- <xref:System.ArgumentException?displayProperty=nameWithType> — создается для недопустимых символов пути на платформе .NET Framework, а также .NET Core 2.0 и предыдущих версиях.
- <xref:System.NotSupportedException?displayProperty=nameWithType> — создается для недопустимых двоеточий в .NET Framework.
- <xref:System.Security.SecurityException?displayProperty=nameWithType> — создается для приложений в частичном доверии, которые не имеют необходимых разрешений (только на платформе .NET Framework). На платформе .NET Framework по умолчанию используется полное доверие.

## <a name="mapping-error-codes-to-exceptions"></a>Сопоставление кодов ошибок с исключениями

Так как файловая система представляет собой ресурс операционной системы, методы ввода-вывода в .NET Core и .NET Framework служат оболочками для соответствующих вызовов операционной системы. Если в коде, выполняемом операционной системой, возникает ошибка ввода-вывода, операционная система возвращает сведения об ошибке в метод ввода-вывода .NET. Затем этот метод преобразует сведения об ошибке, обычно представленные кодом ошибки, в соответствующий тип исключения .NET. В большинстве случаев код ошибки напрямую определяет нужный тип исключения. Метод не выполняет никакой дополнительной обработки в соответствии с контекстом вызова метода.

Например, при вызове метода в операционной системе Windows код ошибки `ERROR_FILE_NOT_FOUND` (или 0x02) преобразуется в исключение <xref:System.IO.FileNotFoundException>, а код ошибки `ERROR_PATH_NOT_FOUND` (или 0x03) — в <xref:System.IO.DirectoryNotFoundException>.

К сожалению, точные условия возникновения определенных кодов ошибок в операционной системе часто не документируются или документируются в недостаточном объеме. Это означает, что возможны непредвиденные исключения. Например, при работе с каталогом логично ожидать, что передача недопустимого пути в конструктор <xref:System.IO.DirectoryInfo.%23ctor%2A?displayProperty=nameWithType> приведет к созданию исключения <xref:System.IO.DirectoryNotFoundException>. Но в этой ситуации может создаваться и <xref:System.IO.FileNotFoundException>.

## <a name="exception-handling-in-io-operations"></a>Обработка исключений при операциях ввода-вывода

По причине зависимости от операционной системы иногда идентичные условия (например, отсутствие указанного каталога) могут создавать в методах ввода-вывода любое исключение из класса ввода-вывода. Это означает, что при вызове интерфейсов API ввода-вывода ваш код должн быть готов обработать все такие исключения или большую их часть, как показано в следующей таблице:

| Тип исключения | .NET Core | .NET Framework |
|---|---|---|
| <xref:System.IO.IOException> | Да | Да |
| <xref:System.IO.FileNotFoundException> | Да | Да |
| <xref:System.IO.DirectoryNotFoundException> | Да | Да |
| <xref:System.IO.DriveNotFoundException?> | Да | Да |
| <xref:System.IO.PathTooLongException> | Да | Да |
| <xref:System.OperationCanceledException> | Да | Да |
| <xref:System.UnauthorizedAccessException> | Да | Да |
| <xref:System.ArgumentException> | .NET Core 2.0 или более ранняя версия| Да |
| <xref:System.NotSupportedException> | Нет | Да |
| <xref:System.Security.SecurityException> | Нет | Только для ограниченного доверия |

## <a name="handling-ioexception"></a>Обработка IOException

<xref:System.IO.IOException> является базовым классом для исключений в пространстве имен <xref:System.IO> и создается для любого кода ошибки, который не имеет сопоставления с определенным типом исключения. Это означает, что оно может появиться в любой операции ввода-вывода.

> [!IMPORTANT]
> Так как <xref:System.IO.IOException> является базовым классом для других типов исключений в пространстве имен <xref:System.IO>, его нужно обрабатывать в блоке `catch` после обработки других исключений, связанных с вводом-выводом.

Кроме того, в версии .NET Core 2.1 не применяется проверка правильности пути (например, отсутствия недопустимых символов в пути), и теперь среда выполнения создает исключение, сопоставленное с кодом ошибки операционной системы, а не результат проверки в собственном коде. В такой ситуации чаще всего создается исключение <xref:System.IO.IOException>, но вы можете столкнуться с любым другим типом исключений.

Обратите внимание, что в коде обработки исключений <xref:System.IO.IOException> всегда нужно обрабатывать последним. Иначе блоки catch для производных классов не проверяются, ведь это исключение является базовым классом для всех остальных.

В случае с <xref:System.IO.IOException> дополнительные сведения об ошибке можно получить из свойства [IOException.HResult](xref:System.Exception.HResult). Чтобы преобразовать значение HResult в код ошибки Win32, отбросьте верхние 16 бит из 32-разрядного значения. В приведенной ниже таблице перечислены коды ошибок, которые могут быть заключены в <xref:System.IO.IOException>.

| HResult | Константа | Описание |
| --- | --- | --- |
| ERROR_SHARING_VIOLATION | 32 | Отсутствует имя файла, или файл или каталог уже используется. |
| ERROR_FILE_EXISTS | 80 | Файл уже существует. |
| ERROR_INVALID_PARAMETER | 87 | Методу передан недопустимый аргумент. |
| ERROR_ALREADY_EXISTS | 183 | Файл или каталог уже существует. |

Для обработки этих исключений можно применить предложение `When` в инструкции catch, как показано в приведенном ниже примере.

[!code-csharp[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/cs/io-exceptions.cs)]
[!code-vb[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/vb/io-exceptions.vb)]

## <a name="see-also"></a>См. также

- [Обработка и создание исключений в .NET](../exceptions/index.md)
- [Обработка исключений (библиотека параллельных задач)](../parallel-programming/exception-handling-task-parallel-library.md)
- [Лучшие методики обработки исключений](../exceptions/best-practices-for-exceptions.md)
- [Практическое руководство. Использование определенных исключений в блоке catch](../exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)
