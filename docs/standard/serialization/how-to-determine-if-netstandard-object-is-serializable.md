---
title: Как определить, является ли объект .NET Standard сериализуемым
description: Показывает, как определить, можно ли сериализовать тип .NET Standard во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159901"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Как определить, является ли объект .NET Standard сериализуемым

.NET Standard — это спецификация, определяющая типы и члены, которые должны присутствовать в конкретных реализациях .NET, соответствующих этой версии стандарта. Однако .NET Standard не определяет, является ли тип сериализуемым. Типы, определенные в библиотеке .NET Standard, не помечены атрибутом <xref:System.SerializableAttribute>. Вместо этого определенные реализации .NET, такие как .NET Framework и .NET Core, могут быть свободны, чтобы определить, является ли конкретный тип сериализуемым.

Если вы разработали библиотеку, предназначенную для .NET Standard, ваша библиотека может использоваться любой реализацией .NET, поддерживающей .NET Standard. Это означает, что невозможно заранее определить, является ли конкретный тип сериализуемым. можно определить, является ли он сериализуемым во время выполнения.

Можно определить, является ли объект сериализуемым во время выполнения, извлекая значение свойства <xref:System.Type.IsSerializable> объекта <xref:System.Type>, который представляет тип этого объекта. В следующем примере показана одна реализация. Он определяет метод расширения `IsSerializable(Object)`, который указывает, можно ли сериализовать любой экземпляр <xref:System.Object>.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Затем можно передать любой объект в метод, чтобы определить, может ли он быть сериализован и десериализован в текущей реализации .NET, как показано в следующем примере:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>См. также раздел

- [Двоичная сериализация](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
