---
title: "Конструкция TRY... CATCH... Оператор finally (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
dev_langs:
- VB
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement, Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement
- When keyword
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
caps.latest.revision: 69
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 379359e3a338746ccd440dbe1ad58c483e562dbe
ms.lasthandoff: 03/13/2017

---
# <a name="trycatchfinally-statement-visual-basic"></a>Оператор Try... Catch... Finally (Visual Basic)
Позволяет обрабатывать некоторые или все возможные ошибки, которые могут возникать в конкретном блоке кода, не прерывая выполнение кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Try  
    [ tryStatements ]  
    [ Exit Try ]  
[ Catch [ exception [ As type ] ] [ When expression ]  
    [ catchStatements ]  
    [ Exit Try ] ]  
[ Catch ... ]  
[ Finally  
    [ finallyStatements ] ]  
End Try  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`tryStatements`|Необязательный. Операторы, в которых может возникнуть ошибка. Может быть составным оператором.|  
|`Catch`|Необязательный. Несколько `Catch` блоки разрешены. Если возникает исключение при обработке `Try` блока, каждый `Catch` инструкция является проверяются в порядке следования, чтобы определить, является ли он обрабатывает исключение, с `exception` представляет исключение, которое было создано.|  
|`exception`|Необязательный. Любое имя переменной. Начальное значение `exception` — это значение возникшей ошибки. Используется с `Catch` ошибок перехвачено. Если аргумент опущен, `Catch` инструкции перехватывает все исключения.|  
|`type`|Необязательный. Указывает тип класса фильтра. Если значение `exception` имеет тип, заданный параметром `type` или производного типа, данный идентификатор становится привязкой к объекту исключения.|  
|`When`|Необязательный. Объект `Catch` инструкции с `When` перехватывают исключения только если `expression` равен `True`. Объект `When` предложение применяется только после проверки типа исключения, и `expression` может ссылаться на идентификатор, представляющий исключение.|  
|`expression`|Необязательный. Должен быть неявно преобразуемым в `Boolean`. Любое выражение, которое описывает универсальный фильтр. Обычно используется для фильтрации по номеру ошибки. Используется с `When` ключевое слово для определения условий, при которых будет перехватываться данная ошибка.|  
|`catchStatements`|Необязательный. Операторы обработки ошибок, возникающих в соответствующем `Try` блок. Может быть составным оператором.|  
|`Exit Try`|Необязательный. Ключевое слово, которое разбивает из `Try...Catch...Finally` структуры. Выполнение возобновляется с кода, непосредственно следующего `End Try` инструкции. `Finally` Инструкция будет выполняться. Не допускается в `Finally` блоков.|  
|`Finally`|Необязательный. Объект `Finally` блоке выполняется всегда, когда выполнение перемещается из любой части `Try...Catch` инструкции.|  
|`finallyStatements`|Необязательный. Операторы, выполняемые после всех других действий по обработке ошибки.|  
|`End Try`|Завершает `Try...Catch...Finally` структуры.|  
  
## <a name="remarks"></a>Примечания  
 Если предполагается, что конкретное исключение может произойти во время определенного раздела кода, необходимо поместить код `Try` блок и использовать `Catch` блок для сохранения управления и обработки исключения при его возникновении.  
  
 Объект `Try…Catch` оператор состоит из `Try` блока, а затем по одному или нескольким `Catch` предложений, которые задают обработчики для различных исключений. Когда исключение `Try` блока, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ищет `Catch` оператор, который обрабатывает исключение. Если соответствующий `Catch` оператор не найден, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проверяет метод, который вызвал текущий метод вверх по стеку вызовов и т. д. Если не `Catch` обнаружен блок [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] отображает пользователю сообщение о необработанном исключении и останавливает выполнение программы.  
  
 Можно использовать несколько `Catch` инструкции в `Try…Catch` инструкции. После этого, порядок `Catch` предложений важен, поскольку они проверяются в порядке. Перехватывайте более конкретные исключения перед менее конкретными.  
  
 Следующие `Catch` бы специальные инструкции условия и будет перехватывать все исключения, производные от <xref:System.Exception>класса.</xref:System.Exception> Обычно следует использовать один из этих вариантов на последнем `Catch` блока в `Try...Catch...Finally` структуры после перехвата всех определенных исключений, предполагается, что. Поток управления никогда не может достичь `Catch` блок, который соответствует любой из этих вариантов.  
  
