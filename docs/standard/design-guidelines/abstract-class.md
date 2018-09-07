---
title: Разработка абстрактных классов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b9dacc4995a126e1ee3f6062dca796194d4882
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44059671"
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов
**X DO NOT** определение открытого или защищенного внутреннего конструкторов в абстрактных типов.  
  
 Конструкторы должны быть открытым, только в том случае, если пользователи должны будут создавать экземпляры типа. Так как нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неправильно спроектированных и вводит в заблуждение пользователей.  
  
 **✓ DO** Определите защищенный или внутренний конструктор в абстрактных классах.  
  
 Защищенный конструктор чаще и просто позволяет базового класса, чтобы сделать свой собственный инициализации при создании подтипов.  
  
 Внутренний конструктор можно использовать для ограничения конкретные реализации абстрактного класса для сборки, определяющей класс.  
  
 **✓ DO** укажите по крайней мере один конкретный тип, наследующий от каждого абстрактный класс, который можно отправить.  
  
 Это помогает проверить архитектуру абстрактного класса. Например <xref:System.IO.FileStream?displayProperty=nameWithType> представляет собой реализацию <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)  
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
