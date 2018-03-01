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
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="58818-102">Преобразование типов .NET Framework в строки</span><span class="sxs-lookup"><span data-stu-id="58818-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="58818-103">Чтобы преобразовать тип .NET Framework в строку, используйте метод **ToString**.</span><span class="sxs-lookup"><span data-stu-id="58818-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="58818-104">Метод **ToString** возвращает символьное представление переданного типа.</span><span class="sxs-lookup"><span data-stu-id="58818-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="58818-105">В следующей таблице приведен список типов платформы .NET Framework, которые возвращают строку в формате, сопоставленном со спецификациями XSD.</span><span class="sxs-lookup"><span data-stu-id="58818-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="58818-106">Тип платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="58818-106">.NET Framework type</span></span>|<span data-ttu-id="58818-107">Возвращаемое строковое значение</span><span class="sxs-lookup"><span data-stu-id="58818-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="58818-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="58818-108">Boolean</span></span>|<span data-ttu-id="58818-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="58818-109">"true", "false"</span></span>|  
|<span data-ttu-id="58818-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="58818-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="58818-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="58818-111">"INF"</span></span>|  
|<span data-ttu-id="58818-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="58818-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="58818-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="58818-113">"-INF"</span></span>|  
|<span data-ttu-id="58818-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="58818-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="58818-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="58818-115">"INF"</span></span>|  
|<span data-ttu-id="58818-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="58818-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="58818-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="58818-117">"-INF"</span></span>|  
|<span data-ttu-id="58818-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="58818-118">DateTime</span></span>|<span data-ttu-id="58818-119">Используется формат гггг-ММ-ддТЧЧ:мм:ссzzzzzz и его подмножества.</span><span class="sxs-lookup"><span data-stu-id="58818-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="58818-120">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="58818-120">Timespan</span></span>|<span data-ttu-id="58818-121">Используется формат PnYnMnTnHnMnS. Например, значение `P2Y10M15DT10H30M20S` соответствует длительности в 2 года, 10 месяцев, 15 дней, 10 часов, 30 минут и 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="58818-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58818-122">См. также</span><span class="sxs-lookup"><span data-stu-id="58818-122">See Also</span></span>  
 [<span data-ttu-id="58818-123">Преобразование типов XML-данных</span><span class="sxs-lookup"><span data-stu-id="58818-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="58818-124">Преобразование строк в типы данных .NET Framework</span><span class="sxs-lookup"><span data-stu-id="58818-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