-   `type` — `Exception`, Например:`Catch ex As Exception`  
  
-   Оператор не имеет `exception` переменной, например:`Catch`  
  
 При `Try…Catch…Finally` инструкции, вложенным в другой `Try` блока, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] сначала проверяет каждый `Catch` инструкции в самом внутреннем содержащемся `Try` блок. Если совпадений `Catch` оператор найден, поиск продолжается `Catch` инструкции внешнего `Try…Catch…Finally` блок.  
  
 Локальные переменные из `Try` , недоступны в блоке `Catch` блокировку, поскольку это отдельные блоки. Если вы хотите использовать переменную в нескольких блоках, объявите переменную вне `Try...Catch...Finally` структуры.  
  
> [!TIP]
>  `Try…Catch…Finally` Оператор доступен в виде фрагмента кода IntelliSense. В диспетчере фрагментов кода, разверните узел **шаблоны кода — Если, для каждого Try Catch, свойство, и т. д**, а затем **обработка ошибок (исключения)**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="finally-block"></a>Блок finally  
 Если у вас есть один или несколько операторов, которые необходимо выполнить перед выходом из `Try` структуру, используйте `Finally` блок. Управление передается `Finally` блокировать только перед передачей из `Try…Catch` структуры. Это верно, даже если исключение возникает внутри `Try` структуры.  
  
 A `Finally` блок полезен для выполнить код, который должен выполняться, даже если существует одно исключение. Управление передается `Finally` блок независимо от того, как `Try...Catch` выходит из блока.  
  
 Код в `Finally` блок даже в случае возникновения кода `Return` инструкции в `Try` или `Catch` блока. Элемент управления не проходит из `Try` или `Catch` в соответствующем блоке `Finally` блока в следующих случаях:  
  
-   [Оператор End](../../../visual-basic/language-reference/statements/end-statement.md) встречается в `Try` или `Catch` блока.  
  
-   Объект <xref:System.StackOverflowException>создается в `Try` или `Catch` блока.</xref:System.StackOverflowException>  
  
 Не является допустимым Явная передача выполнения в `Finally` блок. Передача выполнения из `Finally` недопустимый блок, за исключением об исключении.  
  
 Если `Try` инструкция не содержит хотя бы один `Catch` блок, он должен содержать `Finally` блок.  
  
