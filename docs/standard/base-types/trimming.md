---
title: "Сокращение и удаление знаков из строк в .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Remove - метод"
  - "удаление знаков"
  - "строки [платформа .NET Framework], удаление знаков"
  - "Trim - метод"
  - "TrimEnd - метод"
  - "обрезка знаков"
  - "TrimStart - метод"
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Сокращение и удаление знаков из строк в .NET Framework
При разборе предложения на отдельные слова может оказаться, что некоторые слова на обоих концах содержат пробелы.  В этом случае для удаления ряда пропусков или других знаков из указанного места строки используются методы сокращения из класса **System.String**.  В следующей таблице представлены доступные методы сокращения.  
  
|Название метода|Применение|  
|---------------------|----------------|  
|<xref:System.String.Trim%2A?displayProperty=fullName>|Удаление пробелов или знаков, указанных в массиве знаков, из начала и конца строки.|  
|<xref:System.String.TrimEnd%2A?displayProperty=fullName>|Удаление знаков, указанных в массиве знаков, из конца строки.|  
|<xref:System.String.TrimStart%2A?displayProperty=fullName>|Удаление знаков, указанных в массиве знаков, из начала строки.|  
|<xref:System.String.Remove%2A?displayProperty=fullName>|Удаление указанного числа знаков из указанной позиции индекса в строке.|  
  
## Trim  
 Простым методом удаления пробелов из обоих концов строки является метод <xref:System.String.Trim%2A?displayProperty=fullName>, использование которого показано в следующем примере.  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 Кроме того, можно удалить символы, указанные в массиве знаков из начала и конца строки.  Следующий пример удаляет символы пробелов, точки и звездочки.  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## TrimEnd  
 Метод **String.TrimEnd** удаляет знаки из конца строки, создавая новый объект строки.  Массив знаков передается этому методу для указания удаляемых знаков.  Порядок элементов в массиве знаков не влияет на операцию сокращения.  Сокращение прекращается, если найденный знак не указан в массиве.  
  
 В следующем примере удаляются последние буквы строки с помощью метода **TrimEnd**.  В этом примере положение знаков `'r'` и `'W'` изменено для иллюстрации того, что порядок знаков в массиве не имеет значения.  Обратите внимание, что этот код удаляет последнее слово `MyString` и часть первого.  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 Этот код выводит текст `He` на консоль.  
  
 В следующем примере с помощью метода **TrimEnd** удаляется последнее слово строки.  В этом коде за словом `Hello` следует запятая, и, поскольку запятая не указана в массиве знаков для сокращения, сокращение прекращается на запятой.  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 Этот код выводит текст `Hello,` на консоль.  
  
## TrimStart  
 Метод **String.TrimStart** аналогичен методу **String.TrimEnd**, за исключением того, что он создает новую строку, удаляя знаки из начала существующего объекта строки.  Массив знаков передается методу **TrimStart** для указания удаляемых знаков.  Как и в методе **TrimEnd**, порядок элементов в массиве знаков не влияет на операцию сокращения.  Сокращение прекращается, если найденный знак не указан в массиве.  
  
 В следующем примере удаляется первое слово строки.  В этом примере положение знаков `'l'` и `'H'` изменено для иллюстрации того, что порядок знаков в массиве не имеет значения.  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 Этот код выводит текст `World!` на консоль.  
  
## Удалить  
 Метод <xref:System.String.Remove%2A?displayProperty=fullName> удаляет указанное число знаков, начиная с указанного места в существующей строке.  В этом методе предполагается, что индексация начинается с нуля.  
  
 В следующем примере удаляются десять знаков из строки, начиная с пятой позиции индекса строки, начинающегося с нуля.  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
 Можно также удалить из строки указанный символ или подстроку, вызвав метод <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=fullName> с указанием пустой строки \(<xref:System.String.Empty?displayProperty=fullName>\) в качестве замены.  Следующий пример удаляет все запятые из строки.  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## См. также  
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)