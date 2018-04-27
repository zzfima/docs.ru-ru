---
title: Операторы равенства
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cd740e9b7a5d38229b3564bfeca003fc4d189624
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="equality-operators"></a>Операторы равенства
В этом разделе обсуждаются перегрузка операторов равенства и ссылается на `operator==` и `operator!=` как операторы равенства.  
  
 **X не** перегружать операторы равенства и недоступны в другом.  
  
 **СДЕЛАТЬ ✓** убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства точно совпадает с семантикой и сходными характеристиками производительности.  
  
 Это часто означает, что `Object.Equals` должен переопределяться перегруженного операторов равенства.  
  
 **X ИЗБЕГАЙТЕ** создание исключений из операторов равенства.  
  
 Например, возвращают значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Операторы равенства для типов значений  
 **✓ СДЕЛАТЬ** перегружать операторы равенства для типов значений, если равенство является значимым.  
  
 В большинстве языков программирования, отсутствует реализация по умолчанию из `operator==` для типов значений.  
  
## <a name="equality-operators-on-reference-types"></a>Операторы равенства для ссылочных типов  
 **X ИЗБЕГАЙТЕ** перегрузка операторов равенства на изменяемые ссылочные типы.  
  
 Многие языки имеют операторы встроенных равенства для ссылочных типов. Встроенных операторов, обычно реализуют равенство ссылок и многие разработчики удивлен, когда поведение по умолчанию изменяется на равенство значений.  
  
 Эта проблема устраняется для неизменяемого ссылочных типов так, как неизменность затруднит Обратите внимание на различие между ссылочным равенством и равенство значений.  
  
 **X ИЗБЕГАЙТЕ** перегрузка операторов равенства для ссылочных типов, если реализация будет значительно медленнее, чем, равенство ссылок.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
