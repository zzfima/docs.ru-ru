---
title: Руководство по программированию на C#. Явная реализация интерфейса
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628154"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Явная реализация интерфейса (Руководство по программированию в C#)

Если [класс](../../language-reference/keywords/class.md) реализует два интерфейса, содержащих член с одинаковой сигнатурой, при реализации такого члена в классе оба интерфейса будут использовать этот член в качестве собственной реализации. В следующем примере все вызовы `Paint` приводят к вызову одного и того же метода. Первый пример определяет типы:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

Следующий пример вызывает методы:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Если два члена интерфейса выполняют разные функции, это может привести к некорректной реализации одного или обоих интерфейсов. Член интерфейса можно реализовать явно, создав член класса, который вызывается только через этот интерфейс и относится только к нему. Укажите в имени члена класса имя интерфейса и точку. Пример:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

Член класса `IControl.Paint` доступен только через интерфейс `IControl`, а `ISurface.Paint` — только через интерфейс `ISurface`. Обе реализации метода будут разделены, и ни одна из них не будет доступна в классе напрямую. Пример:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

Явная реализация также применяется в случаях, когда в каждом из двух интерфейсов объявляются разные члены (например, свойство и метод) с одинаковыми именами. Чтобы реализовать оба интерфейса и избежать ошибок компилятора, класс должен использовать явную реализацию либо свойства `P`, либо метода `P`, либо одновременно обоих этих членов. Пример:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

Если класс наследует реализацию метода от интерфейса, этот метод доступен только через ссылку типа интерфейса. Наследуемый член не отображается как часть открытого интерфейса. Следующий пример определяет реализацию по умолчанию для метода интерфейса:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

Следующий пример вызывает реализацию по умолчанию:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Любой класс, реализующий интерфейс `IControl`, может переопределить метод `Paint` по умолчанию либо в качестве открытого метода, либо в качестве реализации интерфейса.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](../classes-and-structs/index.md)
- [Интерфейсы](./index.md)
- [Наследование](../classes-and-structs/inheritance.md)
