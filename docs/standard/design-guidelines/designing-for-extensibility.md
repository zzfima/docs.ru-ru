---
title: Разработка с обеспечением расширяемости
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: KrzysztofCwalina
ms.openlocfilehash: 94900dee72230a1b9d099d78168acc508af62af7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026462"
---
# <a name="designing-for-extensibility"></a>Разработка с обеспечением расширяемости
Одним важным аспектом разработки платформа нужно убедиться, что тщательно рассматривается как расширяемость платформы. Для этого требуется, что вы понимаете, затраты и преимущества, связанные с различные механизмы расширяемости. В этой главе поможет вам решить, какой из механизмов расширения — создание подклассов, события, виртуальные члены, обратные вызовы и т. д. — лучше всего решать требования к платформе.  
  
 Существует много способов для расширения платформы. Они в диапазоне от менее мощных, но менее затратных до очень мощный, но дорого. Для любого заданного расширения требования следует выбирать бы дорогостоящим механизмом расширения, соответствующий требованиям. Имейте в виду, что обычно можно позже добавить более широкие возможности, но никогда не позволит немедленно без критических изменений.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Незапечатанные классы](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Защищенные члены](../../../docs/standard/design-guidelines/protected-members.md)  
 [События и обратные вызовы](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Виртуальные члены](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Абстракции (абстрактные типы и интерфейсы)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
