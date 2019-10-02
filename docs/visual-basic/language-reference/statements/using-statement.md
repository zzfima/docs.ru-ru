---
title: Оператор Using (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 819af63acb6a1f038300bcb999dcfb904eb8a457
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592090"
---
# <a name="using-statement-visual-basic"></a>Оператор Using (Visual Basic)

Объявляет начало блока `Using` и при необходимости получает системные ресурсы, управляющие блоком.

## <a name="syntax"></a>Синтаксис

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Части

|Термин|Определение|  
|---|---|  
|`resourcelist`|Требуется, если не указан `resourceexpression`. Список из одного или нескольких системных ресурсов, которые блокируют элементы управления `Using`, разделенные запятыми.|  
|`resourceexpression`|Требуется, если не указан `resourcelist`. Ссылка на переменную или выражение, ссылающееся на системный ресурс, управляемый этим блоком `Using`.|  
|`statements`|Необязательный параметр. Блок инструкций, выполняемых блоком `Using`.|  
|`End Using`|Обязательный. Завершает определение блока `Using` и уничтожает все ресурсы, которыми он управляет.|  

 Каждый ресурс в части `resourcelist` имеет следующий синтаксис и части:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 \- или -

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>ресаурцелист части

|Термин|Определение|  
|---|---|  
|`resourcename`|Обязательный. Ссылочная переменная, которая ссылается на системный ресурс, который управляется блоком `Using`.|  
|`New`|Требуется, если инструкция `Using` получает ресурс. Если вы уже приобрели ресурс, используйте второй альтернативный синтаксис.|  
|`resourcetype`|Обязательный. Класс ресурса. Класс должен реализовывать интерфейс <xref:System.IDisposable>.|  
|`arglist`|Необязательный параметр. Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype`. См. [список параметров](parameter-list.md).|  
|`resourceexpression`|Обязательный. Переменная или выражение, ссылающиеся на системный ресурс, удовлетворяющий требованиям `resourcetype`. Если используется второй альтернативный синтаксис, необходимо получить ресурс перед передачей управления в оператор `Using`.|  
  
## <a name="remarks"></a>Примечания

 Иногда коду требуется неуправляемый ресурс, например файловый обработчик, оболочка COM или соединение SQL. Блок `Using` гарантирует удаление одного или нескольких таких ресурсов при завершении кода с ними. Это делает их доступными для использования другим кодом.

 Управляемые ресурсы удаляются сборщиком мусора .NET Framework (GC) без дополнительного написания кода для вашей части. Для управляемых ресурсов не требуется блок `Using`. Однако можно по-прежнему использовать блок `Using` для принудительного удаления управляемого ресурса вместо ожидания сборщика мусора.

 Блок `Using` состоит из трех частей: приобретение, использование и утилизация.

- *Получение* означает создание переменной и ее инициализацию для ссылки на системный ресурс. Инструкция `Using` может получить один или несколько ресурсов или получить ровно один ресурс перед входом в блок и предоставить его оператору `Using`. При указании `resourceexpression` необходимо получить ресурс перед передачей управления в оператор `Using`.

- *Использование* означает доступ к ресурсам и выполнение действий с ними. Инструкции между `Using` и `End Using` представляют использование ресурсов.

- *Реализация* означает вызов метода <xref:System.IDisposable.Dispose%2A> для объекта в `resourcename`. Это позволяет объекту очищать свои ресурсы. Оператор `End Using` уничтожает ресурсы в элементе управления блока `Using`.

## <a name="behavior"></a>Поведение

 Блок `Using` ведет себя как конструкция `Try`... `Finally`, в которой блок `Try` использует ресурсы, а блок `Finally` удаляет их. По этой причине блок `Using` гарантирует освобождение ресурсов, независимо от того, как вы выйдете из блока. Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException>.

 Область каждой переменной ресурса, полученной с помощью оператора `Using`, ограничена блоком `Using`.

 Если в инструкции `Using` указано более одного системного ресурса, результат будет таким же, как если бы вложенный `Using` блокировал один из них.

 Если `resourcename` равно `Nothing`, вызов <xref:System.IDisposable.Dispose%2A> не выполняется и исключение не создается.

## <a name="structured-exception-handling-within-a-using-block"></a>Структурированная обработка исключений в блоке using

 Если необходимо выполнить обработку исключения, которое может возникнуть в блоке `Using`, можно добавить в него полную конструкцию `Try`... `Finally`. Если необходимо выполнить обработку ситуации, когда инструкция `Using` не удается получить ресурс, можно проверить, является ли `resourcename` `Nothing`.

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Структурированная обработка исключений вместо блока using

 Если требуется более точный контроль за приобретением ресурсов или требуется дополнительный код в блоке `Finally`, можно переписать блок `Using` как конструкцию `Try`... `Finally`. В следующем примере показана схема конструкций `Try` и `Using`, которые эквивалентны при приобретении и утилизации `resource`.

```vb
Using resource As New resourceType
    ' Insert code to work with resource.
End Using

' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.
Dim resource As New resourceType
Try
    ' Insert code to work with resource.
Finally
    If resource IsNot Nothing Then
        resource.Dispose()
    End If
End Try
```

> [!NOTE]
> Код в блоке `Using` не должен назначать объект в `resourcename` в другую переменную. При выходе из блока `Using` ресурс удаляется, а другая переменная не может получить доступ к ресурсу, на который он указывает.

## <a name="example"></a>Пример

 В следующем примере создается файл с именем log. txt и в него записываются две строки текста. В примере также считывается тот же файл и отображаются строки текста:

 Поскольку классы <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> реализуют интерфейс <xref:System.IDisposable>, код может использовать операторы `Using`, чтобы гарантировать корректное закрытие файла после операций записи и чтения.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>См. также

- <xref:System.IDisposable>
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
- [Практическое руководство. Удаление системного ресурса @ no__t-0
