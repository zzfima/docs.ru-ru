---
title: Защищенные члены
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: 44d342662e1aaeb51f14470f354f2dadd9a6f18d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743642"
---
# <a name="protected-members"></a>Защищенные члены
Защищенные члены сами по себе не предоставляют расширяемости, но они могут обеспечивать расширяемость с помощью подкласса. Они могут использоваться для предоставления расширенных возможностей настройки без необходимости усложнения основного общедоступного интерфейса.

 Разработчикам платформ необходимо соблюдать осторожность при использовании защищенных членов, поскольку имя "Protected" может дать ложный смысл безопасности. Любой пользователь может создать подкласс для незапечатанного класса и доступа к защищенным членам, поэтому все те же методы кодирования, используемые для открытых членов, применяются к защищенным членам.

 ✔️ РЕКОМЕНДУЕТСЯ использовать защищенные элементы для расширенной настройки.

 ✔️ рассматривать защищенные члены в незапечатанных классах как открытые в целях безопасности, документации и анализа совместимости.

 Любой пользователь может наследовать от класса и получить доступ к защищенным членам.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
