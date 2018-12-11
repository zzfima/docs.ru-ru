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
author: KrzysztofCwalina
ms.openlocfilehash: 1982c7c97802dedd1d49c770be5a7ac00944cbfc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130925"
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
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)  
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
