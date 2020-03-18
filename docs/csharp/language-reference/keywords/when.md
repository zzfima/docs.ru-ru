---
title: Справочник по C#. Контекстное ключевое слово when
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 6a61c42ba2d01e84ffae376bf95c99877437be85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712836"
---
# <a name="when-c-reference"></a>when (справочник по C#)

Для того чтобы указать условие фильтра в двух контекстах, можно использовать контекстно-зависимое ключевое слово `when`.

- В операторе `catch` блока [try/catch](try-catch.md) или [try/catch/finally](try-catch-finally.md).
- В метке `case` оператора [switch](switch.md).

## <a name="when-in-a-catch-statement"></a>`when` в операторе `catch`

Начиная с C# версии 6, `when` можно использовать в операторе `catch`, чтобы задать условие, которое должно быть истинным для выполнения обработчика определенного исключения. Синтаксис:

```csharp
catch (ExceptionType [e]) when (expr)
```

здесь *expr* представляет собой выражение, которое оценивает значение типа Boolean. Если он возвращает `true`, обработчик исключений выполняется, а если `false`, то нет.

В следующем примере используется ключевое слово `when`, которое позволяет условно выполнять обработчики для <xref:System.Net.Http.HttpRequestException> в зависимости от того, какой текст содержит сообщение об исключении.

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a>`when` в операторе `switch`

Начиная с версии C# 7.0 метки `case` больше не должны быть взаимоисключающими, а порядок отображения меток `case` в операторе `switch` может определять, какие блоки switch должны быть выполнены. Ключевое слово `when` позволяет задать условие фильтра, при котором соответствующая метка case будет иметь значение true, только если условие фильтра также имеет значение true. Синтаксис:

```csharp
case (expr) when (when-condition):
```

здесь *expr* является постоянным шаблоном или типом шаблона, который сравнивается с соответствующим выражением, а *условие when* представляет собой любое логическое выражение.

В следующем примере ключевое слово `when` используется для проверки объектов `Shape`, которые имеют нулевую область, а также для проверки различных объектов `Shape` с областью больше нуля.

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a>См. также раздел

- [Оператор switch](switch.md)
- [Оператор try-catch](try-catch.md)
- [Оператор try/catch/finally](try-catch-finally.md)
