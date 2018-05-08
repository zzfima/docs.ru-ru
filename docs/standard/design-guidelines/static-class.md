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
ms.openlocfilehash: 92152600d317c04e3fef26400b11e94a549fde4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="static-class-design"></a>Разработка статичных классов
Статический класс был определен как класс, который содержит только статические члены (Разумеется, помимо экземпляр члены, унаследованные от <xref:System.Object?displayProperty=nameWithType> и возможно закрытый конструктор). Некоторые языки предоставляют встроенную поддержку для статических классов. В C# 2.0 и более поздних версиях при объявлении класса статический Это запечатанный, абстрактный и нет членов экземпляра может быть переопределено или объявлен.  
  
 Статические классы — это компромисс между чисто объектно ориентированный проект и простота. Они часто используются для предоставления ярлыки для других операций (таких как <xref:System.IO.File?displayProperty=nameWithType>), владельцы методы расширения, или функции, для которой полное объектно ориентированную оболочку несанкционированному (такие как <xref:System.Environment?displayProperty=nameWithType>).  
  
 **✓ СДЕЛАТЬ** статические классы предназначены для использования только в случае необходимости.  
  
 Статические классы должны использоваться только в качестве вспомогательных классов для объектно-ориентированной платформы.  
  
 **X не** используйте статические классы как всевозможных объектов.  
  
 **X не** объявления или переопределять члены экземпляра в статических классах.  
  
 **✓ СДЕЛАТЬ** объявить как запечатанный, абстрактный статических классов и добавьте конструктор закрытого экземпляра, если язык программирования не предусмотрена встроенная поддержка статических классов.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по разработке типов](../../../docs/standard/design-guidelines/type.md)  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
