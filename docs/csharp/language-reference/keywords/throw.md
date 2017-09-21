---
title: "throw (Справочник по C#)"
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a>throw (Справочник по C#)
Сообщает о возникновении исключения во время выполнения программы.  
  
## <a name="remarks"></a>Примечания

Синтаксис `throw` выглядит следующим образом:

```csharp
throw [e]
```
где `e` — это экземпляр класса, производного от <xref:System.Exception?displayProperty=fullName>. В следующем примере используется оператор `throw` для создания @System.IndexOutOfRangeException, если аргумент, переданный в метод с именем `GetNumber`, не соответствует допустимому индексу внутреннего массива.

[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

Затем вызывающие объекты метода используют блок `try-catch` или `try-catch-finally` для обработки исключения. В следующем примере показана обработка исключения, созданного методом `GetNumber`.

[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>Повторное создание исключения

`throw` можно также использовать в блоке `catch` для повторного создания исключения, обрабатываемого в блоке `catch`.  В этом случае оператор `throw` не принимает операнд исключения. Это наиболее полезно, когда метод передает аргумент от вызывающего объекта в другой метод библиотеки, а метод библиотеки создает исключение, которое должно быть передано вызывающему объекту. Например, в следующем примере повторно создается исключение @System.NullReferenceException, возникающее при попытке получить первый символ неинициализированной строки. 

[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> Можно также использовать синтаксис `throw e` в блоке `catch`, чтобы создать исключение, которое будет передано вызывающему объекту. В этом случае трассировка стека исходного исключения, которое доступно из свойства @System.Exception.Stacktrace, не сохраняется.
 
## <a name="the-throw-expression"></a>Выражение `throw`

Начиная с C# 7 `throw` можно использовать в качестве выражения, а также как оператор. Это позволяет вызывать исключения в контекстах, которые ранее не поддерживались. Сюда входит следующее.

- [Условный оператор](../operators/conditional-operator.md). В следующем примере используется исключение `throw` для создания @System.ArgumentException, если методу передается массив пустых строк. До выхода C# 7 эта логика должна была отображаться в инструкции `if`/`else`.

   [!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [Оператор объединения с NULL](../operators/null-conditional-operator.md). В следующем примере выражение `throw` используется с оператором, принимающим значение NULL, для создания исключения, если строка, назначенная свойству `Name` является `null`.
 
   [!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- Метод или [лямбда](../../lambda-expressions.md), воплощающие выражение. В следующем примере показан метод, воплощающий выражение, который создает @System.InvalidCastException, так как преобразование в значение @System.DateTime не поддерживается.
 
   [!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Операторы try, catch и throw в C++](../../../csharp/language-reference/keywords/try-catch.md)   
 [Ключевые слова C#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [Практическое руководство. Явное создание исключений](https://msdn.microsoft.com/library/xhcbs8fz)

