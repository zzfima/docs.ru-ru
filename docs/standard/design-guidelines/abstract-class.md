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
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709599"
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов
**X DO NOT** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.  
  
 Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры типа. Поскольку нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неверно спроектирован и ошибочно ведет себя для пользователей.  
  
 **✓ DO** Определите защищенный или внутренний конструктор в абстрактных классах.  
  
 Защищенный конструктор является более распространенным и просто позволяет базовому классу выполнять собственную инициализацию при создании подтипов.  
  
 Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.  
  
 **✓ DO** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.  
  
 Это помогает проверить структуру абстрактного класса. Например, <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией абстрактного класса <xref:System.IO.Stream?displayProperty=nameWithType>.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
