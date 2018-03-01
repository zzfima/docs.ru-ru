---
title: "Практическое руководство. Добавление к числу начальных нулей."
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
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7ea854f69e59c614d03f10ff546bd3181f5b51ff
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Практическое руководство. Добавление к числу начальных нулей.
К целому числу можно добавить начальные нули, используя [строку стандартного числового формата](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" с описателем точности. С помощью [строки настраиваемого числового формата](../../../docs/standard/base-types/custom-numeric-format-strings.md) начальные нули можно добавлять как к целым числам, так и к числам с плавающей запятой. В этой статье показано, как использовать оба метода для дополнения числа начальными нулями.  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Дополнение целого числа начальными нулями до определенной длины  
  
1.  Определите минимальное число разрядов для целого числа. Добавьте к этому значению число начальных разрядов.  
  
2.  Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное.  
  
    -   Чтобы отобразить целое число в виде десятичного значения, вызовите его метод `ToString(String)` и передайте строку "D*n*" в качестве значения параметра `format`, где *n* представляет минимальную длину строки.  
  
    -   Чтобы отобразить целое число в виде шестнадцатеричного значения, вызовите его метод `ToString(String)` и передайте строку "X*n*" в качестве значения параметра `format`, где *n* представляет минимальную длину строки.  
  
     Вы также можете использовать строку формата в методе, например <xref:System.String.Format%2A> или <xref:System.Console.WriteLine%2A>, который использует [составное форматирование](../../../docs/standard/base-types/composite-formatting.md).  
  
 Следующий пример форматирует несколько целых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Дополнение целого числа определенным количеством начальных нулей  
  
1.  Определите, сколько начальных нулей должно быть в целом числе.  
  
2.  Определите, хотите ли вы показывать целое число как десятичное или шестнадцатеричное. Чтобы отформатировать число как десятичное значение, необходимо использовать стандартный описатель формата "D", чтобы отформатировать число как шестнадцатеричное значение, используйте стандартный описатель формата "X".  
  
3.  Определите длину недополненной числовой строки, вызвав метод `ToString("D").Length` или `ToString("X").Length` целого числа.  
  
4.  Добавьте число начальных нулей, которое следует добавить в форматированную строку, к длине недополненной числовой строки. Будет получена общая длина результирующей строки.  
  
5.  Вызовите для целого значения метод `ToString(String)` и передайте ему строку "D*n*" для десятичных строк или "X"*n* для шестнадцатеричных строк, где *n* представляет общую длину дополненной строки. Строку форматирования "D*n*" или "X*n*" можно также использовать в методе, поддерживающем составное форматирование.  
  
 Следующий пример дополняет целое число пятью начальными нулями.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Дополнение числового значения начальными нулями до определенной длины  
  
1.  Определите, сколько разрядов слева от десятичного разделителя должно быть в строковом представлении числа. Добавьте к этому значению число начальных нулей.  
  
2.  Определите строку настраиваемого формата числа, использующую местозаполнитель нуля ("0") для представления минимального количества нулей.  
  
3.  Вызовите метод `ToString(String)` числа и передайте ему строку настраиваемого формата. Вы также можете использовать строку настраиваемого формата с методом, поддерживающим составное форматирование.  
  
 Следующий пример форматирует несколько числовых значений с добавлением начальных нулей, чтобы общая длина форматированного числа составляла по крайней мере 8 символов слева от десятичного разделителя.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Дополнение числового значения определенным количеством начальных нулей  
  
1.  Определите, сколько начальных нулей должно быть в числовом значении.  
  
2.  Определите количество разрядов слева от десятичного разделителя в недополненной числовой строке. Для этого выполните следующие действия.  
  
    1.  Определите, содержит ли строковое представление числа символ десятичной точки.  
  
    2.  Если это так, определите число символов слева от десятичной точки.  
  
         - или -  
  
         Если строка не содержит десятичную точку, определите длину строки.  
  
3.  Создайте строку настраиваемого формата, использующую нулевой местозаполнитель ("0") для каждого начального нуля, которые будут добавлены в строку, и использующую нулевой местозаполнитель или местозаполнитель разряда ("#") для представления каждого разряда в строке по умолчанию.  
  
4.  Передайте строку настраиваемого формата как параметр методу `ToString(String)` числа или методу, поддерживающему составное форматирование.  
  
 Следующий пример дополняет два значения типа <xref:System.Double> число пятью начальными нулями.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md)
