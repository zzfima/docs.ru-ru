---
title: "Заполнение строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="b34eb-102">Заполнение строк в .NET</span><span class="sxs-lookup"><span data-stu-id="b34eb-102">Padding Strings in .NET</span></span>
<span data-ttu-id="b34eb-103">Используйте один из следующих <xref:System.String> методы для создания новой строки, состоящий из исходной строки, дополняется стоящими в начале и конце строки символов в указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="b34eb-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="b34eb-104">В качестве заполняющего знака, который, соответственно, будет повторяться либо справа, либо слева, может использоваться пробел или знак, заданный в явной форме.</span><span class="sxs-lookup"><span data-stu-id="b34eb-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="b34eb-105">Имя метода</span><span class="sxs-lookup"><span data-stu-id="b34eb-105">Method name</span></span>|<span data-ttu-id="b34eb-106">Применение</span><span class="sxs-lookup"><span data-stu-id="b34eb-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="b34eb-107">Дополняет строку до указанной общей длины знаками с начала.</span><span class="sxs-lookup"><span data-stu-id="b34eb-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="b34eb-108">Дополняет строку до указанной общей длины знаками с конца.</span><span class="sxs-lookup"><span data-stu-id="b34eb-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="b34eb-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="b34eb-109">PadLeft</span></span>  
 <span data-ttu-id="b34eb-110"><xref:System.String.PadLeft%2A?displayProperty=nameWithType> Метод создает новую строку с помощью объединения знаки к исходной строке, для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="b34eb-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b34eb-111"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> Метод использует в качестве символа заполнения пустого пространства и <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> метод дает возможность указать собственные заполняющий символ.</span><span class="sxs-lookup"><span data-stu-id="b34eb-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="b34eb-112">Следующий пример кода использует <xref:System.String.PadLeft%2A> метод для создания новой строки, длину 20 символов.</span><span class="sxs-lookup"><span data-stu-id="b34eb-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b34eb-113">Этот пример выводит на консоль значение "`--------Hello World!`".</span><span class="sxs-lookup"><span data-stu-id="b34eb-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="b34eb-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="b34eb-114">PadRight</span></span>  
 <span data-ttu-id="b34eb-115"><xref:System.String.PadRight%2A?displayProperty=nameWithType> Метод создает новую строку с помощью объединения знаки к исходной строке, для достижения указанной общей длины.</span><span class="sxs-lookup"><span data-stu-id="b34eb-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b34eb-116"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> Метод использует в качестве символа заполнения пустого пространства и <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> метод дает возможность указать собственные заполняющий символ.</span><span class="sxs-lookup"><span data-stu-id="b34eb-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="b34eb-117">Следующий пример кода использует <xref:System.String.PadRight%2A> метод для создания новой строки, длину 20 символов.</span><span class="sxs-lookup"><span data-stu-id="b34eb-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b34eb-118">Этот пример выводит на консоль значение "`Hello World!--------`".</span><span class="sxs-lookup"><span data-stu-id="b34eb-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b34eb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b34eb-119">See Also</span></span>  
 [<span data-ttu-id="b34eb-120">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b34eb-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
