---
title: Сравнение строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET Framework], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: e63b2a8ac44d6171f9c48990882780ea420f8c76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101670"
---
# <a name="comparing-strings-in-net"></a>Сравнение строк в .NET
Платформа .NET обеспечивает несколько методов для сравнения значений строк. В таблице ниже перечислены и описаны методы сравнения значений.  
  
|Имя метода|Использовать|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|Сравнивает значения двух строк. Возвращает целочисленное значение.|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|Сравнивает две строки без учета локального языка и региональных параметров. Возвращает целочисленное значение.|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|Сравнивает текущий строковый объект с другой строкой. Возвращает целочисленное значение.|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|Определяет, начинается ли строка с переданной строки. Возвращает логическое значение.|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|Определяет, заканчивается ли строка переданной строкой. Возвращает логическое значение.|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|Определяет, совпадают ли две строки. Возвращает логическое значение.|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|Возвращает индекс позиции символа или строки начиная с начала проверяемой строки. Возвращает целочисленное значение.|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|Возвращает индекс позиции символа или строки начиная с конца проверяемой строки. Возвращает целочисленное значение.|  
  
## <a name="compare"></a>Сравнение  
 Статический метод <xref:System.String.Compare%2A?displayProperty=nameWithType> позволяет тщательно сравнивать две строки. Этот метод учитывает язык и региональные параметры. Эту функцию можно использовать для сравнения двух строк или подстрок двух строк. Кроме того, имеются перегруженные методы, которые учитывают или не учитывают регистр и вариативность языка и региональных параметров. В таблице ниже приведены три целочисленных значения, которые может возвращать этот метод.  
  
|Возвращаемое значение|Условие|  
|------------------|---------------|  
|Отрицательное целое число|Первая строка предшествует второй в порядке сортировки.<br /><br /> -или-<br /><br /> Первая строка имеет значение `null`.|  
|0|Первая и вторая строка равны.<br /><br /> -или-<br /><br /> Обе строки имеют значение `null`.|  
|Положительное целое число<br /><br /> -или-<br /><br /> 1|Первая строка следует за второй в порядке сортировки.<br /><br /> -или-<br /><br /> Вторая строка имеет значение `null`.|  
  
