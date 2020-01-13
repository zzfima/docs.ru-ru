---
title: Типы коллекций Hashtable и Dictionary
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
ms.openlocfilehash: a6f234b6205fd30507b9342d9839db6adcddfc2e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711380"
---
# <a name="hashtable-and-dictionary-collection-types"></a>Типы коллекций Hashtable и Dictionary
Класс <xref:System.Collections.Hashtable?displayProperty=nameWithType> и универсальные классы <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> реализуют интерфейс <xref:System.Collections.IDictionary?displayProperty=nameWithType>. Универсальный класс <xref:System.Collections.Generic.Dictionary%602> также реализует универсальный интерфейс <xref:System.Collections.Generic.IDictionary%602>. Таким образом, каждый элемент в этих коллекциях является парой "ключ-значение".  
  
 Объект <xref:System.Collections.Hashtable> состоит из контейнеров, содержащих элементы коллекции. Контейнер — это виртуальная подгруппа элементов внутри объекта <xref:System.Collections.Hashtable>, которая обеспечивает более простой и быстрый поиск и извлечение, чем в большинстве коллекций. Каждый контейнер связан с хэш-кодом, который создается с помощью хэш-функции и основан на ключе элемента.  
  
 Универсальный класс <xref:System.Collections.Generic.HashSet%601> — это неупорядоченная коллекция для хранения уникальных элементов.  
  
 Хэш-функция — это алгоритм, возвращающий числовой хэш-код на основе ключа. Ключом является значение какого-либо свойства хранимого объекта. Хэш-функция должна всегда возвращать один и тот же хэш-код для определенного ключа. Возможна ситуация, когда хэш-функция создает один хэш-код для разных ключей. Однако хэш-функция, создающая уникальный хэш-код для каждого уникального ключа, обеспечивает лучшую производительность при извлечении элементов из хэш-таблицы.  
  
 Каждый объект, который используется в качестве элемента в <xref:System.Collections.Hashtable>, должен иметь возможность создать свой хэш-код, используя реализацию метода <xref:System.Object.GetHashCode%2A>. Однако хэш-функцию также можно указать для всех элементов в <xref:System.Collections.Hashtable>, используя конструктор <xref:System.Collections.Hashtable>, принимающий реализацию <xref:System.Collections.IHashCodeProvider> в качестве одного из своих параметров.  
  
 Когда объект добавляется в <xref:System.Collections.Hashtable>, он сохраняется в контейнере, который связан с хэш-кодом, соответствующим хэш-коду объекта. При поиске значения в <xref:System.Collections.Hashtable> создается хэш-код для этого значения, и поиск осуществляется в контейнере, связанном с этим хэш-кодом.  
  
 Например, хэш-функция для строки может принимать коды ASCII каждого символа в строке и объединять их для создания хэш-кода. Строка "пикник" будет иметь хэш-код, отличный от хэш-кода строки "корзина", поэтому строки "пикник" и "корзина" будут находиться в разных контейнерах. В то же время строки "приказ" и "каприз" будут иметь одинаковый хэш-код и будут находиться в одном контейнере.  
  
 Классы <xref:System.Collections.Generic.Dictionary%602> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602> имеют ту же функциональность, что и класс <xref:System.Collections.Hashtable>. Объект <xref:System.Collections.Generic.Dictionary%602> конкретного типа (отличного от <xref:System.Object>) обеспечивает лучшую производительность, чем <xref:System.Collections.Hashtable> для типов значений. Это происходит потому, что элементы <xref:System.Collections.Hashtable> относятся к типу <xref:System.Object>, поэтому при сохранении или извлечении типа значения происходит упаковка или распаковка. Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> следует использовать в случае, когда к коллекции могут обращаться несколько потоков одновременно.  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IDictionary>
- <xref:System.Collections.IHashCodeProvider>
- <xref:System.Collections.Generic.Dictionary%602>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>
- [Часто используемые типы коллекций](../../../docs/standard/collections/commonly-used-collection-types.md)
