---
title: Массивы
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
ms.openlocfilehash: d4a1f379a88231654c710b1df7b505316377c915
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741802"
---
# <a name="arrays"></a>Массивы
✔️ предпочитаете использовать коллекции через массивы в общедоступных API. Раздел [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) содержит сведения о выборе между коллекциями и массивами.

 ❌ не использовать поля массива, доступного только для чтения. Само поле доступно только для чтения и не может быть изменено, но элементы массива могут быть изменены.

 ✔️ Рассмотрите возможность использования немассивных массивов вместо многомерных массивов.

 Массив массива — это массив с элементами, которые также являются массивами. Массивы, составляющие элементы, могут иметь разные размеры, что приводит к уменьшению объема незанятого пространства для некоторых наборов данных (например, разреженной матрицы) по сравнению с многомерными массивами. Более того, среда CLR оптимизирует операции с индексами на массивах массива, чтобы они могли улучшить производительность во время выполнения в некоторых сценариях.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также раздел

- <xref:System.Array>
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
