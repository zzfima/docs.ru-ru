---
title: Практическое руководство. Извлечение протокола и номера порта из URL-адреса
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: f2704e3fb5ceb68609a475d52e11030177ad760b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138726"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="4a5e5-102">Практическое руководство. Извлечение протокола и номера порта из URL-адреса</span><span class="sxs-lookup"><span data-stu-id="4a5e5-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="4a5e5-103">В следующем примере выполняется извлечение протокола и номера порта из URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a5e5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4a5e5-104">Example</span></span>  
 <span data-ttu-id="4a5e5-105">Этот пример использует метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>, чтобы вернуть имя протокола и номер порта, разделенные двоеточием.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="4a5e5-106">Возможные интерпретации шаблона регулярного выражения `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="4a5e5-107">Шаблон</span><span class="sxs-lookup"><span data-stu-id="4a5e5-107">Pattern</span></span>|<span data-ttu-id="4a5e5-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="4a5e5-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="4a5e5-109">Соответствие должно обнаруживаться в начале строки.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="4a5e5-110">Совпадение с одним или несколькими символами слова.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-110">Match one or more word characters.</span></span> <span data-ttu-id="4a5e5-111">Присвойте этой группе имя `proto`.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="4a5e5-112">Совпадение с двоеточием, за которым следуют две косые черты.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="4a5e5-113">Совпадение с одним или несколькими вхождениями (но как можно меньшему числу) любого символа, отличного от косой черты.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="4a5e5-114">Совпадение с вхождениями в количестве 0 или 1 двоеточия, за которым следует одна или несколько цифр.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="4a5e5-115">Присвойте этой группе имя `port`.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="4a5e5-116">Совпадение с косой чертой.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="4a5e5-117">Метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> разворачивает последовательность замены `${proto}${port}`, которая объединяет захваченное значение из двух именованных групп в шаблоне регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="4a5e5-118">Это удобная альтернатива явному объединению строк, извлеченных из объекта коллекции, который был возвращен свойством <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="4a5e5-119">В примере используется метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> с двумя подстановками `${proto}` и `${port}` для включения захваченных групп в выходную строку.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="4a5e5-120">Вместо этого вы можете извлечь захваченные группы из объекта <xref:System.Text.RegularExpressions.GroupCollection> в сопоставлении, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4a5e5-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4a5e5-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4a5e5-121">See also</span></span>

- [<span data-ttu-id="4a5e5-122">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="4a5e5-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
