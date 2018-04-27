---
title: Незапечатанные классы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c798c3cc93f08b77be7d0a5e0d1232d5598aed6b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="unsealed-classes"></a>Незапечатанные классы
Невозможно наследовать запечатанные классы и не позволяют расширяемости. В противоположность этому классы, которые могут наследоваться от называются незапечатанных классов.  
  
 **✓ Попробуйте** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.  
  
 Разработчики часто требуется наследовать от незапечатанных классов таким образом, чтобы добавить членов удобства, например пользовательских конструкторов, новые методы или перегруженных версий метода. Например `System.Messaging.MessageQueue` не запечатан, и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для определенной очереди путь или добавить пользовательские методы, которые упрощают API для конкретных сценариев.  
  
 Являются незапечатанных классов по умолчанию в большей части языков программирования, а кроме того, это рекомендуемое значение по умолчанию для большинства классов платформы. Расширяемость, обеспечиваемая незапечатанных типов намного пользователями framework с благодарностью довольно легко создать из-за сравнительно мало тестов затраты, связанные с незапечатанные типы.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)
