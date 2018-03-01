---
title: "Преобразование типов .NET Framework в строки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6ca134e13593fdacd759b0000e0e159f76ea067f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="converting-net-framework-types-to-strings"></a>Преобразование типов .NET Framework в строки
Чтобы преобразовать тип .NET Framework в строку, используйте метод **ToString**. Метод **ToString** возвращает символьное представление переданного типа. В следующей таблице приведен список типов платформы .NET Framework, которые возвращают строку в формате, сопоставленном со спецификациями XSD.  
  
|Тип платформы .NET Framework|Возвращаемое строковое значение|  
|-------------------------|--------------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Используется формат гггг-ММ-ддТЧЧ:мм:ссzzzzzz и его подмножества.|  
|TimeSpan|Используется формат PnYnMnTnHnMnS. Например, значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.|  
  
## <a name="see-also"></a>См. также  
 [Преобразование типов XML-данных](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Преобразование строк в типы данных .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
