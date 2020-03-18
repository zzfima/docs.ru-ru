---
title: Объектная модель регулярных выражений
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, backreferences
- Regex class
- Match class
- pattern-matching with regular expressions, backreferences
- .NET Framework regular expressions, classes
- CaptureCollection class
- Group class
- characters [.NET Framework], backreferences
- substrings
- .NET Framework regular expressions, backreferences
- searching with regular expressions, classes
- backreferences
- Capture class
- repeating groups of characters
- MatchCollection class
- parsing text with regular expressions, backreferences
- regular expressions [.NET Framework]
- characters [.NET Framework], regular expressions
- classes [.NET Framework], regular expression
- regular expressions [.NET Framework], classes
- characters [.NET Framework], metacharacters
- metacharacters, regular expression classes
- metacharacters, backreferences
- parsing text with regular expressions, classes
- regular expressions [.NET Framework], backreferences
- strings [.NET Framework], regular expressions
- pattern-matching with regular expressions, classes
- GroupCollection class
ms.assetid: 49a21470-64ca-4b5a-a889-8e24e3c0af7e
ms.openlocfilehash: 8956be3cf8f96a8dd255f378d4927404c172c908
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160005"
---
# <a name="the-regular-expression-object-model"></a>Объектная модель регулярных выражений
<a name="introduction"></a> В этом разделе описывается объектная модель, используемая при работе с регулярными выражениями в .NET. Он содержит следующие разделы:  
  