> [!TIP]
>  Если не нужно перехватывать определенные исключения, `Using` инструкции ведет себя как `Try…Finally` блока и гарантирует освобождение ресурсов независимо от способа выхода из блока. Это верно даже при возникновении необработанного исключения. Дополнительные сведения см. в разделе [с помощью инструкции](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="exception-argument"></a>Исключение аргумента  
 `Catch` Блок `exception` аргумент является экземпляром класса <xref:System.Exception>класс или класс, производный от `Exception` класса</xref:System.Exception> `Exception` Ошибки, возникшей в соответствующий экземпляр класса `Try` блок.  
  
 Свойства `Exception` объекта определить причину и место возникновения исключения. Например <xref:System.Exception.StackTrace%2A>списки свойств вызываемых методов, которые приводят к исключению, помогая обнаружить место возникновения ошибки в код.</xref:System.Exception.StackTrace%2A> <xref:System.Exception.Message%2A>Возвращает сообщение, описывающее исключение.</xref:System.Exception.Message%2A> <xref:System.Exception.HelpLink%2A>Возвращает ссылку на соответствующий файл справки.</xref:System.Exception.HelpLink%2A> <xref:System.Exception.InnerException%2A>Возвращает `Exception` возвращает объект, который вызвал текущее исключение, или `Nothing` Если нет исходного `Exception`.</xref:System.Exception.InnerException%2A>  
  
## <a name="considerations-when-using-a-trycatch-statement"></a>Рекомендации по использованию Try... Оператор catch  
 Используйте `Try…Catch` инструкции только для того, чтобы сообщить о совершении программы необычных или непредвиденных событий. Возможны следующие причины этого.  
  
-   Перехват исключений во время выполнения создает дополнительную нагрузку и может работать медленнее, чем предварительно проверки, чтобы избежать исключений.  
  
-   Если `Catch` блока обрабатывается неправильно, исключение может быть некорректно отображается для пользователей.  
  
-   Обработка исключений усложняет программы.  
  
 Вы не всегда требуется `Try…Catch` инструкцию, чтобы проверить условие, которое с большой вероятностью может возникать. В следующем примере проверяется, существует ли файл, прежде чем пытаться открыть его. Это уменьшает необходимость для перехвата исключения, созданного <xref:System.IO.File.OpenText%2A>метод.</xref:System.IO.File.OpenText%2A>  
  
 [!code-vb[VbVbalrStatements&#94;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_1.vb)]  
  
 Убедитесь, что код в `Catch` блоки мог правильно выдавать исключения для пользователей, через поточно-ведение журнала или соответствующие сообщения. В противном случае — может оставаться неизвестные исключения.  
  
## <a name="async-methods"></a>Асинхронные методы  
 Если пометить метод [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператора в методе. Оператор с `Await` оператор приостанавливает выполнение до завершения выполнения ожидаемой задачи. Задача представляет выполняющуюся работу. Если задачи, связанные с `Await` оператор завершает выполнение возобновляется в том же методе. Дополнительные сведения см. в разделе [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
 Задача, возвращаемая асинхронный метод может оказаться в состоянии faulted, указывающее на то, что она завершена из-за необработанного исключения. Задача также может оказаться в состоянии отмены, в результате чего `OperationCanceledException` вызываемом из выражения await. Для перехвата любого типа исключения, поместите `Await` выражения, который связан с задачей в `Try` блокировать и перехватить исключение в `Catch` блок. Пример приведен далее в этом разделе.  
  
 Задача может находиться в состоянии сбоя из-за несколькими исключениями ответственность за его с ошибками. Например задача может быть результатом вызова <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Когда ожидать такой задачи, перехваченное исключение является только одним из исключений и невозможно предсказать, какие исключение будет перехвачено. Пример приведен далее в этом разделе.  
  
 `Await` Выражение не может быть внутри `Catch` блока или `Finally` блока.  
  
## <a name="iterators"></a>Итераторы  
 Функции итератора или `Get` доступа выполняющий настраиваемую итерацию по коллекции. Использует итератор [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкции для возврата каждого элемента коллекции одной за раз. Вызов функции итератора с помощью [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Объект `Yield` инструкция может находиться внутри `Try` блок. Объект `Try` блок, содержащий `Yield` инструкция может иметь `Catch` блокируется и может иметь `Finally` блок. В разделе «Попробуйте блоков в Visual Basic» [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) пример.  
  
 Объект `Yield` оператор не может находиться внутри `Catch` блока или `Finally` блока.  
  
 Если `For Each` текст (за пределами функции итератора) вызывает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции итератора. A `Catch` блок внутри функции итератора перехватывает только исключения, которые возникают внутри функции итератора.  
  
## <a name="partial-trust-situations"></a>Ситуациях частичного доверия  
 В случаях частичного доверия, таких как приложения, размещенного в общей сетевой папке `Try...Catch...Finally` не перехватывает исключения безопасности, возникающие перед обращением к методу, содержащему вызов. В следующем примере, когда вы устанавливаете на общий ресурс сервера и запуск оттуда, создается ошибка «System.Security.SecurityException: Сбой запроса.» Дополнительные сведения об исключениях системы безопасности см. в разделе <xref:System.Security.SecurityException>класса.</xref:System.Security.SecurityException>  
  
 [!code-vb[VbVbalrStatements&#85;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_2.vb)]  
  
 В такой ситуации частичного доверия необходимо поместить `Process.Start` инструкции в отдельном `Sub`. Первоначальный вызов `Sub` завершится ошибкой. Это позволяет `Try...Catch` перехватить его перед `Sub` , содержащий `Process.Start` запущена и созданные исключения безопасности.  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует структуру `Try...Catch...Finally` инструкции.  
  
 [!code-vb[VbVbalrStatements&#86;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `CreateException` вызывает метод `NullReferenceException`. Код, который создает исключение, не находится в `Try` блок. Таким образом `CreateException` метод не обрабатывает исключение. `RunSample` Метод обработки исключения, так как вызов `CreateException` метод находится в `Try` блок.  
  
 Пример содержит `Catch` инструкции для различных типов исключений, упорядочены, начиная от наиболее конкретных к наиболее общим.  
  
 [!code-vb[VbVbalrStatements&#91;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_4.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `Catch When` инструкции для фильтрации по условному выражению. Если условное выражение вычислено как `True`, код в `Catch` блок.  
  
 [!code-vb[VbVbalrStatements&#92;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_5.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `Try…Catch` инструкции, содержащейся в `Try` блок. Внутренний `Catch` блок вызывает исключение, имеющее его `InnerException` свойство на исходное исключение. Внешний `Catch` блок сообщает свои собственные исключения и внутренним исключением.  
  
 [!code-vb[VbVbalrStatements&#93;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/try-catch-finally-statement_6.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется обработка исключений для асинхронных методов. Перехват исключения, которое применяется к асинхронной задачи, `Await` выражение находится в `Try` блок вызывающего объекта и исключение перехватывается в `Catch` блок.  
  
 Раскомментируйте строку `Throw New Exception` в этом примере для демонстрации обработки исключений. Исключение перехватывается в `Catch` блокировать задачи `IsFaulted` свойству `True`и эта задача `Exception.InnerException` свойству исключение.  
  
 Раскомментируйте `Throw New OperationCancelledException` строки, чтобы продемонстрировать, что происходит при отмене асинхронного процесса. Исключение перехватывается в `Catch` блока, а задача `IsCanceled` свойству `True`. Однако при некоторых условиях, которые не применяются к этому примеру `IsFaulted` равен `True` и `IsCanceled` имеет значение `False`.  
  
 [!code-vb[csAsyncExceptions&#1;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_7.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется обработка исключений, когда несколько задач могут привести к нескольким исключениям. `Try` Блока `Await` выражение для задачи, <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>возвращаемые.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Задача завершается, когда трех задач, который <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>применяется завершены.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>  
  
 Каждая из трех задач вызывает исключение. `Catch` Блок перебор исключений, которые находятся в `Exception.InnerExceptions` свойства задачи, `Task.WhenAll` возвращается.  
  
 [!code-vb[csAsyncExceptions&#3;](../../../csharp/language-reference/keywords/codesnippet/VisualBasic/try-catch-finally-statement_8.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Information.Err%2A></xref:Microsoft.VisualBasic.Information.Err%2A>   
 <xref:System.Exception></xref:System.Exception>   
 [Оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)   
 [Советы и рекомендации по использованию фрагментов кода](https://docs.microsoft.com/visualstudio/ide/best-practices-for-using-code-snippets)   
 [Обработка исключений](https://msdn.microsoft.com/library/dd997415)   
 [Оператор Throw](../../../visual-basic/language-reference/statements/throw-statement.md)
