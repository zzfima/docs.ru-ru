---
title: "Интерполяция строк. Язык C#"
description: "Узнайте, как работает интерполяция строк в C# 6"
keywords: ".NET, .NET Core, C#, строка"
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de8f77e44319731f87f00d227a5373a78bf40e32
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="string-interpolation-in-c"></a>Интерполяция строк в C# #

Интерполяция строк — это процесс замены заполнителей в строке значениями строковой переменной. До версии C# 6 для этого приходилось применять метод `System.String.Format`. Он работает нормально, но использует только нумерованные заполнители, что порой затрудняет восприятие синтаксических конструкций и усложняет их.

В других языках программирования интерполяция строк уже достаточно давно является встроенной возможностью. Например, в PHP можно сделать так:

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

Наконец, в C# 6 мы тоже может выполнять такую интерполяцию строк. Укажите перед строкой `$`, и все переменные и (или) выражения в ней будут заменены соответствующими значениями.

## <a name="prerequisites"></a>Предварительные требования
Компьютер должен быть настроен для выполнения .NET Core. Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).
Это приложение можно запустить в ОС Windows, Ubuntu Linux, macOS или в контейнере Docker. Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас. В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом. Вы можете заменить его на любое другое средство, с которым вам удобно работать.

## <a name="create-the-application"></a>Создание приложения

Теперь, когда вы установили все нужные средства, создайте новое приложение .NET Core. Чтобы использовать генератор командной строки, создайте для проекта каталог, например `interpolated`, и выполните следующую команду в любой удобной оболочке:

```
dotnet new console
```

Эта команда создает скелет проекта .NET Core: файл проекта *interpolated.csproj* и файл исходного кода *Program.cs*. Нужно также выполнить команду `dotnet restore`, чтобы восстановить зависимости, необходимые для компиляции проекта.

Чтобы выполнить программу, используйте `dotnet run`. Она выведет в консоль сообщение "Hello, World".

## <a name="intro-to-string-interpolation"></a>Знакомство с интерполяцией строк

При использовании `System.String.Format` в строку включаются специальные местозаполнители, которые заменяются параметрами, переданными вслед за строкой. Например:

[!code-csharp[Пример использования метода String.Format](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

Этот код выводит строку "My name is Matt Groves".

В C# 6 вы теперь можете обойтись без `String.Format`. Определите интерполируемую строку, указав перед ней символ `$`, а затем просто используйте переменные прямо в этой строке. Например:

[!code-csharp[Пример интерполяции](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

Можно использовать не только переменные. В фигурных скобках можно указать любое допустимое выражение. Например:

[!code-csharp[Пример выражения в интерполяции](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

Этот пример кода выведет данные:

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a>Как работает интерполяция строк

Компилятор преобразует синтаксис интерполяции в String.Format. Таким образом, вы можете выполнять [все, что раньше можно было сделать со String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).

Например, можно добавить отбивку и форматирование чисел:

[!code-csharp[Пример интерполяции с форматированием](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

Приведенный выше пример выведет примерно следующее:

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Если имя переменной не найдено, создается ошибки времени компиляции.

Например:

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

При компиляции этого кода, вы получите ошибки:
 
* `Cannot use local variable 'adj' before it is declared` — это значит, что переменная `adj` объявляется *после* интерполируемой строки.
* `The name 'otheranimal' does not exist in the current context` — это значит, что переменная с именем `otheranimal` вообще никогда не объявляется.

## <a name="localization-and-internationalization"></a>Локализация и интернационализация

Интерполируемые строки поддерживают `IFormattable` и `FormattableString`, что можно удачно применять в контексте интернационализации.

По умолчанию интерполируемая строка использует текущие настройки языка и региональных параметров. Чтобы использовать другие параметры, можно выполнить приведение строки к типу `IFormattable`.

Например:

[!code-csharp[Пример интерполяции с интернационализацией](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a>Заключение 

В этом руководстве вы узнали, как использовать функции интерполяции строк в C# 6. По сути это упрощенная запись обычной инструкции `String.Format`, допускающая несколько более сложных вариантов использования.

