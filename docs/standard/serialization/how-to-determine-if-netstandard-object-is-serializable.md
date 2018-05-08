---
title: 'Как: определить, является ли сериализуемый объект .NET Standard'
description: Показано, как определить, можно ли сериализовать .NET стандартного типа во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 247eed2e7091930c6bcfaa524296b45350dd6510
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Как: определить, является ли сериализуемый объект .NET Standard

В стандарте .NET является спецификация, определяющая типы и члены, которые должны присутствовать на определенных реализаций .NET, которые соответствуют этой версии стандарта. Однако .NET Standard не определяет ли тип является сериализуемым. Типы, определенные в стандартной библиотеке .NET не отмечены ни <xref:System.SerializableAttribute> атрибута. Вместо этого определенных реализаций .NET, такие как .NET Framework и .NET Core, могут определить, является ли определенный тип сериализуемым. 

Если вы разработали библиотеку, ориентированном .NET Standard, библиотеки могут использоваться реализацией .NET, которая поддерживает .NET Standard. Это означает, что вы не может заранее знаете ли определенный тип является сериализуемым; может только определить, является ли он поддерживает сериализацию во время выполнения.

Можно определить, является ли объект сериализуемые во время выполнения, получая значение <xref:System.Type.IsSerializable> свойство <xref:System.Type> , представляющий тип этого объекта. Следующий пример предоставляет одну реализацию. Он определяет `IsSerializable(Object)` метод расширения, который указывает ли какая-либо <xref:System.Object> экземпляр может быть сериализован.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Затем можно передать любой объект в метод, чтобы определить ли его можно сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>См. также

[Двоичная сериализация](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
