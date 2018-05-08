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
ms.openlocfilehash: 725eeb42dc5462022ac1a021c537d701929398ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-statement-visual-basic"></a>Оператор Using (Visual Basic)
Объявляет начало `Using` блокировку и при необходимости получает системные ресурсы, которыми управляет блок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`resourcelist`|Требуется, если не указать `resourceexpression`. Список из одного или нескольких системных ресурсов, это `Using` блокировать элементы управления, разделенных запятыми.|  
|`resourceexpression`|Требуется, если не указать `resourcelist`. Ссылочная переменная или выражение, которое ссылается на системный ресурс, чтобы управлять этим `Using` блока.|  
|`statements`|Необязательный. Блок инструкций, `Using` блок.|  
|`End Using`|Обязательно. Завершает определение `Using` блоков и освобождает все ресурсы, которыми он управляет.|  
  
 Каждый ресурс в `resourcelist` часть имеет следующий синтаксис и компоненты:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 - или -  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist частей  
  
|Термин|Определение|  
|---|---|  
|`resourcename`|Обязательно. Ссылочная переменная, которая ссылается на системный ресурс, `Using` блокировать элементы управления.|  
|`New`|Обязателен, если `Using` инструкция получает ресурса. Если ресурс уже получен, используйте альтернативный синтаксис.|  
|`resourcetype`|Обязательно. Класс ресурса. Класс должен реализовывать <xref:System.IDisposable> интерфейса.|  
|`arglist`|Необязательный. Список аргументов, которые передаются в конструктор для создания экземпляра `resourcetype`. В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Обязательно. Переменная или выражение, которое ссылается на системный ресурс, отвечающий требованиям `resourcetype`. Если используется альтернативный синтаксис, необходимо получить ресурс перед передачей управления `Using` инструкции.|  
  
## <a name="remarks"></a>Примечания  
 Иногда код требует неуправляемых ресурсов, такие как дескриптор файла, оболочка COM или SQL-соединение. Объект `Using` блок гарантирует удаление одного или нескольких таких ресурсов после завершения вашего кода с ними. Это делает их доступными для использования другим кодом.  
  
 Управляемые ресурсы удаляются с .NET Framework сборщик мусора (GC) без дополнительного кодирования со стороны пользователя. Нет необходимости `Using` блок для управляемых ресурсов. Тем не менее, можно по-прежнему использовать `Using` блок для принудительного освобождения управляемых ресурсов, а не ждет, пока сборщик мусора.  
  
 Объект `Using` блок состоит из трех частей: приобретение, использование и удаление.  
  
-   *Приобретение* означает создание переменной и инициализация ее для ссылки на ресурс системы. `Using` Оператор может получить один или несколько ресурсов, или можно получить ровно один ресурс перед вводом блока и указать его `Using` инструкции. При указании `resourceexpression`, необходимо получить ресурс перед передачей управления `Using` инструкции.  
  
-   *Использование* означает доступ к ресурсам и выполнение действий с ними. Инструкции между `Using` и `End Using` представляют собой использование ресурсов.  
  
-   *Реализация* означает вызов <xref:System.IDisposable.Dispose%2A> объекта в метод `resourcename`. Это позволяет объекту удалить его ресурсы. `End Using` Инструкции освобождает все ресурсы в группе `Using` блока управления.  
  
## <a name="behavior"></a>Поведение  
 Объект `Using` блок ведет себя как `Try`... `Finally` построения, в котором `Try` блок использует ресурсы и `Finally` блок удаляет их. По этой причине `Using` блок гарантирует освобождение ресурсов, независимо от того, как выйти из блока. Это верно даже при наличии необработанного исключения, за исключением <xref:System.StackOverflowException>.  
  
 Области каждой переменной ресурсов, полученных `Using` инструкции ограничено `Using` блока.  
  
 Если указать более одного системного ресурса в `Using` инструкции эффект совпадает, если вложенные `Using` блокирует один в другой.  
  
 Если `resourcename` — `Nothing`, не вызов <xref:System.IDisposable.Dispose%2A> производится, и исключение не возникает.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>В блоке Using обработке структурированных исключений  
 Если необходимо обрабатывать исключения, которые могут возникнуть в `Using` блока, можно добавить полный `Try`... `Finally` конструкции, к нему. Если требуется обрабатывать случаи, где `Using` инструкции не удалось получить ресурсы, можно проверить на предмет `resourcename` — `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Структурированная обработка исключений без блока с помощью  
 Если требуется более точный контроль приобретение ресурсов, или требуется дополнительный код в `Finally` блока, можно переписать `Using` блокировки на `Try`... `Finally` построения. В следующем примере показано основу `Try` и `Using` конструкций, которые эквивалентны в приобретении и реализации `resource`.  
  
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
>  Код внутри `Using` блок не следует присваивать объект в `resourcename` другой переменной. После выхода из `Using` блока, ресурс удаляется, а другая переменная нет доступа к ресурсу, на который он указывает.  
  
## <a name="example"></a>Пример  
 В следующем примере создается файл с именем log.txt и записывает две строки текста в файл. В примере также считывает этот же файл и отображаются строки текста.  
  
 Поскольку <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> классы реализуют <xref:System.IDisposable> интерфейс, в коде можно использовать `Using` инструкции, чтобы убедиться, что файл правильно закрыты после записи и операций чтения.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IDisposable>  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Практическое руководство. Удаление системного ресурса](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