> [!IMPORTANT]
> Метод <xref:System.String.Compare%2A?displayProperty=nameWithType> в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод <xref:System.String.Compare%2A?displayProperty=nameWithType> для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 В примере ниже метод <xref:System.String.Compare%2A?displayProperty=nameWithType> используется для определения относительных значений двух строк.  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 Этот пример выводит на консоль значение `-1` .  
  
 В предыдущем примере по умолчанию учитывается язык и региональные параметры. Для сравнения строк без учета языка и региональных параметров используйте перегрузку метода <xref:System.String.Compare%2A?displayProperty=nameWithType> , которая позволяет указать язык и региональные параметры с помощью параметра *culture* . Пример, демонстрирующий использование метода <xref:System.String.Compare%2A?displayProperty=nameWithType> для сравнения без учета языка и региональных параметров, см. в разделе [Сравнение строк без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="compareordinal"></a>CompareOrdinal  
 Метод <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> сравнивает два строковых объекта без учета локального языка и региональных параметров. Возвращаемые этим методом значения идентичны значениям, возвращаемым методом **Compare** в предыдущей таблице.  
  
> [!IMPORTANT]
> Метод <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 В примере ниже метод **CompareOrdinal** используется для сравнения значений двух строк.  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 Этот пример выводит на консоль значение `-32` .  
  
## <a name="compareto"></a>CompareTo  
 Метод <xref:System.String.CompareTo%2A?displayProperty=nameWithType> сравнивает строку, которую инкапсулирует текущий строковый объект, с другой строкой или объектом. Возвращаемые этим методом значения идентичны значениям, возвращаемым методом <xref:System.String.Compare%2A?displayProperty=nameWithType> в предыдущей таблице.  
  
> [!IMPORTANT]
> Метод <xref:System.String.CompareTo%2A?displayProperty=nameWithType> в основном предназначен для использования при упорядочивании или сортировке строк. Не следует использовать метод <xref:System.String.CompareTo%2A?displayProperty=nameWithType> для проверки на равенство (то есть для явного поиска возвращаемого значения 0 без учета того, является ли одна строка меньше или больше другой). Для определения равенства двух строк используйте метод <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .  
  
 В примере ниже метод <xref:System.String.CompareTo%2A?displayProperty=nameWithType> используется для сравнения объекта `string1` с объектом `string2` .  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 Этот пример выводит на консоль значение `-1` .  
  
 Все перегрузки метода <xref:System.String.CompareTo%2A?displayProperty=nameWithType> по умолчанию выполняют сравнение с учетом языка и региональных параметров и регистра. У этого метода нет перегрузок, позволяющих выполнять сравнение без учета языка и региональных параметров. В целях повышения ясности кода рекомендуется использовать вместо него метод **String.Compare** , указывая <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> для операций с учетом языка и региональных параметров и <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> для операций без учета языка и региональных параметров. Примеры, демонстрирующие использование метода **String.Compare** для сравнения с учетом и без учета языка и региональных параметров, см. в разделе [Сравнение строк без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).  
  
## <a name="equals"></a>Равно  
 С помощью метода **String.Equals** можно легко определить идентичность двух строк. Этот метод учитывает регистр и возвращает логическое значение **true** или **false** . Метод можно вызывать из существующего класса, как показано в следующем примере. В примере ниже метод **Equals** используется для определения того, содержит ли строковый объект фразу "Hello World".  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 Этот пример выводит на консоль значение `True` .  
  
 Этот метод также можно использовать как статический. В примере ниже два строковых объекта сравниваются с помощью статического метода.  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 Этот пример выводит на консоль значение `True` .  
  
## <a name="startswith-and-endswith"></a>StartsWith и EndsWith  
 Метод **String.StartsWith** можно использовать для определения того, начинается ли строковый объект с тех же символов, которые включает другая строка. Этот метод учитывает регистр и возвращает значение **true** , если текущий строковый объект начинается с переданной строки, и значение **false** в противном случае. В примере ниже этот метод используется для определения того, начинается ли строковый объект со слова "Hello".  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 Этот пример выводит на консоль значение `True` .  
  
 Метод **String.EndsWith** сравнивает переданную строку с символами, находящимися в конце текущего строкового объекта. Он также возвращает логическое значение. В примере ниже конец строки проверяется с помощью метода **EndsWith** .  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 Этот пример выводит на консоль значение `False` .  
  
## <a name="indexof-and-lastindexof"></a>IndexOf и LastIndexOf  
 С помощью метода **String.IndexOf** можно определить позицию первого вхождения конкретного символа в строку. Этот метод учитывает регистр и начинает отсчет с начала строки. Он возвращает позицию переданного символа, используя отсчитываемый от нуля индекс. Если символ не удается найти, возвращается значение –1.  
  
 В примере ниже метод **IndexOf** используется для поиска первого вхождения символа "`l`" в строку.  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 Этот пример выводит на консоль значение `2` .  
  
 Метод **String.LastIndexOf** аналогичен методу **String.IndexOf** за исключением того, что он возвращает позицию последнего вхождения конкретного символа в строку. Он учитывает регистр и использует отсчитываемый от нуля индекс.  
  
 В примере ниже метод **LastIndexOf** используется для поиска последнего вхождения символа "`l`" в строку.  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 Этот пример выводит на консоль значение `9` .  
  
 Оба метода полезно использовать в сочетании с методом **String.Remove** . Для получения позиции символа используется метод **IndexOf** или **LastIndexOf** , после чего эта позиция передается методу **Remove** для удаления символа или начинающегося с него слова.  
  
## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
- [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- [Таблицы весовых коэффициентов сортировки (для .NET в Windows)](https://www.microsoft.com/download/details.aspx?id=10921)
- [Таблица параметров сортировки по умолчанию для элементов Юникод (для .NET Core в Linux и macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
