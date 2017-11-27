---
title: "Оператор Function (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: "62"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 667ab7ceb54e1f339fd645883ca2686c0cbb72b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="function-statement-visual-basic"></a>Оператор Function (Visual Basic)
Объявляет имя, параметры и код, определяющие `Function` процедуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Части  
  
-   `attributelist`  
  
     Необязательно. В разделе [список атрибутов](attribute-list.md).  
  
-   `accessmodifier`  
  
     Необязательно. Ниже указаны доступные значения.  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Закрытые](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Необязательно. Ниже указаны доступные значения.  
  
    -   [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Необязательно. В разделе [общих](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Необязательно. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Необязательно. В разделе [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Необязательно. В разделе [итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Обязательный. Имя процедуры. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Необязательно. Список параметров типа для универсальной процедуры. В разделе [введите список](type-list.md).  
  
-   `parameterlist`  
  
     Необязательно. Список имен локальных переменных, представляющих параметры этой процедуры. В разделе [список параметров](parameter-list.md).  
  
-   `returntype`  
  
     Обязателен, если `Option Strict` — `On`. Тип данных значения, возвращаемые этой процедурой.  
  
-   `Implements`  
  
     Необязательно. Указывает, что эта процедура реализует один или несколько `Function` процедуры, каждая из которых определена в интерфейс, реализуемый этой процедуры классом или структурой. В разделе [реализует оператор](implements-statement.md).  
  
-   `implementslist`  
  
     Является обязательным, если предоставлен параметр `Implements`. Список реализуемых процедур `Function`.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Каждый элемент `implementedprocedure` имеет перечисленные ниже синтаксис и компоненты.  
  
     `interface.definedname`  
  
    |Отделение|Описание|  
    |---|---|  
    |`interface`|Обязательный. Имя интерфейса, реализуемого данной процедурой, содержащего класса или структуры.|  
    |`definedname`|Обязательный. Имя, под которым процедура определена в `interface`.|  
  
-   `Handles`  
  
     Необязательно. Указывает, что эта процедура может обрабатывать одно или несколько конкретных событий. В разделе [обрабатывает](handles-clause.md).  
  
-   `eventlist`  
  
     Является обязательным, если предоставлен параметр `Handles`. Список событий, которые обрабатывает данная процедура.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Каждый элемент `eventspecifier` имеет перечисленные ниже синтаксис и компоненты.  
  
     `eventvariable.event`  
  
    |Отделение|Описание|  
    |---|---|  
    |`eventvariable`|Обязательный. Объектная переменная объявлена с типом данных класса или структуры, который инициирует событие.|  
    |`event`|Обязательный. Имя события, которое обрабатывает данная процедура.|  
  
-   `statements`  
  
     Необязательно. Блок операторов для выполнения этой процедуры.  
  
-   `End Function`  
  
     Завершает определение данной процедуры.  
  
## <a name="remarks"></a>Примечания  
 Весь исполняемый код должен быть внутри процедуры. Каждая процедура в свою очередь, объявлен внутри класса, структуры или модуль, который называется содержащего класса, структуры или модуля.  
  
 Чтобы вернуть значение в вызывающий код, используйте `Function` процедуры; в противном случае используйте `Sub` процедуры.  
  
## <a name="defining-a-function"></a>Определение функции  
 Можно определить `Function` процедуры только на уровне модуля. Таким образом что контекст объявления для функции должен быть класс, структура, модуль или интерфейс и не может быть исходным файлом, пространство имен, процедура или блок. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).  
  
 `Function`процедуры по умолчанию для общего доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа.  
  
 Объект `Function` процедура может объявить тип данных, процедура возвращает значение. Можно указать любой тип данных или имя перечисления, структуры, класса или интерфейса. Если не указать `returntype` , процедура возвращает `Object`.  
  
 Если в этой процедуре используется `Implements` ключевое слово, содержащего класса или структуры, также должен иметь `Implements` оператор, который следует сразу за его `Class` или `Structure` инструкции. `Implements` Инструкция должна включать каждого интерфейса, который указан в `implementslist`. Тем не менее имя, по которому интерфейс определяет `Function` (в `definedname`) не должны совпадать с именем этой процедуры (в `name`).  
  
> [!NOTE]
>  Лямбда-выражения можно использовать для определения встроенной функции выражения. Дополнительные сведения см. в разделе [выражение функции](../../../visual-basic/language-reference/operators/function-expression.md) и [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Возврат из функции  
 Когда `Function` процедура возвращает в вызывающий код, выполнение продолжается с оператора, следующего за оператором, который вызвал процедуру.  
  
 Для возврата значения из функции, можно присвоить значение имени функции или включить ее в `Return` инструкции.  
  
 `Return` Инструкция одновременно назначает возвращаемое значение и выходит из функции, как показано в следующем примере.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 В следующем примере возвращаемое значение присваивается имени функции `myFunction` , а затем использует `Exit Function` для возврата.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 `Exit Function` И `Return` инструкции вызывают Немедленный выход из `Function` процедуры. Любое количество `Exit Function` и `Return` операторы могут использоваться в любом месте в процедуре, и могут быть использованы смешанные `Exit Function` и `Return` инструкции.  
  
 Если вы используете `Exit Function` без присвоения значения `name`, процедура возвращает значение по умолчанию для типа данных, который указан в `returntype`. Если `returntype` не указан, процедура возвращает `Nothing`, который является значением по умолчанию для `Object`.  
  
## <a name="calling-a-function"></a>Вызов функции  
 Вызывается `Function` процедуры с помощью имени процедуры, за которым следует список аргументов в скобки в выражении. Круглые скобки можно опустить только в том случае, если вы не имеет аргументов. Тем не менее код является более удобочитаемым, если всегда использовать круглые скобки.  
  
 Можно вызвать `Function` процедуры одинаково вызывать любую библиотеку функции, такие как `Sqrt`, `Cos`, или `ChrW`.  
  
 Можно также вызвать функцию с помощью `Call` ключевое слово. В этом случае возвращаемое значение игнорируется. Использование `Call` ключевое слово не рекомендуется в большинстве случаев. Дополнительные сведения см. в разделе [инструкции Call](call-statement.md).  
  
 Visual Basic иногда упорядочение арифметические выражения для повышения внутренней эффективности. По этой причине не следует использовать `Function` процедуры в арифметическом выражении, если функция изменяет значение переменных в одном выражении.  
  
## <a name="async-functions"></a>Асинхронные функции  
 *Async* позволяет вызывать асинхронные функции, не прибегая к использованию явных обратных вызовов или ручному разделению кода между несколькими функции или лямбда-выражения.  
  
 Если определить функцию с [Async](../../../visual-basic/language-reference/modifiers/async.md) модификатор, можно использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в функции. Когда управление достигает `Await` выражения в `Async` функции, управление возвращается вызывающему объекту и выполнение в функции приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в функции.  
  
> [!NOTE]
>  `Async` Процедура возвращает вызывающему встречает первый ожидаемый объект, который еще не завершена, или он доходит до конца `Async` процедуры, какое событие происходит раньше.  
  
 `Async` Функция может иметь тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.Task>. Пример `Async` функции, которая имеет тип возвращаемого значения <xref:System.Threading.Tasks.Task%601> приведены ниже.  
  
 `Async` Функция не может объявить все [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) параметров.  
  
 Объект [оператор Sub](sub-statement.md) также могут быть помечены с помощью `Async` модификатор. Это в первую очередь для обработчиков событий, где не может быть возвращено значение. `Async``Sub` Процедуру нельзя ожидать и код, вызывающий `Async``Sub` процедура не может перехватывать исключения, возникающие с `Sub` процедуры.  
  
 Дополнительные сведения о `Async` функции, в разделе [асинхронное программирование с использованием ключевых слов Async и Await](../../../visual-basic/programming-guide/concepts/async/index.md), [поток управления в асинхронных программах](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), и [асинхронные типы возвращаемых значений](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Функции итератора  
 *Итератор* функция выполняет настраиваемую итерацию по коллекции, например список или массив. Использует функции итератора [Yield](yield-statement.md) инструкции для возврата всех элементов, одну за другой. Когда [Yield](yield-statement.md) инструкция исчерпана, текущее расположение в коде запоминается. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Итератор вызывается из клиентского кода с помощью [For Each... Далее](for-each-next-statement.md) инструкции.  
  
 Тип возвращаемого значения функции итератора может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Function` инструкции для объявления имени, параметров и кода, образующих текст `Function` процедуры. `ParamArray` Модификатор разрешает функции принимать переменное число аргументов.  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается функция, объявленная в предыдущем примере.  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере `DelayAsync` — `Async``Function` с типом возвращаемого значения <xref:System.Threading.Tasks.Task%601>. `DelayAsync` имеет инструкцию `Return`, которая возвращает целое число. Поэтому объявление функции `DelayAsync` должен иметь тип возвращаемого значения `Task(Of Integer)`. Так как возвращаемый тип — `Task(Of Integer)`, вычисление `Await` выражения в `DoSomethingAsync` создает целое число. Это показано в этом операторе: `Dim result As Integer = Await delayTask`.  
  
 `startButton_Click` Процедура является примером `Async Sub` процедуры. Поскольку `DoSomethingAsync` — `Async` функции, задача для вызова `DoSomethingAsync` должна быть ожидаемой, как показывает следующая инструкция: `Await DoSomethingAsync()`. `startButton_Click``Sub` Процедура должна быть определена с `Async` модификатор из-за `Await` выражение.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Sub](sub-statement.md)  
 [Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Список параметров](parameter-list.md)  
 [Оператор Dim](dim-statement.md)  
 [Оператор Call](call-statement.md)  
 [Of](of-clause.md)  
 [Массивы параметров](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Выражение функции](../../../visual-basic/language-reference/operators/function-expression.md)
