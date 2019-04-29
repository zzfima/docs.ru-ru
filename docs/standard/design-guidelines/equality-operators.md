---
title: Операторы равенства
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960340"
---
# <a name="equality-operators"></a>Операторы равенства
В этом разделе обсуждаются перегрузка операторов равенства и ссылается на `operator==` и `operator!=` как операторы равенства.  
  
 **X DO NOT** перегружать операторы равенства и недоступны в другом.  
  
 **✓ DO** убедитесь, что <xref:System.Object.Equals%2A?displayProperty=nameWithType> и операторы равенства точно совпадает с семантикой и сходными характеристиками производительности.  
  
 Это часто означает, что `Object.Equals` должен быть переопределен, если операторы равенства являются перегруженными.  
  
 **X AVOID** создание исключений из операторов равенства.  
  
 Например, возвращают значение false, если один из аргументов имеет значение null, а не вызывает `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Операторы равенства для типов значений  
 **✓ DO** перегружать операторы равенства для типов значений, если равенство является значимым.  
  
 В большинстве языков программирования, имеется реализация по умолчанию не `operator==` для типов значений.  
  
## <a name="equality-operators-on-reference-types"></a>Операторы равенства для ссылочных типов  
 **X AVOID** перегрузка операторов равенства на изменяемые ссылочные типы.  
  
 Во многих языках применяются операторы встроенные равенства для ссылочных типов. Встроенные операторы обычно реализуют равенство ссылок и многие разработчики удивлен, когда поведение по умолчанию изменяется на равенство значений.  
  
 Эта проблема уменьшается для неизменяемого ссылочных типов, поскольку неизменность затруднит Обратите внимание на различие между ссылочным равенством и равенства значений.  
  
 **X AVOID** перегрузка операторов равенства для ссылочных типов, если реализация будет значительно медленнее, чем, равенство ссылок.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила использования](../../../docs/standard/design-guidelines/usage-guidelines.md)
