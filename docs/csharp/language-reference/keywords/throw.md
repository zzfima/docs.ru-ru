---
title: "throw (Справочник по C#) | Microsoft Docs"
ms.date: "2015-03-02"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "throw"
  - "throw_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "throw - ключевое слово [C#]"
  - "throw - оператор [C#]"
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
caps.handback.revision: 22
---
# throw (Справочник по C#)
Оператор `throw` используется для сообщения об аномальных ситуациях \(исключениях\) в ходе выполнения программы.  
  
## Заметки  
 Созданное исключение — это объект, класс которого унаследован от объекта <xref:System.Exception?displayProperty=fullName>, как показано в следующем примере.  
  
```  
class MyException : System.Exception {}  
// ...  
throw new MyException();  
```  
  
 Обычно оператор `throw` используется с операторами `try-catch` и `try-finally`.  Оператор [throw](../../../csharp/language-reference/keywords/throw.md) можно включить в блок `catch`, чтобы заново создать исключение, перехваченное блоком `catch`.  В этом случае оператор [throw](../../../csharp/language-reference/keywords/throw.md) не принимает операнд исключения.  Дополнительные сведения и примеры см. в разделах [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) и [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Пример  
 В этом примере демонстрируется вызов исключения с помощью оператора `throw`.  
  
 [!code-cs[csrefKeywordsExceptions#5](../../../csharp/language-reference/keywords/codesnippet/csharp/throw_1.cs)]  
  
## Пример кода  
 См. примеры в разделах [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) и [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Операторы try, catch и throw в C\+\+](../../../csharp/language-reference/keywords/try-catch.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [Практическое руководство. Явное создание исключения](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)