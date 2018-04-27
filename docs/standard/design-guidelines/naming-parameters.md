---
title: Именование параметров
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3e5dfe35fd4f2939898acee44764535c6de5fe9e
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="naming-parameters"></a>Именование параметров
Помимо очевидной причине удобочитаемость необходимо придерживаться следующих правил имена параметров, поскольку параметры отображаются в документации и в конструкторе при средства визуального проектирования предоставляют Intellisense и функции просмотра классов.  
  
 **✓ СДЕЛАТЬ** использовать camelCasing в именах параметров.  
  
 **✓ СДЕЛАТЬ** использовать описательные имена параметров.  
  
 **✓ Попробуйте** с помощью имен, основываясь на назначение параметра, а не тип параметра.  
  
### <a name="naming-operator-overload-parameters"></a>Именование параметров перегрузки оператора  
 **СДЕЛАТЬ ✓** использовать `left` и `right` для имен параметров перегрузку бинарного оператора, если нет никакого значения для параметров.  
  
 **СДЕЛАТЬ ✓** использовать `value` унарный оператор перегрузка для имен параметров при наличии не значения для параметров.  
  
 **✓ Попробуйте** значимые имена для оператора перегружать параметров, если это добавляет особого значения.  
  
 **X не** использования сокращений и числовые индексы для оператора перегрузки имена параметров.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
