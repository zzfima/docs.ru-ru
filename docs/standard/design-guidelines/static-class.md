---
title: Разработка статичных классов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972050"
---
# <a name="static-class-design"></a>Разработка статичных классов
Статический класс представляет собой класс, который содержит только статические члены (Конечно, помимо экземпляр членам, унаследованным от <xref:System.Object?displayProperty=nameWithType> и возможно закрытый конструктор). Некоторые языки предоставляют встроенную поддержку для статических классов. В C# 2.0 и более поздних версий когда класс объявлен как статический, это запечатанный, абстрактный, и нет членов экземпляров можно переопределить или объявлен.  
  
 Статические классы — это компромисс между чисто объектно ориентированного проектирования и простотой. Они часто используются для предоставления ярлыки для других операций (таких как <xref:System.IO.File?displayProperty=nameWithType>), владельцы методы расширения, или функции, для которой полное объектно ориентированную оболочку несанкционированному (такие как <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ DO** статические классы предназначены для использования только в случае необходимости.  
  
 Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированной платформы.  
  
 **X DO NOT** используйте статические классы как всевозможных объектов.  
  
 **X DO NOT** объявления или переопределять члены экземпляра в статических классах.  
  
 **✓ DO** объявить как запечатанный, абстрактный статических классов и добавьте конструктор закрытого экземпляра, если язык программирования не предусмотрена встроенная поддержка статических классов.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)  
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
