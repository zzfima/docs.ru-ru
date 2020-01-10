---
title: Преобразование типов .NET Framework в строки
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711081"
---
# <a name="converting-net-framework-types-to-strings"></a>Преобразование типов .NET Framework в строки
Чтобы преобразовать тип .NET Framework в строку, используйте метод **ToString**. Метод **ToString** возвращает символьное представление переданного типа. В следующей таблице приведен список типов платформы .NET Framework, которые возвращают строку в формате, сопоставленном со спецификациями XSD.  
  
|Тип платформы .NET Framework|Возвращаемое строковое значение|  
|-------------------------|--------------------------|  
|Логическое значение .|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Используется формат гггг-ММ-ддТЧЧ:мм:ссzzzzzz и его подмножества.|  
|TimeSpan|Используется формат PnYnMnTnHnMnS. Например, значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.|  
  
## <a name="see-also"></a>См. также:

- [Преобразование типов XML-данных](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [Преобразование строк в типы данных .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
