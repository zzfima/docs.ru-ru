---
title: Устранение рисков. Проверка схемы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc0232e0187c795fe20e6a99d4a710ba6244e34e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599664"
---
# <a name="mitigation-xml-schema-validation"></a>Устранение рисков. Проверка схемы XML
В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] в ходе проверки XSD-схемы выявляется нарушение ограничения уникальности, если используется составной ключ и один ключ является пустым.  
  
## <a name="impact"></a>Последствия  
 Влияние этого изменения должно быть минимальным: в зависимости от спецификации схемы ожидается ошибка проверки схемы в случае нарушения ограничения `xsd:unique` при использовании составного ключа с пустым ключом.  
  
## <a name="mitigation"></a>Устранение рисков  
 Обнаружение ошибки проверки схемы при наличии одного пустого ключа в составном ключе — это настраиваемая функция.  
  
- Начиная с приложений, ориентированных на [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], функция обнаружения ошибок проверки схемы включена по умолчанию, однако ее можно отключить, чтобы не выполнять обнаружение ошибок проверки схемы.  
  
- В приложениях, выполняющихся в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], но ориентированных на [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] и более ранние версии платформы, обнаружение ошибок проверки схемы не выполняется по умолчанию, однако его можно включить, чтобы выполнять обнаружение ошибок проверки схемы.  
  
 Это поведение можно настроить, используя класс <xref:System.AppContext> для определения значения параметра `System.Xml.IgnoreEmptyKeySequences`. Так как значение параметра по умолчанию — `false` (пустые последовательности ключей не игнорируются), для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], можно отключить это поведение, используя следующий код для задания значения параметра `true`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Для приложений, предназначенных для [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] и более ранних версий, поскольку значение параметра по умолчанию — `true` (пустые последовательности ключей игнорируются), можно гарантировать, что составной ключ с пустым ключом будет создавать ошибку проверки схемы, используя следующий код для задания значения параметра `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
