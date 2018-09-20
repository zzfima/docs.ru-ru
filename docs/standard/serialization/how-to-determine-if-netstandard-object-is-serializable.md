---
title: Как определить, если сериализуется объект .NET Standard
description: Показано, как определить, может ли быть сериализован типом .NET Standard во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46324598"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Как определить, если сериализуется объект .NET Standard

.NET Standard — это спецификация, определяющая типы и члены, которые должны присутствовать на конкретных реализаций .NET, которые соответствуют этой версии стандарта. Тем не менее .NET Standard не определяет ли тип является сериализуемым. Типы, определенные в библиотеку .NET Standard не отмечены <xref:System.SerializableAttribute> атрибута. Вместо этого конкретных реализаций .NET, например .NET Framework и .NET Core, могут определять, является ли определенный тип сериализуемым. 

Если вы разработали библиотеку, ориентированном на .NET Standard, библиотека может использоваться любой реализации .NET, которая поддерживает .NET Standard. Это означает, что невозможно заранее известно ли определенный тип является сериализуемым; только необходимо выяснить, является ли сериализуемые во время выполнения.

Можно определить, является ли объект сериализуемые во время выполнения, получая значение <xref:System.Type.IsSerializable> свойство <xref:System.Type> , представляющий тип этого объекта. Следующий пример предоставляет одну реализацию. Он определяет `IsSerializable(Object)` метод расширения, который указывает ли какая-либо <xref:System.Object> экземпляр может быть сериализован.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Затем можно передать любой объект в метод, чтобы определить, является ли его можно сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>См. также

- [Двоичная сериализация](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
