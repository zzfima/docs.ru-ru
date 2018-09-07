---
title: Именование параметров
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e6a8a1dcdcb8fa3311b040c72987f0f76e681fc
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086476"
---
# <a name="naming-parameters"></a>Именование параметров
Помимо очевидная причина восприятия очень важно следовать рекомендациям для имен параметров, так как параметры отображаются в документации и в конструкторе, когда средства визуального проектирования предоставляют Intellisense и функции просмотра классов.  
  
 **✓ DO** использовать camelCasing в именах параметров.  
  
 **✓ DO** использовать описательные имена параметров.  
  
 **✓ CONSIDER** с помощью имен, основываясь на назначение параметра, а не тип параметра.  
  
### <a name="naming-operator-overload-parameters"></a>Именование параметров перегрузки оператора  
 **✓ DO** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.  
  
 **✓ DO** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.  
  
 **✓ CONSIDER** значимые имена для оператора перегружать параметров, если это добавляет особого значения.  
  
 **X DO NOT** использования сокращений и числовые индексы для оператора перегрузки имена параметров.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
