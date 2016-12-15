---
title: "try-catch (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "try"
  - "try_CSharpKeyword"
  - "catch"
  - "catch_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "catch - ключевое слово [C#]"
  - "try-catch - оператор [C#]"
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
caps.handback.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# try-catch (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор try\-catch состоит из блока `try`, за которым следует одно или несколько предложений `catch`, задающих обработчики для различных исключений.  
  
## Заметки  
 При возникновении исключения общеязыковая среда выполнения \(CLR\) ищет оператор `catch`, который обрабатывает это исключение.  Если текущий выполняемый метод не содержит такой блок `catch`, среда CLR выполняет поиск в методе, который вызвал текущий метод, и так далее вверх по стеку вызовов.  Если блок `catch` не находится, то среда CLR отображает пользователю сообщение о необработанном исключении и останавливает выполнение программы.  
  
 Блок `try` содержит защищенный код, который может вызвать исключение.  Этот блок выполняется, пока не возникнет исключение или пока он не будет успешно завершен.  Например, следующая попытка приведения объекта `null` вызывает исключение <xref:System.NullReferenceException>:  
  
```c#  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 Хотя предложение `catch` может использоваться без аргументов для перехвата любого типа исключения, такое использование не рекомендуется.  В целом вы должны перехватывать только те исключения, после которых вы знаете, как выполнить восстановление.  Поэтому всегда следует указывать аргумент объекта, производный от <xref:System.Exception?displayProperty=fullName>, например:  
  
```c#  
catch (InvalidCastException e)   
{  
}  
```  
  
 В одном блоке try\-catch можно использовать несколько определенных предложений `catch`.  В этом случае важен порядок предложений `catch`, поскольку предложения `catch` проверяются по порядку.  Перехватывайте более конкретные исключения перед менее конкретными.  Компилятор выдает ошибку, если вы расположили блоки catch в таком порядке, что последующий блок может быть никогда не достигнут.  
  
 Использование аргументов `catch` представляет один из способов фильтрации исключений, которые требуется обработать.  Вы также можете использовать выражение предиката, которое дополнительно проверяет исключение, чтобы решить, следует ли его обрабатывать.  Если выражение предиката возвращает значение false, поиск обработчика продолжается.  
  
```c#  
Catch (ArgumentException e) if (e.ParamName == “…”)  
{  
}  
```  
  
 Фильтры исключений предпочтительнее перехвата и повторного вызова \(объясняется ниже\), поскольку фильтры оставляют стек в целости и сохранности.  Если последующий обработчик разгружает стек, вы можете увидеть, откуда изначально произошло исключение, а не только последнее место, в котором оно было повторно вызвано.  Обычно выражения фильтра исключений используются для ведения журнала.  Вы можете создать функцию предиката, которая всегда возвращает значение false, а также записывает выходной результат в журнал, чтобы регистрировать исключения в журнале по мере их поступления без необходимости их обработки и повторного вызова.  
  
 Оператор [throw](../../../csharp/language-reference/keywords/throw.md) можно включить в блок `catch`, чтобы заново вызвать исключение, перехваченное блоком `catch`.  В следующем примере извлекаются сведения об источнике из исключения <xref:System.IO.IOException>, а затем это исключение вызывается для родительского метода.  
  
```c#  
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
  
 Вы можете перехватывать одно исключение и вызывать другое исключение.  При этом следует указать перехватываемое исключение как внутреннее, как показано в следующем примере.  
  
```c#  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 Вы также можете повторно вызывать исключение при выполнении указанного условия, как показано в следующем примере.  
  
```c#  
  
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
  
 В блоке `try` инициализируйте только те переменные, которые в нем объявлены.  В противном случае до завершения выполнения блока может возникнуть исключение.  Например, в следующем примере кода переменная `n` инициализируется внутри блока `try`.  Попытка использовать данную переменную вне этого блока `try` в инструкции `Write(n)` приведет к ошибке компилятора.  
  
```c#  
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
  
 Дополнительные сведения о перехвате исключений см. в разделе [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
## Исключения в асинхронных методах  
 Асинхронный метод помечается модификатором [async](../../../csharp/language-reference/keywords/async.md) и обычно содержит одно или несколько выражений или инструкций await.  Выражение await применяет оператор [await](../../../csharp/language-reference/keywords/await.md) к <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.  
  
 Когда управление достигает `await` в асинхронном методе, выполнение метода приостанавливается до завершения выполнения ожидающей задачи.  После завершения задачи выполнение в методе может быть возобновлено.  Дополнительные сведения см. в разделах [Асинхронное программирование с использованием ключевых слов Async и Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md) и [Поток управления в асинхронных программах](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Завершенная задача, к которой применяется `await`, может находиться в состоянии сбоя из\-за необработанного исключения в методе, который возвращает эту задачу.  Ожидание задачи вызывает исключение.  Задача также может завершиться в отмененном состоянии, если отменяется асинхронный процесс, возвращающий эту задачу.  Ожидание отмененной задачи вызывает `OperationCanceledException`.  Дополнительные сведения о том, как отменить асинхронный процесс, см. в разделе [Настройка асинхронного приложения](../Topic/Fine-Tuning%20Your%20Async%20Application%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Для перехвата исключения ожидайте задачу в блоке `try` и перехватывайте это исключение в соответствующем блоке `catch`.  См. пример в разделе «Пример».  
  
 Задача может быть в состоянии сбоя, если в ожидаемом асинхронном методе произошло несколько исключений.  Например, задача может быть результатом вызова метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  При ожидании такой задачи перехватывается только одно из исключений и невозможно предсказать, какое исключение будет перехвачено.  См. пример в разделе «Пример».  
  
## Пример  
 В следующем примере блок `try` содержит вызов метода `ProcessString`, который может вызвать исключение.  Предложение `catch` содержит обработчик исключений, который просто отображает сообщение на экране.  Когда оператор `throw` вызывается из `MyMethod`, система осуществляет поиск оператора `catch` и отображает сообщение `Exception caught`.  
  
 [!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## Пример  
 В следующем примере используются два блока catch и перехватывается наиболее конкретное исключение, поступившее первым.  
  
 Чтобы перехватить наименее конкретное исключение, можно заменить оператор throw в `ProcessString` следующим оператором: `throw new Exception()`.  
  
 Если в этом примере первым поместить блок catch для перехвата наименее конкретного исключения, то появится следующее сообщение об ошибке: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.  
  
 [!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## Пример  
 В следующем примере демонстрируется обработка исключений для асинхронных методов.  Для перехвата исключения, вызванного асинхронной задачей, поместите выражение `await` в блок `try` и перехватывайте это исключение в блоке `catch`.  
  
 Раскомментируйте строку `throw new Exception` в этом примере для демонстрации обработки исключений.  Для свойства `IsFaulted` задачи установлено значение `True`, для свойства `Exception.InnerException` задачи установлено это исключение, а исключение перехватывается в блоке `catch`.  
  
 Раскомментируйте строку `throw new OperationCancelledException` для демонстрации того, что происходит, когда вы отменяете асинхронный процесс.  Для свойства `IsCanceled` задачи устанавливается значение `true`, и исключение перехватывается в блоке `catch`.  В некоторых условиях, которые неприменимы в данном примере, для свойства `IsFaulted` задачи устанавливается значение `true`, а для `IsCanceled` устанавливается значение `false`.  
  
 [!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## Пример  
 В следующем примере демонстрируется обработка исключений, когда несколько задач могут привести к нескольким исключениям.  Блок `try` ожидает задачу, которая возвращается вызовом метода <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Эта задача завершается после завершения трех задач, к которым применяется WhenAll.  
  
 Каждая из трех задач вызывает исключение.  Блок `catch` выполняет итерацию по исключениям, которые обнаруживаются в свойстве `Exception.InnerExceptions` задачи, возвращенной методом <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  
  
 [!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы try, throw и catch \(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)