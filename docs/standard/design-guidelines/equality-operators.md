---
title: Операторы равенства
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 31a5ce18f4526b5e3b8411365dff812601de87ad
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709443"
---
# <a name="equality-operators"></a>Операторы равенства
В этом разделе обсуждаются перегрузки операторов равенства и ссылки на `operator==` и `operator!=` в качестве операторов равенства.  
  
 **X DO NOT** перегружать операторы равенства и недоступны в другом.  
  
 **✓ DO** убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства точно совпадает с семантикой и сходными характеристиками производительности.  
  
 Это часто означает, что `Object.Equals` необходимо переопределить при перегрузке операторов равенства.  
  
 **X AVOID** создание исключений из операторов равенства.  
  
 Например, возвращается значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Операторы равенства для типов значений  
 **✓ DO** перегружать операторы равенства для типов значений, если равенство является значимым.  
  
 В большинстве языков программирования отсутствует стандартная реализация `operator==` для типов значений.  
  
## <a name="equality-operators-on-reference-types"></a>Операторы равенства в ссылочных типах  
 **X AVOID** перегрузка операторов равенства на изменяемые ссылочные типы.  
  
 Многие языки имеют встроенные операторы равенства для ссылочных типов. Встроенные операторы обычно реализуют равенство ссылок, и многие разработчики удивлены, когда поведение по умолчанию изменяется на равенство значений.  
  
 Эта проблема устранена для неизменяемых ссылочных типов, поскольку неизменность значительно затрудняет заметную разницу между равенством ссылок и равенством значений.  
  
 **X AVOID** перегрузка операторов равенства для ссылочных типов, если реализация будет значительно медленнее, чем, равенство ссылок.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
