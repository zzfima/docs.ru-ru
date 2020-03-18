---
title: Сокращение и удаление символов из строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: bdbe267bb178e90c0008422e6543a23178c2c4d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159992"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a>Сокращение и удаление символов из строк в .NET
При разборе предложения на отдельные слова может оказаться, что в начале или в конце некоторых слов стоят пробелы. В этом случае можно воспользоваться методами сокращения в классе **System.String**, чтобы удалить любое количество пробелов или других символов из указанной позиции в строке. В таблице ниже описаны доступны методы сокращения.  
  
|Имя метода|Использование|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|Удаление пробелов или знаков, указанных в массиве знаков, из начала и конца строки.|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|Удаление символов, указанных в массиве символов, в конце строки.|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|Удаление символов, указанных в массиве символов, в начале строки.|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|Удаление указанного количества символов в указанной позиции индекса в строке.|  
  
## <a name="trim"></a>Trim

 Простой способ удалить пробелы с обоих концов строки — метод <xref:System.String.Trim%2A?displayProperty=nameWithType>, использование которого показано в следующем примере.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 Кроме того, можно удалить символы, указанные в массиве знаков, из начала и конца строки. В следующем примере удаляются символы пробелов, точки и звездочки.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a>TrimEnd

 Метод **String.TrimEnd** удаляет символы в конце строки, создавая новый строковый объект. Для указания символов, которые следует удалять, в этот метод передается массив символов. Порядок элементов в массиве символов не влияет на выполнение операции сокращения. В случае обнаружения символа, который отсутствует в массиве, операция останавливается.  
  
 Ниже приведен пример удаления последних букв строки с помощью метода **TrimEnd**. В этом примере положение символов `'r'` и `'W'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения. Обратите внимание, что этот код удаляет последнее слово `MyString` и часть первого.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 Этот код выводит на консоль значение `He`.  
  
 Ниже приведен пример удаления последнего слова строки с помощью метода **TrimEnd**. В этом коде после слова `Hello` следует запятая, а поскольку запятая не указана в массиве символов для сокращения, то выполнение операции прекращается на запятой.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 Этот код выводит на консоль значение `Hello,`.  
  
## <a name="trimstart"></a>TrimStart

 Метод **String.TrimStart** аналогичен методу **String.TrimEnd** за исключением того, что он создает новую строку путем удаления знаков в начале существующего строкового объекта. Для указания символов, которые следует удалять, в метод **TrimStart** передается массив символов. Как и в случае с методом **TrimEnd**, порядок элементов в массиве символов не влияет на выполнение операции сокращения. В случае обнаружения символа, который отсутствует в массиве, операция останавливается.  
  
 В следующем примере удаляется первое слово в строке. В этом примере положение символов `'l'` и `'H'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 Этот код выводит на консоль значение `World!`.  
  
## <a name="remove"></a>Remove

 Метод <xref:System.String.Remove%2A?displayProperty=nameWithType> удаляет указанное количество знаков, начиная с указанного места в существующей строке. Этот метод подразумевает, что отсчет индекса начинается с нуля.  
  
 В следующем примере из строки удаляется десять символов, начиная с пятой позиции отсчитываемого от нуля индекса строки.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a>Заменить

 Чтобы удалить из строки указанный символ или подстроку, можно вызвать метод <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> и указать пустую строку (<xref:System.String.Empty?displayProperty=nameWithType>) в качестве замены. В следующем примере удаляются все запятые из строки.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a>См. также раздел

- [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
