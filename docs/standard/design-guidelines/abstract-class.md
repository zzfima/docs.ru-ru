---
title: Разработка абстрактных классов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 018dd353024e75e9819f5a97008f2f422ecad291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739055"
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов

❌ не определяйте открытые или защищенные внутренние конструкторы в абстрактных типах.

 Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры типа. Поскольку нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неверно спроектирован и ошибочно ведет себя для пользователей.

 ✔️ определить защищенный или внутренний конструктор в абстрактных классах.

 Защищенный конструктор является более распространенным и просто позволяет базовому классу выполнять собственную инициализацию при создании подтипов.

 Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.

 ✔️ предоставить по крайней мере один конкретный тип, наследующий от каждого передаваемого абстрактного класса.

 Это помогает проверить структуру абстрактного класса. Например, <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией абстрактного класса <xref:System.IO.Stream?displayProperty=nameWithType>.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
