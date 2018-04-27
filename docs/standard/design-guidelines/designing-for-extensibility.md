---
title: Разработка с обеспечением расширяемости
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b643c33a1418839c8aabf06d681083232e61553a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="designing-for-extensibility"></a>Разработка с обеспечением расширяемости
Проектирование платформу одним важным аспектом является обеспечение внимательно изучить расширяемость такой платформы. Это требует понимания издержки и прибыль, связанные с различные механизмы расширения. В этой главе помогут решить, какой из механизмов расширения — создания подкласса событий, виртуальные члены, обратные вызовы и т. д, соответствуют требованиям вашей платформы.  
  
 Существует множество способов, чтобы разрешить расширяемости платформы. Они в диапазоне от менее мощные, но менее затратным до очень мощные, но дорого. Для любого заданного расширяемости требования следует выбирать бы дорогостоящих механизм расширяемости, соответствующий требованиям. Имейте в виду, что обычно можно позднее добавить дополнительные расширения, но никогда не позволит немедленно без критических изменений.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Незапечатанные классы](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Защищенные члены](../../../docs/standard/design-guidelines/protected-members.md)  
 [События и обратные вызовы](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Виртуальные члены](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Абстракции (абстрактные типы и интерфейсы)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
