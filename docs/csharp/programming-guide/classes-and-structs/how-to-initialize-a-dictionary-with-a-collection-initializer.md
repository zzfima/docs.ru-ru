---
title: Руководство по программированию на C#. Инициализация словаря с помощью инициализатора набора
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 22f80365b974df66999ac68f7bc2a9ffa7d445a5
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596818"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#)

<xref:System.Collections.Generic.Dictionary%602> содержит коллекцию пар "ключ-значение". Ее метод <xref:System.Collections.Generic.Dictionary%602.Add*> принимает два параметра: один для ключа, другой — для значения. Для инициализации <xref:System.Collections.Generic.Dictionary%602> или любой коллекции, метод `Add` которой принимает несколько параметров, можно заключить каждый набор параметров в скобки, как показано в приведенном ниже примере. Другой вариант — использовать инициализатор индекса, как показано также в следующем примере.

## <a name="example"></a>Пример

В следующем примере кода <xref:System.Collections.Generic.Dictionary%602> инициализируется экземплярами типа `StudentName`.  Первая инициализация использует метод `Add` с двумя аргументами. Компилятор создает вызов метода `Add` для каждой пары ключа `int` и значения `StudentName`. Вторая инициализация использует общедоступный метод индексатора чтения и записи класса `Dictionary`:

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

Обратите внимание на две пары фигурных скобок в каждом элементе коллекции в первом объявлении. Внутренняя пара фигурных скобок заключает инициализатор объекта `StudentName`, а внешняя пара — инициализатор пары "ключ – значение", которая будет добавлена в коллекцию `students` <xref:System.Collections.Generic.Dictionary%602>. И наконец, весь инициализатор коллекции для словаря заключается в фигурные скобки. Во второй инициализации левая часть оператора присваивания является ключом, а правая часть — значением, использующим инициализатор объекта для `StudentName`.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Инициализаторы объектов и коллекций](./object-and-collection-initializers.md)
