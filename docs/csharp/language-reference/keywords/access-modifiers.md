---
title: Справочник по C#. Модификаторы доступа
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
ms.openlocfilehash: 5568d79c4a13b7b0db5a46bb4ebb2168ea66a2c9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606098"
---
# <a name="access-modifiers-c-reference"></a>Модификаторы доступа (Справочник по C#)
Модификаторы доступа — это ключевые слова, которые задают объявленный уровень доступности члена или типа. В этом разделе описываются четыре модификатора доступа:  
  
- `public`
- `protected`
- `internal`
- `private`
  
 С помощью этих модификаторов можно задать следующие шесть уровней доступа:  
  
- [`public`](public.md): Неограниченный доступ.  
  
- [`protected`](protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса.  
  
- [`internal`](internal.md): Доступ ограничен текущей сборкой.  
  
- [`protected internal`](protected-internal.md): Доступ ограничен текущей сборкой или типами, которые являются производными от содержащего класса.  
  
- [`private`](private.md): Доступ ограничен содержащим типом.  

- [`private protected`](private-protected.md): Доступ ограничен содержащим классом или типами, которые являются производными от содержащего класса в текущей сборке.  
  
 В этом разделе также представлена следующая информация:  
  
- [Уровни доступности](./accessibility-levels.md). С помощью четырех модификаторов доступа можно объявить шесть уровней доступности.  
  
- [Домен доступности](./accessibility-domain.md). Определяет, в каких разделах программы может присутствовать ссылка на этот элемент.  
  
- [Ограничения на использование уровней доступности](./restrictions-on-using-accessibility-levels.md). Общие сведения об ограничениях на использование объявленных уровней доступности.  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md)
- [Ключевые слова доступа](./access-keywords.md)
- [Модификаторы](./modifiers.md)
