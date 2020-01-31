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
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741703"
---
# <a name="equality-operators"></a>Операторы равенства
В этом разделе обсуждаются перегрузки операторов равенства и ссылки на `operator==` и `operator!=` в качестве операторов равенства.

 ❌ не перегружать один из операторов равенства, а не другой.

 ✔️ Убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства имеют точно такую же семантику и аналогичные характеристики производительности.

 Это часто означает, что `Object.Equals` необходимо переопределить при перегрузке операторов равенства.

 ❌ избежать возникновения исключений из операторов равенства.

 Например, возвращается значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.

## <a name="equality-operators-on-value-types"></a>Операторы равенства для типов значений
 ✔️ ВЫПОЛНИТЬ перегрузку операторов равенства для типов значений, если равенство является осмысленным.

 В большинстве языков программирования отсутствует стандартная реализация `operator==` для типов значений.

## <a name="equality-operators-on-reference-types"></a>Операторы равенства в ссылочных типах
 ❌ избежать перегрузки операторов равенства для изменяемых ссылочных типов.

 Многие языки имеют встроенные операторы равенства для ссылочных типов. Встроенные операторы обычно реализуют равенство ссылок, и многие разработчики удивлены, когда поведение по умолчанию изменяется на равенство значений.

 Эта проблема устранена для неизменяемых ссылочных типов, поскольку неизменность значительно затрудняет заметную разницу между равенством ссылок и равенством значений.

 ❌ избежать перегрузки операторов равенства в ссылочных типах, если реализация будет значительно медленнее, чем равенство ссылок.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
