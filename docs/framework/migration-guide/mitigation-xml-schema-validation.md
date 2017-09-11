---
title: "Устранение рисков. Проверка схемы XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 786e2d0d70aaead6d464d262ca43dade8db64a52
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="4f240-102">Устранение рисков. Проверка схемы XML</span><span class="sxs-lookup"><span data-stu-id="4f240-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="4f240-103">В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] в ходе проверки XSD-схемы выявляется нарушение ограничения уникальности, если используется составной ключ и один ключ является пустым.</span><span class="sxs-lookup"><span data-stu-id="4f240-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4f240-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="4f240-104">Impact</span></span>  
 <span data-ttu-id="4f240-105">Влияние этого изменения должно быть минимальным: в зависимости от спецификации схемы ожидается ошибка проверки схемы в случае нарушения ограничения `xsd:unique` при использовании составного ключа с пустым ключом.</span><span class="sxs-lookup"><span data-stu-id="4f240-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4f240-106">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="4f240-106">Mitigation</span></span>  
 <span data-ttu-id="4f240-107">Обнаружение ошибки проверки схемы при наличии одного пустого ключа в составном ключе — это настраиваемая функция.</span><span class="sxs-lookup"><span data-stu-id="4f240-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="4f240-108">Начиная с приложений, ориентированных на [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], функция обнаружения ошибок проверки схемы включена по умолчанию, однако ее можно отключить, чтобы не выполнять обнаружение ошибок проверки схемы.</span><span class="sxs-lookup"><span data-stu-id="4f240-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="4f240-109">В приложениях, выполняющихся в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], но ориентированных на [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] и более ранние версии платформы, обнаружение ошибок проверки схемы не выполняется по умолчанию, однако его можно включить, чтобы выполнять обнаружение ошибок проверки схемы.</span><span class="sxs-lookup"><span data-stu-id="4f240-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="4f240-110">Это поведение можно настроить, используя класс <xref:System.AppContext> для определения значения параметра `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="4f240-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="4f240-111">Так как значение параметра по умолчанию — `false` (пустые последовательности ключей не игнорируются), для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], можно отключить это поведение, используя следующий код для задания значения параметра `true`.</span><span class="sxs-lookup"><span data-stu-id="4f240-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 <span data-ttu-id="4f240-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="4f240-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span></span>  
  
 <span data-ttu-id="4f240-113">Для приложений, предназначенных для [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] и более ранних версий, поскольку значение параметра по умолчанию — `true` (пустые последовательности ключей игнорируются), можно гарантировать, что составной ключ с пустым ключом будет создавать ошибку проверки схемы, используя следующий код для задания значения параметра `false`.</span><span class="sxs-lookup"><span data-stu-id="4f240-113">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 <span data-ttu-id="4f240-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="4f240-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f240-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4f240-115">See Also</span></span>  
 [<span data-ttu-id="4f240-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="4f240-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

