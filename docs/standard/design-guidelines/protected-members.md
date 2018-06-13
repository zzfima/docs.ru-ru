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
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571089"
---
# <a name="protected-members"></a>Защищенные члены
Защищенные члены сами по себе не имеют все расширения, но они могут сделать расширяемости через подклассы более широкими возможностями. Они могут использоваться для предоставления дополнительной настройки параметров без излишне усложнения основных открытого интерфейса.  
  
 Framework конструкторы, должны Будьте внимательны с защищенных членов, поскольку имя «защищен» может предоставить заблуждение безопасности. Любой пользователь может подкласс незапечатанного класса и доступ к защищенным членам, и таким образом те же защитного приемы программирования, используемый для открытых членов касаться защищенные члены.  
  
 **✓ Попробуйте** с помощью защищенные члены для расширенной настройки.  
  
 **✓ СДЕЛАТЬ** обрабатывать защищенные члены незапечатанных классов как открытые с целью анализа безопасности, документацию и совместимости.  
  
 Любой пользователь может наследовать от класса и обращаться к защищенным членам.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
