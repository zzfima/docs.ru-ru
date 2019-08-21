---
title: Память и диапазоны
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd091c821f59febfc8c7a203334454e7b59c12
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666420"
---
# <a name="memory--and-span-related-types"></a>Типы, связанные с памятью и диапазонами

Начиная с .NET Core 2.1, .NET включает ряд взаимосвязанных типов, представляющих непрерывную область строго типизированной произвольной памяти. Сюда входит следующее.

- <xref:System.Span%601?displayProperty=nameWithType> — тип, используемый для доступа к непрерывной области памяти. В основе экземпляра <xref:System.Span%601> может быть массив типа `T`, <xref:System.String>, буфер, выделенный с помощью [stackalloc](../../csharp/language-reference/operators/stackalloc.md), или указатель на неуправляемую память. Так как выделение выполняется в стеке, существует ряд ограничений. Например, поле в классе не может иметь тип <xref:System.Span%601>, а диапазон нельзя использовать в асинхронных операциях.

- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Span%601>.

- <xref:System.Memory%601?displayProperty=nameWithType> — непрерывная область памяти, которая выделяется в управляемой куче, а не стеке. В основе экземпляра <xref:System.Memory%601> может быть массив объектов типа `T` или <xref:System.String>. Так как он может храниться в управляемой куче, <xref:System.Memory%601> не имеет ограничений, применимых к <xref:System.Span%601>.

- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Memory%601>.

- <xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType> — выделяет строго типизированные блоки памяти из пула памяти для владельца. Экземпляры <xref:System.Buffers.IMemoryOwner%601> можно арендовать из пула путем вызова <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>, и освобождать в пул путем вызова <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.

- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> — представляет владельца блока памяти и управляет временем ее существования.

- <xref:System.Buffers.MemoryManager%601> — абстрактный базовый класс, используемый для замены реализации <xref:System.Memory%601>, чтобы включить для <xref:System.Memory%601> поддержку дополнительных типов, включая безопасные дескрипторы. <xref:System.Buffers.MemoryManager%601> — используется только в сложных сценариях.

- <xref:System.ArraySegment%601> — программа-оболочка для определенного числа элементов массива, начиная с определенного индекса.

- <xref:System.MemoryExtensions?displayProperty=nameWithType> — коллекция методов расширения для преобразования строк, массивов и фрагментов массивов для блоков <xref:System.Memory%601>.

> [!NOTE]
> Для более ранних платформ <xref:System.Span%601> и <xref:System.Memory%601> доступны в [пакете System.Memory NuGet](https://www.nuget.org/packages/System.Memory/).

Дополнительные сведения см. в описании пространства имен <xref:System.Buffers?displayProperty=nameWithType>.

## <a name="working-with-memory-and-span"></a>Использование памяти и диапазонов

Так как типы, связанные с памятью и диапазонами, обычно используются для хранения данных в конвейере обработки, очень важно, чтобы разработчики следовали набору рекомендаций при использовании <xref:System.Span%601>, <xref:System.Memory%601> и связанных типов. Эти рекомендации описаны в руководствах по использованию структур [Memory\<T> и Span\<T>](memory-t-usage-guidelines.md).

## <a name="see-also"></a>См. также

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
