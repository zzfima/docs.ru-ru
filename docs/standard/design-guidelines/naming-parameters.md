---
title: Именование параметров
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: 0bb67056bb39b6a5f372191a1d0b0bb0dc1fe4d1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709183"
---
# <a name="naming-parameters"></a>Именование параметров
Помимо очевидной причины удобочитаемости, важно следовать рекомендациям по именам параметров, так как параметры отображаются в документации и в конструкторе, когда визуальные средства проектирования предоставляют функции IntelliSense и просмотра классов.  
  
 **✓ DO** использовать camelCasing в именах параметров.  
  
 **✓ DO** использовать описательные имена параметров.  
  
 **✓ CONSIDER** с помощью имен, основываясь на назначение параметра, а не тип параметра.  
  
### <a name="naming-operator-overload-parameters"></a>Именование параметров перегрузки оператора  
 **✓ DO** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.  
  
 **✓ DO** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.  
  
 **✓ CONSIDER** значимые имена для оператора перегружать параметров, если это добавляет особого значения.  
  
 **X DO NOT** использования сокращений и числовые индексы для оператора перегрузки имена параметров.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
