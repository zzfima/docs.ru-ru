---
title: Защищенные члены
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199743"
---
# <a name="protected-members"></a>Защищенные члены
Защищенные члены сами по себе не предоставляют все расширения, но они могут сделать расширяемости через подклассы более мощные. Они могут использоваться для предоставления Дополнительные параметры настройки без усложнять основной открытый интерфейс.  
  
 Конструкторы Framework нужно очень осторожно защищенные члены, поскольку имя «защищен» можно предоставить ложное чувство защищенности. Любой пользователь может подкласс Незапечатанный класс и доступ к защищенным членам, и поэтому те же защитных приемы программирования, используемый для открытых членов применяются к защищенным членам.  
  
 **✓ CONSIDER** с помощью защищенные члены для расширенной настройки.  
  
 **✓ DO** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.  
  
 Любой пользователь может наследовать от класса и доступа к защищенным членам.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
