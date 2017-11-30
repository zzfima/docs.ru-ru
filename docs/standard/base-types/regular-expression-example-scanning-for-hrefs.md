---
title: "Пример регулярного выражения. Поиск ссылок HREF"
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
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a>Пример регулярного выражения. Поиск ссылок HREF
В следующем примере показаны поиск и вывод всех значений href="...", а также их позиций в строке.  
  
## <a name="the-regex-object"></a>Объект Regex  
 Поскольку `DumpHRefs` метод может вызываться несколько раз из пользовательского кода, он использует `static` (`Shared` в Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> метод. Это позволяет обработчику регулярных выражений кэшировать регулярное выражение и избежать дополнительной нагрузки, создания нового <xref:System.Text.RegularExpressions.Regex> объекта при каждом вызове метода. Объект <xref:System.Text.RegularExpressions.Match> объект затем используется для перебора всех совпадений в строке.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 В следующем примере показан вызов метода `DumpHRefs`.  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 Возможные интерпретации шаблона регулярного выражения `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` показаны в следующей таблице.  
  
|Шаблон|Описание|  
|-------------|-----------------|  
|`href`|Совпадение с литеральной строкой "href". Сопоставление не учитывает регистр.|  
|`\s*`|Соответствует нулю или нескольким символам пробела.|  
|`=`|Совпадает со знака равенства.|  
|`\s*`|Соответствует нулю или нескольким символам пробела.|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|Полностью соответствовать одному из следующих без назначения результата захватываемой группе:<br /><br /> -Кавычки или апострофа, за которым следует ноль или более вхождений любых символов, кроме кавычки или апострофа, следуют кавычки или апостроф. В этот шаблон включена группа с именем `1`.<br />— Один или несколько знаков пустого пространства. В этот шаблон включена группа с именем `1`.|  
|`(?<1>[^"']*)`|Присвоить ноль или несколько любых символов, кроме кавычки или апострофа, группе записи `1`.|  
|`"(?<1>\S+)`|Присвоить один или несколько символов, отличных от пробела, захваченной группе с именем `1`.|  
  
## <a name="match-result-class"></a>Класс результата поиска  
 Результаты поиска, хранятся в <xref:System.Text.RegularExpressions.Match> класса, который предоставляет доступ к все подстроки, извлеченным при поиске. Также запоминается искомая строка и используемое регулярное выражение, чтобы оно могло вызвать <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> метод для выполнения другого поиска, начиная с того места, где закончилось последнее из них.  
  
## <a name="explicitly-named-captures"></a>Явно именованные шаблоны  
 В обычных регулярных выражениях круглые скобки, обозначающие отдельные шаблоны, автоматически последовательно нумеруются. В связи с этим возникают две проблемы. Во-первых, если регулярное выражение изменяется из-за вставки или удаления пары круглых скобок, все части кода, которые ссылаются на нумерованные шаблоны, необходимо переписать, чтобы отразить новую нумерацию. Во-вторых, вследствие того, что различные пары круглых скобок часто используются для определения двух альтернативных выражений для поиска, трудно определить, какое из двух выражений в действительности вернуло результат.  
  
 Для решения этих проблем <xref:System.Text.RegularExpressions.Regex> класс поддерживает синтаксис `(?<name>…)` для отслеживания соответствия в указанной области (области, можно назвать с помощью string или integer; целые числа работают быстрее). Таким образом, если совпадение будет найдено повторно, оно попадет в ту же ячейку. В случае конфликта успешным является то совпадение, которое было помещено в ячейку последним. (Однако доступен и полный список совпадений для одной ячейки. В разделе <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> Дополнительные сведения.)  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
