---
title: Устранение рисков. Проверка схемы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 99cc1eae08697909d89e5c1e46cd604c7da543bc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457748"
---
# <a name="mitigation-xml-schema-validation"></a>Устранение рисков. Проверка схемы XML
В .NET Framework 4.6 в ходе проверки XSD-схемы выявляется нарушение ограничения уникальности, если используется составной ключ и один ключ является пустым.  
  
## <a name="impact"></a>Последствия  
 Влияние этого изменения должно быть минимальным: в зависимости от спецификации схемы ожидается ошибка проверки схемы в случае нарушения ограничения `xsd:unique` при использовании составного ключа с пустым ключом.  
  
## <a name="mitigation"></a>Устранение рисков  
 Обнаружение ошибки проверки схемы при наличии одного пустого ключа в составном ключе — это настраиваемая функция.  
  
- Начиная с приложений, ориентированных на .NET Framework 4.6, функция обнаружения ошибок проверки схемы включена по умолчанию, однако ее можно отключить, чтобы не выполнять обнаружение ошибок проверки схемы.  
  
- В приложениях, выполняющихся в .NET Framework 4.6, но ориентированных на .NET Framework 4.5.2 и более ранние версии платформы, обнаружение ошибок проверки схемы не выполняется по умолчанию, однако его можно включить, чтобы выполнять обнаружение ошибок проверки схемы.  
  
 Это поведение можно настроить, используя класс <xref:System.AppContext> для определения значения параметра `System.Xml.IgnoreEmptyKeySequences`. Так как значение параметра по умолчанию — `false` (пустые последовательности ключей не игнорируются), для приложений, предназначенных для .NET Framework 4.6, можно отключить это поведение, используя следующий код для задания значения параметра `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Для приложений, предназначенных для .NET Framework 4.5.2 и более ранних версий, поскольку значение параметра по умолчанию — `true` (пустые последовательности ключей игнорируются), можно гарантировать, что составной ключ с пустым ключом будет создавать ошибку проверки схемы, используя следующий код для задания значения параметра `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)
