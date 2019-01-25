---
title: Именование параметров
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646624"
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
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
