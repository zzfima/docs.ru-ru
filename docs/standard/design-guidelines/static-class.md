---
title: Разработка статичных классов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709066"
---
# <a name="static-class-design"></a>Разработка статичных классов
Статический класс определяется как класс, который содержит только статические члены (конечно же, помимо членов экземпляра, наследуемых от <xref:System.Object?displayProperty=nameWithType> и, возможно, закрытого конструктора). Некоторые языки предоставляют встроенную поддержку статических классов. В C# 2,0 и более поздних версиях, когда класс объявлен как статический, он запечатан, является абстрактным, а члены экземпляра не могут быть переопределены или объявлены.  
  
 Статические классы являются компромиссом между чисто объектно-ориентированной архитектурой и простотой. Они обычно используются для предоставления сочетаний клавиш для других операций (например, <xref:System.IO.File?displayProperty=nameWithType>), владельцев методов расширения или функциональных возможностей, для которых полная объектно-ориентированная оболочка не гарантируется (например, <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** статические классы предназначены для использования только в случае необходимости.  
  
 Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированного ядра платформы.  
  
 **X DO NOT** используйте статические классы как всевозможных объектов.  
  
 **X DO NOT** объявления или переопределять члены экземпляра в статических классах.  
  
 **✓ DO** объявить как запечатанный, абстрактный статических классов и добавьте конструктор закрытого экземпляра, если язык программирования не предусмотрена встроенная поддержка статических классов.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
