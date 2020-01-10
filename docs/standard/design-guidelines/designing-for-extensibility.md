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
ms.openlocfilehash: cd5db2d1e299df1b3d0f706ebc507e6855b72505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709469"
---
# <a name="designing-for-extensibility"></a>Разработка с обеспечением расширяемости
Одним из важных аспектов разработки платформы является обеспечение тщательного рассмотрения расширяемости платформы. Для этого необходимо понимать затраты и преимущества, связанные с различными механизмами расширения. Эта глава поможет вам решить, какие механизмы расширения (подклассы, события, виртуальные члены, обратные вызовы и т. д.) лучше удовлетворять требованиям вашей инфраструктуры.  
  
 Существует множество способов разрешить расширяемость в платформах. Они находятся в диапазоне от менее мощных, но менее дорогостоящих к очень мощным, но дорогостоящим. Для любого конкретного требования к расширяемости следует выбрать наиболее дорогостоящий механизм расширяемости, соответствующий требованиям. Помните, что обычно можно добавить дополнительную расширяемость, но вы никогда не сможете отказаться от внесения критических изменений.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Незапечатанные классы](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Защищенные члены](../../../docs/standard/design-guidelines/protected-members.md)  
 [События и обратные вызовы](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Виртуальные члены](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Абстракции (абстрактные типы и интерфейсы)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
