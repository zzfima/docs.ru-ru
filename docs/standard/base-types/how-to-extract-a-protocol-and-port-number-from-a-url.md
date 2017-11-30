---
title: "Практическое руководство. Извлечение протокола и номера порта из URL-адреса"
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
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="d268c-102">Практическое руководство. Извлечение протокола и номера порта из URL-адреса</span><span class="sxs-lookup"><span data-stu-id="d268c-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="d268c-103">В следующем примере выполняется извлечение протокола и номера порта из URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="d268c-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d268c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d268c-104">Example</span></span>  
 <span data-ttu-id="d268c-105">В этом примере <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> метод для возврата протокола и двоеточие, за которым следует номер порта.</span><span class="sxs-lookup"><span data-stu-id="d268c-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="d268c-106">Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d268c-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="d268c-107">Шаблон</span><span class="sxs-lookup"><span data-stu-id="d268c-107">Pattern</span></span>|<span data-ttu-id="d268c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d268c-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="d268c-109">Соответствие должно обнаруживаться в начале строки.</span><span class="sxs-lookup"><span data-stu-id="d268c-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="d268c-110">Совпадение с одним или несколькими символами слова.</span><span class="sxs-lookup"><span data-stu-id="d268c-110">Match one or more word characters.</span></span> <span data-ttu-id="d268c-111">Имя этой группы `proto`.</span><span class="sxs-lookup"><span data-stu-id="d268c-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="d268c-112">Совпадение с двоеточием, за которым следуют две косые черты.</span><span class="sxs-lookup"><span data-stu-id="d268c-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="d268c-113">Совпадение с одним или несколькими вхождениями (но как можно меньшему числу) любого символа, отличного от косой черты.</span><span class="sxs-lookup"><span data-stu-id="d268c-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="d268c-114">Совпадение с вхождениями в количестве 0 или 1 двоеточия, за которым следует одна или несколько цифр.</span><span class="sxs-lookup"><span data-stu-id="d268c-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="d268c-115">Имя этой группы `port`.</span><span class="sxs-lookup"><span data-stu-id="d268c-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="d268c-116">Совпадение с косой чертой.</span><span class="sxs-lookup"><span data-stu-id="d268c-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="d268c-117"><xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Метод развертывает `${proto}${port}` замены последовательности, который объединяет значение две именованные группы, в шаблоне регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="d268c-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="d268c-118">Он является удобной альтернативой явно сцепления строк, полученных из коллекции объект, возвращаемый <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="d268c-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="d268c-119">В этом примере <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> метод с двумя подстановками `${proto}` и `${port}`, включаемых в выходной строке записанной группы.</span><span class="sxs-lookup"><span data-stu-id="d268c-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="d268c-120">Захватываемым группам можно получить из соответствующего <xref:System.Text.RegularExpressions.GroupCollection> вместо этого, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="d268c-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d268c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d268c-121">See Also</span></span>  
 [<span data-ttu-id="d268c-122">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="d268c-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
