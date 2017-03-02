---
title: "Типы коллекций Hashtable и Dictionary"
description: "Типы коллекций Hashtable и Dictionary"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0f18fac7-fd0d-4f25-a046-1d3d51de062e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 58c87f9e86b5b97feb654e92a56f81940c201a6a
ms.lasthandoff: 03/02/2017

---

# <a name="hashtable-and-dictionary-collection-types"></a>Типы коллекций Hashtable и Dictionary

Класс [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) и универсальные классы [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и [System.Collections.Concurrent.ConcurrentDictionary<T>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) реализуют интерфейс [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary). Универсальный класс `Dictionary<T>` также реализует универсальный интерфейс [IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2). Таким образом, каждый элемент в этих коллекциях является парой "ключ-значение".

Объект `Hashtable` состоит из контейнеров, содержащих элементы коллекции. Контейнер — это виртуальная подгруппа элементов внутри объекта `Hashtable`, которая обеспечивает более простой и быстрый поиск и извлечение, чем в большинстве коллекций. Каждый контейнер связан с хэш-кодом, который создается с помощью хэш-функции и основан на ключе элемента.

Универсальный класс [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) — это неупорядоченная коллекция для хранения уникальных элементов. 

Хэш-функция — это алгоритм, возвращающий числовой хэш-код на основе ключа. Ключом является значение какого-либо свойства хранимого объекта. Хэш-функция должна всегда возвращать один и тот же хэш-код для определенного ключа. Возможна ситуация, когда хэш-функция создает один хэш-код для разных ключей. Однако хэш-функция, создающая уникальный хэш-код для каждого уникального ключа, обеспечивает лучшую производительность при извлечении элементов из хэш-таблицы.

Каждый объект, который используется в качестве элемента в `Hashtable`, должен иметь возможность создать свой хэш-код, используя реализацию метода `GetHashCode`. 

Когда объект добавляется в `Hashtable`, он сохраняется в контейнере, который связан с хэш-кодом, соответствующим хэш-коду объекта. При поиске значения в `Hashtable` создается хэш-код для этого значения, и поиск осуществляется в контейнере, связанном с этим хэш-кодом.

Например, хэш-функция для строки может принимать коды ASCII каждого символа в строке и объединять их для создания хэш-кода. Строка "пикник" будет иметь хэш-код, отличный от хэш-кода строки "корзина", поэтому строки "пикник" и "корзина" будут находиться в разных контейнерах. В то же время строки "приказ" и "каприз" будут иметь одинаковый хэш-код и будут находиться в одном контейнере.

Классы `Dictionary<T>` и `ConcurrentDictionary<T>` имеют ту же функциональность, что и класс `Hashtable`. Объект `Dictionary<T>` конкретного типа (отличного от `Object`) обеспечивает лучшую производительность, чем `Hashtable` для типов значений. Это происходит потому, что элементы `Hashtable` относятся к типу `Object`, поэтому при сохранении или извлечении типа значения происходит упаковка или распаковка. Класс `ConcurrentDictionary<T>` следует использовать в случае, когда к коллекции могут обращаться несколько потоков одновременно.

## <a name="see-also"></a>См. также

[Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)

[IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[Dictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2)

[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)

[Часто используемые типы коллекций](commonly-used-collection-types.md)