- [Механизм регулярных выражений](#Engine)  
  
- [Объекты MatchCollection и Match](#Match_and_MCollection)  
  
- [Коллекция Group](#GroupCollection)  
  
- [Захватываемая группа](#the_captured_group)  
  
- [Коллекция Capture](#CaptureCollection)  
  
- [Отдельный захват](#the_individual_capture)  
  
<a name="Engine"></a>
## <a name="the-regular-expression-engine"></a>Механизм регулярных выражений  
 Механизм регулярных выражений в .NET представлен классом <xref:System.Text.RegularExpressions.Regex>. Механизм отвечает за синтаксический анализ и компиляцию регулярного выражение, а также выполнение операций, которые сопоставляют шаблон регулярного выражения с входной строкой. Этот механизм представляет центральный компонент объектной модели регулярных выражений .NET.  
  
 Вы можете использовать механизм регулярных выражений одним из двух способов:  
  
- Вызывая статичные методы класса <xref:System.Text.RegularExpressions.Regex>. Параметры метода включают в себя входную строку и шаблон регулярного выражения. Механизм регулярных выражений кэширует регулярные выражения, которые используются в вызовах статичных методов, чтобы повторные вызовы статичных методов регулярных выражений, применяющие одно и то же регулярное выражение, выполнялись относительно быстро.  
  
- Создавая экземпляр объекта <xref:System.Text.RegularExpressions.Regex>, передавая регулярное выражение конструктору класса. В этом случае объект <xref:System.Text.RegularExpressions.Regex> не изменяется (доступен только для чтения) и представляет механизм регулярных выражений, который тесно связана с одним регулярным выражением. Так как регулярные выражения, используемые экземплярами <xref:System.Text.RegularExpressions.Regex>, не кэшируются, не следует создавать экземпляр объекта <xref:System.Text.RegularExpressions.Regex> несколько раз с одним и тем же регулярным выражением.  
  
 Вы можете вызывать методы класса <xref:System.Text.RegularExpressions.Regex>, чтобы выполнить следующие операции:  
  
- определить, соответствует ли строка шаблону регулярного выражения;  
  
- извлечь одно сопоставление или первое сопоставление;  
  
- извлечь все сопоставления;  
  
- заменить сопоставленную подстроку;  
  
- разделить одну строку на массив строк.  
  
 Эти операции описаны в следующих разделах.  
  
### <a name="matching-a-regular-expression-pattern"></a>Сопоставление шаблона регулярного выражения  
 Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> возвращает значение `true`, если строка соответствует шаблону; в противном случае возвращается значение `false`. Метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> часто используется для проверки входной строки. Например, следующий код проверяет, содержит ли строка допустимый номер социального страхования для США.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/validate1.cs#1)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/validate1.vb#1)]  
  
 Возможные интерпретации шаблона регулярного выражения `^\d{3}-\d{2}-\d{4}$` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`^`|Выделение начала входной строки.|  
|`\d{3}`|Совпадение с тремя десятичными цифрами.|  
|`-`|Выделение дефиса.|  
|`\d{2}`|Совпадение с двумя десятичными цифрами.|  
|`-`|Выделение дефиса.|  
|`\d{4}`|Выделяются 4 десятичные цифры.|  
|`$`|Соответствует концу входной строки.|  
  
### <a name="extracting-a-single-match-or-the-first-match"></a>Извлечение одного сопоставления или первого сопоставления  
 Метод <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> возвращает объект <xref:System.Text.RegularExpressions.Match>, который содержит сведения о первой подстроке, соответствующей шаблону регулярного выражения. Если свойство `Match.Success` возвращает значение `true` (найдено соответствие), вы можете получить информацию о последующих соответствиях, вызвав метод <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>. Этот метод можно вызывать, пока свойство `Match.Success` не вернет значение `false`. Например, следующий код использует метод <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType> для поиска первого экземпляра повторяющегося слова в строке. Затем вызывается метод <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> для поиска других экземпляров. Пример просматривает свойство `Match.Success` после каждого вызова метода, чтобы определить, было ли текущее сопоставление успешным и следует ли вызывать метод <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match1.cs#2)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match1.vb#2)]  
  
 Возможные интерпретации шаблона регулярного выражения `\b(\w+)\W+(\1)\b` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Сопоставление начинается на границе слова.|  
|`(\w+)`|Совпадение с одним или несколькими символами слова. Это первая группа записи.|  
|`\W+`|Совпадение с одним или большим числом несловообразующих символов.|  
|`(\1)`|Выделение первой захватываемой строки. Это вторая группа записи.|  
|`\b`|Сопоставление заканчивается на границе слова.|  
  
### <a name="extracting-all-matches"></a>Извлечение всех сопоставлений  
 Метод <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> возвращает объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий сведения о всех сопоставлениях, найденных механизмом регулярных выражений во входной строке. Например, предыдущий пример можно изменить, чтобы вызывать метод <xref:System.Text.RegularExpressions.Regex.Matches%2A> вместо методов <xref:System.Text.RegularExpressions.Regex.Match%2A> и <xref:System.Text.RegularExpressions.Match.NextMatch%2A>.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matches1.cs#3)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matches1.vb#3)]  
  
### <a name="replacing-a-matched-substring"></a>Замена сопоставленной подстроки  
 Метод <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> заменяет каждую подстроку, соответствующую шаблону регулярного выражения, на указанную строку или шаблон регулярного выражения и возвращает всю замененную входную строку. Например, следующий код добавляет обозначение денежной единицы США перед десятичным числом в строке.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/replace1.cs#4)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/replace1.vb#4)]  
  
 Возможные интерпретации шаблона регулярного выражения `\b\d+\.\d{2}\b` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`\d+`|Совпадение с одной или несколькими десятичными цифрами.|  
|`\.`|Сопоставляется точка.|  
|`\d{2}`|Совпадение с двумя десятичными цифрами.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  
  
 Шаблон замены `$$$&` интерпретируется, как показано в следующей таблице.  
  
|Шаблон|Строка замены|  
|-------------|------------------------|  
|`$$`|Символ доллара ($).|  
|`$&`|Вся сопоставленная подстрока.|  
  
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Разделение одной строки на массив строк  
 Метод <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> разделяет входную строку в позициях, заданных соответствием регулярного выражения. Например, следующий код помещает элементы нумерованного списка в массив строк.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/split1.cs#5)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/split1.vb#5)]  
  
 Возможные интерпретации шаблона регулярного выражения `\b\d{1,2}\.\s` показаны в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`\d{1,2}`|Совпадение с одной или двумя десятичными цифрами.|  
|`\.`|Сопоставляется точка.|  
|`\s`|Соответствует пробелу.|  
  
<a name="Match_and_MCollection"></a>
## <a name="the-matchcollection-and-match-objects"></a>Объекты MatchCollection и Match  
 Методы Regex возвращают два объекта, входящие в объектную модель регулярного выражения: <xref:System.Text.RegularExpressions.MatchCollection> и <xref:System.Text.RegularExpressions.Match>.  
  
<a name="the_match_collection"></a>
### <a name="the-match-collection"></a>Коллекция Match  
 Метод <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> возвращает объект <xref:System.Text.RegularExpressions.MatchCollection>, содержащий объекты <xref:System.Text.RegularExpressions.Match>, которые представляют все сопоставления, найденных механизмом регулярных выражений, в том порядке, в котором они присутствуют во входной строке. Если соответствий нет, метод возвращает объект <xref:System.Text.RegularExpressions.MatchCollection> без членов. Свойство <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType> позволяет получить доступ к отдельным членам коллекции по индексу (от нуля до значения свойства <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType> минус 1). <xref:System.Text.RegularExpressions.MatchCollection.Item%2A> — это индексатор коллекции (для C#) и свойство по умолчанию (для Visual Basic).  
  
 По умолчанию вызов метода <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> использует отложенные вычисления для заполнения объекта <xref:System.Text.RegularExpressions.MatchCollection>. Доступ к свойствам, которым требуется полностью заполненная коллекция, например свойства <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType> и <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType>, может быть связан с дополнительными затратами. Поэтому мы рекомендуем обращаться к коллекции, используя объект <xref:System.Collections.IEnumerator>, возвращаемый методом <xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator%2A?displayProperty=nameWithType>. Некоторые языки предоставляют конструкции, такие как `For Each` в Visual Basic и `foreach` в C#, которые создают оболочку для интерфейса <xref:System.Collections.IEnumerator> коллекции.  
  
 Следующий пример использует метод <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%29?displayProperty=nameWithType> для заполнения объекта <xref:System.Text.RegularExpressions.MatchCollection> всеми соответствиями, найденными во входной строке. Пример перечисляет коллекцию, копирует соответствия в массив строк и записывает позиции символов в целочисленный массив.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matchcollection1.cs#6)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matchcollection1.vb#6)]  
  
<a name="the_match"></a>
### <a name="the-match"></a>Класс Match  
 Класс <xref:System.Text.RegularExpressions.Match> представляет результат одного сопоставления регулярного выражения. Доступ к объектам <xref:System.Text.RegularExpressions.Match> можно получить двумя способами:  
  
- Извлекая их из объекта <xref:System.Text.RegularExpressions.MatchCollection>, который возвращается методом <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>. Для извлечения отдельных объектов <xref:System.Text.RegularExpressions.Match> выполните итерацию коллекции, воспользовавшись конструкцией `foreach` (в C#) или `For Each`...`Next` (в Visual Basic), либо используйте свойство <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType> для извлечения конкретного объекта <xref:System.Text.RegularExpressions.Match> по индексу или по имени. Вы также можете получить отдельные объекты <xref:System.Text.RegularExpressions.Match> из коллекции, циклически проходя по коллекции по индексу (от нуля до числа объектов в коллекции минус 1). Однако этот метод не использует отложенные вычисления, так как он обращается к свойству <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>.  
  
     Следующий пример извлекает отдельные объекты <xref:System.Text.RegularExpressions.Match> из объекта <xref:System.Text.RegularExpressions.MatchCollection>, циклически перебирая коллекцию с помощью конструкции `foreach` или `For Each`...`Next`. Регулярное выражение просто сопоставляет строку "abc" во входной строке.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match2.vb#7)]  
  
- Вызывая метод <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>, который возвращает объект <xref:System.Text.RegularExpressions.Match>, представляющий первое соответствие в строке или ее части. Вы можете определить, найдено ли соответствие, получив значение свойства `Match.Success`. Чтобы извлечь объекты <xref:System.Text.RegularExpressions.Match>, представляющие последующие соответствия, вызывайте метод <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>, пока свойство `Success` полученного объекта <xref:System.Text.RegularExpressions.Match> не будет иметь значение `false`.  
  
     Следующий пример использует методы <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType> и <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> для сопоставления строки "abc" во входной строке.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match3.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match3.vb#8)]  
  
 Два свойства класса <xref:System.Text.RegularExpressions.Match> возвращают объекты коллекции:  
  
- Свойство <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> возвращает объект <xref:System.Text.RegularExpressions.GroupCollection>, который содержит сведения о подстроках, соответствующих захватываемым группам в шаблоне регулярного выражения.  
  
- Свойство `Match.Captures` возвращает объект <xref:System.Text.RegularExpressions.CaptureCollection> с ограниченным применением. Коллекция не заполняется для объекта <xref:System.Text.RegularExpressions.Match>, свойство `Success` которого имеет значение `false`. В противном случае она содержит один объект <xref:System.Text.RegularExpressions.Capture>, содержащий такие же данные, что и объект <xref:System.Text.RegularExpressions.Match>.  
  
 Дополнительные сведения об этих объектах см. в разделах [Коллекция Group](#GroupCollection) и [Коллекция Capture](#CaptureCollection) далее в этой статье.  
  
 Два дополнительных свойства класса <xref:System.Text.RegularExpressions.Match> предоставляют сведения о соответствии. Свойство `Match.Value` возвращает подстроку из входной строки, соответствующую шаблону регулярного выражения. Свойства `Match.Index` возвращает начальную позицию сопоставленной подстроки во входной строке с основанием ноль.  
  
 Класс <xref:System.Text.RegularExpressions.Match> также содержит два метода сопоставления шаблона:  
  
- Метод <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> ищет совпадение после соответствия, представленного текущим объектом <xref:System.Text.RegularExpressions.Match>, и возвращает объект <xref:System.Text.RegularExpressions.Match>, представляющий соответствие.  
  
- Метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> выполняет указанную замену в сопоставленной строке и возвращает результат.  
  
 В следующем примере метод <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> используется для добавления символа $ и пробела перед каждым числом из двух дробных разрядов.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/result1.cs#9)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/result1.vb#9)]  
  
 Шаблон регулярного выражения `\b\d+(,\d{3})*\.\d{2}\b` определяется, как показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`\d+`|Совпадение с одной или несколькими десятичными цифрами.|  
|`(,\d{3})*`|Совпадение с нулем или несколькими вхождениями запятой, за которыми следуют три десятичные цифры.|  
|`\.`|Совпадение с символом десятичной точки.|  
|`\d{2}`|Совпадение с двумя десятичными цифрами.|  
|`\b`|Совпадение должно заканчиваться на границе слова.|  
  
 Шаблон замены `$$ $&` указывает, что сопоставленную подстроку следует заменить на символ доллара ($) (шаблон `$$`), пробел и значение соответствия (шаблон `$&`).  
  
 [Вверх](#introduction)  
  
<a name="GroupCollection"></a>
## <a name="the-group-collection"></a>Коллекция Group  
 Свойство <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> возвращает объект <xref:System.Text.RegularExpressions.GroupCollection>, содержащий объекты <xref:System.Text.RegularExpressions.Group>, которые представляют захватываемые группы в одном соответствии. Первый объект <xref:System.Text.RegularExpressions.Group> в коллекции (объект с нулевым индексом) представляет все сопоставление. Каждый последующий объект представляет результаты одной захватываемой группы.  
  
 Вы можете извлечь отдельные объекты <xref:System.Text.RegularExpressions.Group> из коллекции, используя свойство <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType>. Неименованные группы можно извлечь по их номеру в коллекции, а именованные группы — по имени или номеру. Неименованные выделения идут в коллекции первыми и индексируются слева направо в том порядке, в котором они указаны в шаблоне регулярного выражения. Именованные выделения индексируются после неименованных слева направо в том порядке, в котором они указаны в шаблоне регулярного выражения. Чтобы определить, какие нумерованные группы доступны в коллекции, возвращаемой для определенного метода сопоставления регулярного выражения, вызовите метод <xref:System.Text.RegularExpressions.Regex.GetGroupNumbers%2A?displayProperty=nameWithType> экземпляра. Чтобы определить, какие именованные группы доступны в коллекции, вызовите метод <xref:System.Text.RegularExpressions.Regex.GetGroupNames%2A?displayProperty=nameWithType> экземпляра. Оба метода полезны в процедурах общего назначения, которые анализируют соответствия, найденные любым регулярным выражением.  
  
 Свойство <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType> — это индексатор коллекции для C# и свойство объекта по умолчанию для Visual Basic. Это значит, что доступ к отдельным объектам <xref:System.Text.RegularExpressions.Group> можно получить по индексу (или, для именованных групп, по имени) следующим образом:  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupsyntax1.cs#13)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupsyntax1.vb#13)]  
  
 В следующем примере определяется регулярное выражение, которое использует конструкции группировки для выделения месяца, дня и года из даты.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupcollection1.cs#10)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupcollection1.vb#10)]  
  
 Шаблон регулярного выражения `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` определяется, как показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\b`|Совпадение должно начинаться на границе слова.|  
|`(\w+)`|Совпадение с одним или несколькими символами слова. Это первая группа записи.|  
|`\s`|Соответствует пробелу.|  
|`(\d{1,2})`|Совпадение с одной или двумя десятичными цифрами. Это вторая группа записи.|  
|`,`|Сопоставление запятой.|  
|`\s`|Соответствует пробелу.|  
|`(\d{4})`|Выделяются 4 десятичные цифры. Это третья группа записи.|  
|`\b`|Сопоставление заканчивается на границе слова.|  
  
 [Вверх](#introduction)  
  
<a name="the_captured_group"></a>
## <a name="the-captured-group"></a>Захватываемая группа  
 Класс <xref:System.Text.RegularExpressions.Group> представляет результат одной захватываемой группы. Объекты Group, представляющие захватываемые группы, заданные в регулярном выражении, возвращаются свойством <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> объекта <xref:System.Text.RegularExpressions.GroupCollection>, который возвращается свойством <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>. Свойство <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> — это индексатор (для C#) и свойство по умолчанию (для Visual Basic) класса <xref:System.Text.RegularExpressions.Group>. Вы также можете извлечь отдельные члены, циклически перебирая коллекцию с помощью конструкции `foreach` или `For Each`. Пример см. в предыдущем разделе.  
  
 В следующем примере вложенные конструкции группировки используются для записи подстрок в группы. Шаблон регулярного выражения `(a(b))c` сопоставляет строку "abc". Он назначает подстроку "ab" первой захватываемой группе, а подстроку "b" — второй захватываемой группе.  
  
 [!code-csharp[RegularExpressions.Classes#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#6)]
 [!code-vb[RegularExpressions.Classes#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#6)]  
  
 В следующем примере именованные конструкции группировки используются для выделения подстрок из строки, содержащей данные в формате "DATANAME:VALUE", которые регулярное выражение разделяет в позиции двоеточия (:).  
  
 [!code-csharp[RegularExpressions.Classes#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#8)]
 [!code-vb[RegularExpressions.Classes#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#8)]  
  
 Шаблон регулярного выражения `^(?<name>\w+):(?<value>\w+)` определяется, как показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`^`|Начало совпадения в начале входной строки.|  
|`(?<name>\w+)`|Совпадение с одним или несколькими символами слова. Имя захватываемой группы — `name`.|  
|`:`|Сопоставление двоеточия.|  
|`(?<value>\w+)`|Совпадение с одним или несколькими символами слова. Имя захватываемой группы — `value`.|  
  
 Свойства класса <xref:System.Text.RegularExpressions.Group> предоставляют сведения о захватываемой группе: свойство `Group.Value` содержит выделенную подстроку, свойство `Group.Index` указывает начальную позицию захватываемой группы во входном тексте, свойство `Group.Length` содержит длину выделенного текста, а свойство `Group.Success` указывает, соответствует ли подстрока шаблону, заданному захватываемой группой.  
  
 Применение квантификаторов к группе (см. раздел [Квантификаторы](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)) изменяет связь одного выделения в захватываемой группе двумя способами:  
  
- Если квантификатор `*` или `*?` (который указывает ноль или больше соответствий) применен к группе, во входной строке может отсутствовать соответствие захватываемой группе. Если выделенного текста нет, свойства объекта <xref:System.Text.RegularExpressions.Group> задаются, как показано в следующей таблице.  
  
    |Свойство объекта Group|Значение|  
    |--------------------|-----------|  
    |`Success`|`false`|  
    |`Value`|<xref:System.String.Empty?displayProperty=nameWithType>|  
    |`Length`|0|  
  
     Это показывается в следующем примере. В шаблоне регулярного выражения `aaa(bbb)*ccc` первая захватываемая группа (подстрока "bbb") может быть сопоставлена ноль или больше раз. Так как входная строка "aaaccc" соответствует шаблону, захватываемая группа не имеет соответствия.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/nocapture1.cs#11)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/nocapture1.vb#11)]  
  
- Квантификаторы могут сопоставлять множество вхождений шаблона, заданного захватываемой группой. В этом случае свойства `Value` и `Length` объекта <xref:System.Text.RegularExpressions.Group> содержат сведения только о последней выделенной подстроке. Например, следующее регулярное выражение сопоставляет предложение, заканчивающееся на точку. Оно использует две конструкции группировки: первая выделяет отдельные слова вместе с пробелом, вторая выделяет отдельные слова. Как видно из результата выполнения примера, хотя регулярное выражение успешно выделяет все предложение, вторая захватываемая группа выделяет только последнее слово.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/lastcapture1.cs#12)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/lastcapture1.vb#12)]  
  
 [Вверх](#introduction)  
  
<a name="CaptureCollection"></a>
## <a name="the-capture-collection"></a>Коллекция Capture  
 Объект <xref:System.Text.RegularExpressions.Group> содержит сведения только о последнем выделении. Однако весь набор выделений, созданный захватываемой группой, по-прежнему доступен из объекта <xref:System.Text.RegularExpressions.CaptureCollection>, возвращаемого свойством <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>. Каждый член коллекции — это объект <xref:System.Text.RegularExpressions.Capture>, представляющий выделение этой захватываемой группы в порядке захвата (и, следовательно, в порядке сопоставления выделенных строк слева направо во входной строке). Вы можете извлечь отдельные объекты <xref:System.Text.RegularExpressions.Capture> из коллекции одним из двух способов:  
  
- циклически перебирая коллекцию с помощью конструкции `foreach` (для C#) или `For Each` (для Visual Basic);  
  
- используя свойство <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A?displayProperty=nameWithType> для извлечения определенного объекта по индексу. Свойство <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A> — это свойство по умолчанию (для Visual Basic) индексатор (для C#) класса <xref:System.Text.RegularExpressions.CaptureCollection>.  
  
 Если квантификатор не применен к захватываемой группе, объект <xref:System.Text.RegularExpressions.CaptureCollection> содержит один объект <xref:System.Text.RegularExpressions.Capture>, который не представляет особого интереса, так как он содержит сведения о том же соответствии, что и объект <xref:System.Text.RegularExpressions.Group>. Если к захватываемой группе применен квантификатор, объект <xref:System.Text.RegularExpressions.CaptureCollection> содержит все выделения захватываемой группы, а последний член коллекции представляет то же выделение, что и объект <xref:System.Text.RegularExpressions.Group>.  
  
 Например, если использовать шаблон регулярного выражения `((a(b))c)+` (где квантификатор "+" указывает одно или несколько соответствий) для выделения соответствий из строки "abcabcabc", объект <xref:System.Text.RegularExpressions.CaptureCollection> для каждого объекта <xref:System.Text.RegularExpressions.Group> содержит три члена.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capturecollection1.cs#14)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capturecollection1.vb#14)]  
  
 Следующий пример использует регулярное выражение `(Abc)+` для поиска одного или нескольких последовательных вхождений строки "Abc" в строке "XYZAbcAbcAbcXYZAbcAb". Этот пример демонстрирует использование свойства <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> для получения нескольких групп выделенных подстрок.  
  
 [!code-csharp[RegularExpressions.Classes#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#5)]
 [!code-vb[RegularExpressions.Classes#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#5)]  
  
 [Вверх](#introduction)  
  
<a name="the_individual_capture"></a>
## <a name="the-individual-capture"></a>Отдельное выделение  
 Класс <xref:System.Text.RegularExpressions.Capture> содержит результаты одного выделения части выражения. Свойство <xref:System.Text.RegularExpressions.Capture.Value%2A?displayProperty=nameWithType> содержит сопоставленный текст, а свойство <xref:System.Text.RegularExpressions.Capture.Index%2A?displayProperty=nameWithType> указывает начальную позицию сопоставленной подстроки во входной строке с основанием ноль.  
  
 Следующий пример ищет во входной строке температуру выбранных городов. Запятая (",") используется для разделения города и температуры, а точка с запятой (";") — для разделения данных каждого города. Вся входная строка представляет одно соответствие. В шаблоне регулярного выражения `((\w+(\s\w+)*),(\d+);)+`, который используется для анализа строки, название города назначается второй захватываемой группе, а температура — четвертой захватываемой группе.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capture1.cs#16)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capture1.vb#16)]  
  
 Определение регулярного выражения показано в следующей таблице.  
  
|Шаблон|Описание:|  
|-------------|-----------------|  
|`\w+`|Совпадение с одним или несколькими символами слова.|  
|`(\s\w+)*`|Сопоставляется ноль или несколько экземпляров пробела, за которыми следует один или несколько словообразующих символов. Этот шаблон выделяет названия городов из нескольких слов. Это третья группа записи.|  
|`(\w+(\s\w+)*)`|Сопоставляется один или несколько словообразующих символов, за которыми следует ноль или несколько пробелов и один или несколько словообразующих символов. Это вторая группа записи.|  
|`,`|Сопоставление запятой.|  
|`(\d+)`|Сопоставление с одной или несколькими цифрами. Это четвертая группа записи.|  
|`;`|Сопоставление точки с запятой.|  
|`((\w+(\s\w+)*),(\d+);)+`|Шаблона из слова, за которым следуют другие слова, запятая, одна или несколько цифр и точка запятая сопоставляется один или более раз. Это первая группа записи.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Text.RegularExpressions>
- [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
- [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
