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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957548"
---
# <a name="using-statement-visual-basic"></a>Оператор Using (Visual Basic)
Объявляет начало `Using` блока и при необходимости получает системные ресурсы, которые блокируют элементы управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`resourcelist`|Требуется, если не указан `resourceexpression`. Список из одного или нескольких системных ресурсов, которые `Using` управляются этим блоком, разделенные запятыми.|  
|`resourceexpression`|Требуется, если не указан `resourcelist`. Ссылка на переменную или выражение, ссылающееся на системный ресурс, который `Using` должен управляться этим блоком.|  
|`statements`|Необязательный параметр. Блок операторов, `Using` выполняемых блоком.|  
|`End Using`|Обязательный. Завершает определение `Using` блока и уничтожает все ресурсы, которыми он управляет.|  
  
 Каждый ресурс в `resourcelist` части имеет следующий синтаксис и части:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -или-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>ресаурцелист части  
  
|Термин|Определение|  
|---|---|  
|`resourcename`|Обязательный. Ссылочная переменная, которая ссылается на системный ресурс, `Using` который контролируется блоком.|  
|`New`|Требуется, `Using` если инструкция получает ресурс. Если вы уже приобрели ресурс, используйте второй альтернативный синтаксис.|  
|`resourcetype`|Обязательный. Класс ресурса. Класс должен реализовывать <xref:System.IDisposable> интерфейс.|  
|`arglist`|Необязательный параметр. Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype`. См. [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Обязательный. Переменная или выражение, ссылающееся на системный ресурс, удовлетворяющий требованиям `resourcetype`. Если используется второй альтернативный синтаксис, необходимо получить ресурс перед передачей управления `Using` оператору.|  
  
## <a name="remarks"></a>Примечания  
 Иногда коду требуется неуправляемый ресурс, например файловый обработчик, оболочка COM или соединение SQL. `Using` Блок гарантирует удаление одного или нескольких таких ресурсов при завершении кода с ними. Это делает их доступными для использования другим кодом.  
  
 Управляемые ресурсы удаляются сборщиком мусора .NET Framework (GC) без дополнительного написания кода для вашей части. Для управляемых ресурсов `Using` блок не требуется. Однако можно по-прежнему использовать `Using` блок для принудительного удаления управляемого ресурса вместо ожидания сборщика мусора.  
  
 Блок `Using` состоит из трех частей: приобретение, использование и утилизация.  
  
- *Получение* означает создание переменной и ее инициализацию для ссылки на системный ресурс. Инструкция может получить один или несколько ресурсов, либо можно получить ровно один ресурс, прежде чем входить в блок и передать его `Using` в инструкцию. `Using` При указании `resourceexpression`необходимо получить ресурс перед передачей управления `Using` оператору.  
  
- *Использование* означает доступ к ресурсам и выполнение действий с ними. Операторы между `Using` и `End Using` представляют использование ресурсов.  
  
- *Реализация* означает вызов <xref:System.IDisposable.Dispose%2A> метода для объекта в `resourcename`. Это позволяет объекту очищать свои ресурсы. Оператор уничтожает ресурсы `Using` под управлением блока. `End Using`  
  
## <a name="behavior"></a>Поведение  
 Блок ведет себя `Try`подобно... `Using` конструкция, в `Try` которой блок `Finally` использует ресурсы, а блок удаляет их. `Finally` По `Using` этой причине блок гарантирует освобождение ресурсов, независимо от того, как вы выйдете из блока. Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException>.  
  
 Область каждой переменной ресурса, полученной `Using` инструкцией, ограничена `Using` блоком.  
  
 Если в `Using` инструкции указано более одного системного ресурса, то такой результат будет таким же, как если бы вложенные `Using` блоки совпадали друг с другом.  
  
 Если `resourcename` имеет `Nothing`значение, вызов <xref:System.IDisposable.Dispose%2A> не выполняется и исключение не создается.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Структурированная обработка исключений в блоке using  
 Если необходимо выполнить обработку исключения, которое может возникнуть в `Using` блоке, можно добавить полный `Try`... `Finally` его создание. Если необходимо решить, когда `Using` инструкция не сможет получить ресурс, можно проверить, имеет ли `resourcename` это значение `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Структурированная обработка исключений вместо блока using  
 Если требуется более точный контроль за приобретением ресурсов или требуется дополнительный код в `Finally` блоке, можно `Using` переписать блок как `Try`... `Finally` создание. В следующем примере показаны `Try` скелеты `Using` и конструкции, эквивалентные в приобретении и утилизации `resource`.  
  
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
> Код внутри `Using` блока не должен назначать объект в `resourcename` другую переменную. При выходе из `Using` блока ресурс удаляется, а другая переменная не может получить доступ к ресурсу, на который он указывает.  
  
## <a name="example"></a>Пример  
 В следующем примере создается файл с именем log. txt и в него записываются две строки текста. В этом примере также считывается тот же файл и отображаются строки текста.  
  
 Поскольку классы <xref:System.IO.TextReader> <xref:System.IDisposable> и реализуют интерфейс, код может использовать `Using` инструкции, чтобы убедиться, что файл правильно закрыт после операций записи и чтения. <xref:System.IO.TextWriter>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IDisposable>
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Практическое руководство. Удаление системного ресурса](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
