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
ms.openlocfilehash: fe53ea58dc98a4de793fe9dad1c3ceeac71622fc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843205"
---
# <a name="using-statement-visual-basic"></a>Оператор Using (Visual Basic)
Объявляет начало `Using` блокировать и при необходимости получает системные ресурсы, которыми управляет блок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`resourcelist`|Требуется, если не ввести расширение `resourceexpression`. Список один или несколько системных ресурсов, что этот `Using` блокировать элементы управления, разделенных запятыми.|  
|`resourceexpression`|Требуется, если не ввести расширение `resourcelist`. Ссылочную переменную или выражение, которое ссылается на системный ресурс, контролируемый это `Using` блока.|  
|`statements`|Необязательный параметр. Блок операторов, `Using` блоке.|  
|`End Using`|Обязательный. Завершает определение `Using` блоков и освобождает все ресурсы, которыми он управляет.|  
  
 Каждый ресурс в `resourcelist` часть имеет следующие синтаксис и составляющие:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 - или -  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist частей  
  
|Термин|Определение|  
|---|---|  
|`resourcename`|Обязательный. Ссылочную переменную, которая ссылается на системный ресурс, `Using` блокировать элементы управления.|  
|`New`|Обязателен, если `Using` инструкция получает ресурс. Если ресурс уже получен, используйте альтернативный синтаксис.|  
|`resourcetype`|Обязательный. Класс ресурса. Класс должен реализовывать <xref:System.IDisposable> интерфейс.|  
|`arglist`|Необязательный параметр. Список аргументов, передаваемые в конструктор для создания экземпляра `resourcetype`. См. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Обязательный. Переменная или выражение, которое ссылается на системный ресурс, отвечающий требованиям `resourcetype`. Если используется альтернативный синтаксис, необходимо получить ресурс до передачи управления `Using` инструкции.|  
  
## <a name="remarks"></a>Примечания  
 Иногда код требует неуправляемый ресурс, такие как дескриптор файла, оболочка COM или SQL-соединение. Объект `Using` блок гарантирует удаление одного или нескольких таких ресурсов после завершения вашего кода с ними. Это делает их доступными для использования другим кодом.  
  
 Управляемые ресурсы удаляются сборщиком мусора .NET Framework (GC) без дополнительного кодирования со стороны пользователя. Нет необходимости `Using` блок для управляемых ресурсов. Тем не менее, можно по-прежнему использовать `Using` блок для принудительного удаления управляемых ресурсов, а не ждать, пока сборщик мусора.  
  
 Объект `Using` блок состоит из трех частей: приобретения, использование и удаление.  
  
-   *Приобретение* означает создание переменной и инициализировать его, чтобы ссылаться на системный ресурс. `Using` Оператор может получить один или несколько ресурсов, или можно получить ровно один ресурс перед вводом блока и указать его, чтобы `Using` инструкции. Если вы указали `resourceexpression`, необходимо получить ресурс до передачи управления `Using` инструкции.  
  
-   *Использование* означает, что доступ к ресурсам и выполнение действий с ними. Операторы между `Using` и `End Using` представляют собой использование ресурсов.  
  
-   *Реализация* означает, что вызов <xref:System.IDisposable.Dispose%2A> объекта в метод `resourcename`. Это позволяет объекту, удалить его ресурсы. `End Using` Инструкция удаляет ресурсы в группе `Using` блока управления.  
  
## <a name="behavior"></a>Поведение  
 Объект `Using` блок ведет себя как `Try`... `Finally` построения, в котором `Try` блок использует ресурсы и `Finally` блок удаляет их. По этой причине `Using` блок гарантирует освобождение ресурсов, независимо от того, как выйти из блока. Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException>.  
  
 Области каждой переменной ресурсов, полученных `Using` инструкции ограничено `Using` блока.  
  
 Если указать более одного системного ресурса в `Using` инструкции, эффект одинаков как, если вложенные `Using` блокирует один в другой.  
  
 Если `resourcename` — `Nothing`, вызов <xref:System.IDisposable.Dispose%2A> производится, и исключение не создается.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Обработка в пределах блока с помощью структурированных исключений  
 Если необходимо обрабатывать исключения, которые могут возникнуть в `Using` блок, вы можете добавить полный `Try`... `Finally` конструкции, к нему. Если вам нужно обрабатывать случаи, где `Using` инструкция не может успешно получить ресурсы, можно проверить на предмет `resourcename` является `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Структурированная обработка исключений без блока с помощью  
 Если вам требуется более точный контроль приобретение ресурсов, или требуется дополнительный код в `Finally` блока, можно переписать `Using` заблокировать, в виде `Try`... `Finally` конструкции. В следующем примере показан скелет `Try` и `Using` конструкции, которые эквивалентны в приобретении и реализации `resource`.  
  
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
>  Код внутри `Using` блок не следует присваивать объекта в `resourcename` другой переменной. После выхода из `Using` блока, ресурс освобождается, и еще одной переменной не может доступ к ресурсу, на который он указывает.  
  
## <a name="example"></a>Пример  
 В следующем примере создается файл с именем log.txt и записывает две строки текста в файл. В примере также считывает этот же файл и отображаются строки текста.  
  
 Так как <xref:System.IO.TextWriter> и <xref:System.IO.TextReader> классы реализуют <xref:System.IDisposable> интерфейс, можно использовать код `Using` инструкции, чтобы убедиться, что файл неправильно закрыта после завершения записи и операций чтения.  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IDisposable>
- [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Практическое руководство. Удаление ресурса системы](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
