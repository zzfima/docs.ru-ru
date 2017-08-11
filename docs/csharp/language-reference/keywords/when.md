---
title: "when (справочник по C#)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: ae869fa04d2dfb963694f258624c5cd594ff1184
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
 # <a name="when-c-reference"></a>when (справочник по C#)

Для того чтобы указать условие фильтра в двух контекстах, можно использовать контекстно-зависимое ключевое слово `when`.

- В операторе `catch` блока [try/catch](try-catch.md) или [try/catch/finally](try-catch-finally.md).
- В метке `case` оператора [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` в операторе `catch`

Начиная с C# версии 6, `When` можно использовать в операторе `catch`, чтобы задать условие, которое должно быть истинным для выполнения обработчика определенного исключения. Он имеет следующий синтаксис:

```csharp
catch ExceptionType [e] when (expr)
```
здесь *expr* представляет собой выражение, которое оценивает значение типа Boolean. Если он возвращает `true`, обработчик исключений выполняется, а если `false`, то нет. 

В следующем примере используется ключевое слово `when`, которое позволяет условно выполнять обработчики для @System.Net.HttpRequestException в зависимости от того, какой текст содержит сообщение об исключении.

 [!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` в операторе `switch`

Начиная с версии 7, метки `case` больше не должны быть взаимоисключающими, а порядок отображения меток `case` в операторе `switch` может определять, какие блоки switch должны быть выполнены. Ключевое слово `when` позволяет задать условие фильтра, при котором соответствующая метка case будет иметь значение true, только если условие фильтра также имеет значение true. Он имеет следующий синтаксис:

```csharp
case (expr) when (when-condition):
```
здесь *expr* является постоянным шаблоном или типом шаблона, который сравнивается с соответствующим выражением, а *условие when* представляет собой любое логическое выражение. 

В следующем примере ключевое слово `when` используется для проверки объектов `Shape`, которые имеют нулевую область, а также для проверки различных объектов `Shape` с областью больше нуля. 

 [!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>См. также 
  [Оператор switch](switch.md)  
  [Оператор try-catch](try-catch.md)  
  [Оператор try/catch/finally](try-catch-finally.md) 


