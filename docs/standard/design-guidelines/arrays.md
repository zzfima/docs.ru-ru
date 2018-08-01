---
title: Массивы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570409"
---
# <a name="arrays"></a>Массивы
**✓ DO** способом с помощью коллекций на массивы в открытых интерфейсах API. [Коллекций](../../../docs/standard/design-guidelines/guidelines-for-collections.md) разделе содержатся сведения о выборе между коллекциям и массивам.  
  
 **X DO NOT** использовать поля только для чтения массив. Поле доступно только для чтения и не может быть изменен, но можно изменить элементы в массиве.  
  
 **✓ CONSIDER** ступенчатые массивы вместо многомерных массивов.  
  
 Массив массивов — это массив с элементами, которые также являются массивами. Массивы, которые составляют элементы могут иметь различные размеры, что позволяет экономить пространство для некоторых наборов данных (например, Разреженные матрицы) по сравнению с многомерных массивов. Кроме того среда CLR оптимизирует операции с индексами на массивы массивов, поэтому они могут достичь высокой производительности среды выполнения, в некоторых сценариях.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array>  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
