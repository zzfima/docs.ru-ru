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
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45990210"
---
# <a name="arrays"></a>Массивы
**✓ DO** способом с помощью коллекций на массивы в открытых интерфейсах API. [Коллекций](../../../docs/standard/design-guidelines/guidelines-for-collections.md) разделе содержатся сведения о выборе между коллекций и массивов.  
  
 **X DO NOT** использовать поля только для чтения массив. Само поле только для чтения и не может быть изменено, но можно изменить элементы в массиве.  
  
 **✓ CONSIDER** ступенчатые массивы вместо многомерных массивов.  
  
 Массив массивов — это массив, содержащий элементы, которые также являются массивами. Массивы, которые составляют элементы могут иметь различные размеры, что позволяет экономить пространство для некоторых наборов данных (например, разреженных матрицы), по сравнению с многомерных массивов. Кроме того среда CLR оптимизирует операции с индексами на массивы массивов, поэтому они могут достичь более высокой производительности среды выполнения, в некоторых сценариях.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- <xref:System.Array>  
- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
