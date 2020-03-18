---
title: Составное форматирование
ms.date: 10/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parameter specifiers
- strings [.NET Framework], alignment
- format specifiers, composite formatting
- strings [.NET Framework], composite
- composite formatting
- objects [.NET Framework], formatting multiple objects
ms.assetid: 87b7d528-73f6-43c6-b71a-f23043039a49
ms.openlocfilehash: b1ec8cfc0f8c6e660d716c51bf3c3387b73a278f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398481"
---
# <a name="composite-formatting"></a>Составное форматирование

В качестве входных данных для составного форматирования в .NET используется список объектов и строка составного формата. Строка составного формата состоит из фиксированного текста, в который включены индексированные местозаполнители, которые называются элементами форматирования и соответствуют объектам из списка. Операция форматирования создает результирующую строку, состоящую из исходного фиксированного текста, в который включено строковое представление объектов из списка.  
  
> [!IMPORTANT]
> Вместо использования строк составного формата можно использовать *интерполированные строки*, если их поддерживает язык и языковая версия, которые вы используете. Интерполированная строка — это строка, которая содержит *интерполированные выражения*. Каждое интерполированное выражение завершается значением выражения и включается в строку результатов, если строка назначена. Дополнительные сведения см. в разделе [Интерполяция строк (справочник по C#)](../../csharp/language-reference/tokens/interpolated.md) и [Интерполированные строки (справочник по Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).

Возможность составного форматирования поддерживается следующими методами:  
  
- Метод <xref:System.String.Format%2A?displayProperty=nameWithType>, который возвращает отформатированную результирующую строку.  
  
- Метод <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, который добавляет отформатированную результирующую строку в объект <xref:System.Text.StringBuilder>.
- Некоторые перегруженные версии метода <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, которые отображают отформатированную результирующую строку в консоли.  
  
- Некоторые перегруженные версии метода <xref:System.IO.TextWriter.WriteLine%2A?displayProperty=nameWithType>, которые записывают отформатированную результирующую строку в поток или файл. Классы, производные от <xref:System.IO.TextWriter>, например <xref:System.IO.StreamWriter> и <xref:System.Web.UI.HtmlTextWriter>, также поддерживают эту функцию.  
  
- Метод <xref:System.Diagnostics.Debug.WriteLine%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, который выводит отформатированное сообщение в прослушиватели трассировки.  
  
- Методы <xref:System.Diagnostics.Trace.TraceError%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.TraceWarning%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, которые выводят отформатированные сообщения в прослушиватели трассировки.  
  
- Метод <xref:System.Diagnostics.TraceSource.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, который записывает информационный метод в прослушиватели трассировки.  
  
## <a name="composite-format-string"></a>Строка составного формата  
 Строка составного формата и список объектов используются в качестве аргументов методов, поддерживающих составное форматирование. Строка составного формата состоит из блоков фиксированного текста числом от нуля и больше, перемежаемых одним или несколькими элементами форматирования. Фиксированным текстом может являться произвольная строка, а каждый элемент форматирования должен соответствовать объекту или упакованной структуре из списка. В ходе составного форматирования создается новая результирующая строка, в которой все элементы форматирования заменены на строковое представление соответствующих объектов из списка.  
  
 Рассмотрим следующий фрагмент кода <xref:System.String.Format%2A>.  
  
 [!code-csharp[Formatting.Composite#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#1)]
 [!code-vb[Formatting.Composite#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#1)]  
  
 Здесь "`Name =`" и "`, hours =`" — фиксированный текст. Элементы форматирования — это "`{0}`" c индексом 0, который соответствует объекту `name`, и "`{1:hh}`" с индексом 1, который соответствует объекту `DateTime.Now`.  
  
## <a name="format-item-syntax"></a>Синтаксис элементов форматирования  
 Каждый элемент форматирования имеет следующий вид и состоит из следующих компонентов:  
  
 `{` *index*[`,`*alignment*][`:`*formatString*]`}`  
  
 Парные фигурные скобки ("{" и "}") здесь обязательны.  
  
### <a name="index-component"></a>Индекс  
 Обязательный компонент *index*, также называемый описателем параметра, — это число, определяющее соответствующий объект из списка; индексация элементов ведется от нуля. Иными словами, элемент форматирования с индексом 0 отвечает за формат первого объекта в списке, элемент форматирования с индексом 1 служит для форматирования второго объекта в списке и т. д. В пример ниже входят четыре описателя параметров (с номерами от 0 до 3) для представления простых чисел меньше 10.  
  
 [!code-csharp[Formatting.Composite#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#7)]
 [!code-vb[Formatting.Composite#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#7)]  
  
 На один и тот же элемент в списке объектов может ссылаться сразу несколько элементов форматирования — достигается это путем задания одинакового описателя параметра. Например, одно и то же числовое значение можно отформатировать в шестнадцатеричном, экспоненциальном и десятичном виде путем задания следующей строки составного форматирования: "0x{0:X} {0:E} {0:N}", как показано в следующем примере.  
  
 [!code-csharp[Formatting.Composite#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#10)]
 [!code-vb[Formatting.Composite#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#10)]  
  
 Любой элемент форматирования может ссылаться на произвольный объект списка. Например, если имеется три объекта, то можно отформатировать сначала второй, а затем первый и третий объекты, указав следующую строку составного форматирования: "{1} {0} {2}". Объекты, на которые не ссылаются элементы форматирования, пропускаются. Если описатель параметра ссылается на элемент за пределами списка объектов, то во время выполнения создается исключение <xref:System.FormatException>.  
  
### <a name="alignment-component"></a>Выравнивание  
 Необязательный компонент *alignment* — это целое число со знаком, которое служит для указания желательной ширины поля форматирования. Если значение *alignment* меньше длины форматируемой строки, то *alignment* пропускается, и в качестве значения ширины поля используется длина форматируемой строки. Форматируемые данные выравниваются в поле по правому краю, если *alignment* имеет положительное значение, или по левому краю, если *alignment* имеет отрицательное значение. При необходимости отформатированная строка дополняется пробелами. При использовании компонента *alignment* необходимо поставить запятую.  
  
 В примере ниже определяются два массива: один содержит имена сотрудников, а второй — количество часов, которые они проработали в течение двух недель. Строка составного формата выравнивает имена по левому краю 20-символьного поля, а часы работы — по правому краю 5-символьного поля. Обратите внимание, что строка стандартного формата "N1" также используется для форматирования часов с одной цифрой дробной части.  
  
 [!code-csharp[Formatting.Composite#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/alignment1.cs#8)]
 [!code-vb[Formatting.Composite#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/alignment1.vb#8)]  
  
### <a name="format-string-component"></a>Компонент строки формата  
 Необязательный компонент *formatString* — это строка формата, соответствующая типу форматируемого объекта. Если соответствующий объект является объектом <xref:System.DateTime>, используется строка стандартного или настраиваемого формата чисел, а если соответствующий объект является значением перечисления, используется [строка формата перечисления](../../../docs/standard/base-types/enumeration-format-strings.md). Если компонент *formatString* не задан, то для числовых значений, значений даты и времени, а также перечислений используется общий формат ("G"). При использовании компонента *formatString* необходимо двоеточие.  
  
 В следующей таблице перечислены типы и категории типов в библиотеке классов .NET Framework, которые поддерживают предопределенный набор строк формата, а также ссылки на разделы, в которых перечисляются поддерживаемые строки формата. Обратите внимание, что форматирование строк — это расширяемый механизм, который позволяет определять новые строки формата для всех существующих типов, а также определять набор строк формата, поддерживаемых прикладным типом. Подробнее см. в разделах, посвященных интерфейсам <xref:System.IFormattable> и <xref:System.ICustomFormatter>.  
  
|Тип или категория типов|См.|  
|---------------------------|---------|  
|Типы даты и времени (<xref:System.DateTime>, <xref:System.DateTimeOffset>)|[Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)<br /><br /> [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|  
|Типы перечисления (все типы, производные от <xref:System.Enum?displayProperty=nameWithType>)|[Строки форматов перечисления](../../../docs/standard/base-types/enumeration-format-strings.md)|  
|Числовые типы (<xref:System.Numerics.BigInteger>, <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>)|[Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md)<br /><br /> [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md)|  
|<xref:System.Guid>|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.TimeSpan>|[Строки стандартного формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md)<br /><br /> [Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md)|  
  
### <a name="escaping-braces"></a>Оформление фигурных скобок  
 Начало и конец элемента форматирования обозначаются соответственно открывающей и закрывающей фигурной скобкой. Это означает, что для вывода открывающих и закрывающих фигурных скобок необходимо использовать escape-последовательности. Для вывода открывающей или закрывающей фигурной скобки в фиксированном тексте следует поставить две открывающие или, соответственно, закрывающие фигурные скобки подряд ("{{" или "}}"). Фигурные скобки в элементе форматирования интерпретируются последовательно в порядке их обнаружения. Интерпретация вложенных скобок не поддерживается.  
  
 Порядок интерпретации скобок может привести к непредвиденным результатам. Например, рассмотрим элемент форматирования "{{{{0:D}}}}", который должен вывести открывающую фигурную скобку, числовое значение, отформатированное в десятичном виде, и закрывающую фигурную скобку. В действительности элемент форматирования будет интерпретирован следующим образом:  
  
1. Первые две открывающие фигурные скобки ("{{") составляют escape-последовательность, которая дает в итоге одиночную открывающую фигурную скобку.  
  
2. Следующие три знака ("{0:") воспринимаются как начало элемента форматирования.  
  
3. Следующий знак ("D") должен интерпретироваться как указатель на десятичный числовой формат, но стоящая за ним пара фигурных скобок ("}}") дает в результате одиночную фигурную скобку. Поскольку результирующая строка ("D}") не является стандартным описателем числового формата, то она будет интерпретирована как строка пользовательского формата, что приведет к выводу строки "D}".  
  
4. Последняя фигурная скобка ("}") интерпретируется как конец элемента форматирования.  
  
5. Итоговый результат, который будет выведен — строка "{D}". Числовое значение, которое требовалось отформатировать, выведено не будет.  
  
 Одним из способов избежать неправильной интерпретации фигурных скобок и элементов форматирования при написании кода является раздельное форматирование фигурных скобок и элементов форматирования. Это означает, что первая операция форматирования должна выводить строку с открывающей фигурной скобкой, следующая операция — результат обработки элемента форматирования, а последняя операция — строку с закрывающей фигурной скобкой. Этот подход показан в приведенном ниже примере.  
  
 [!code-csharp[Formatting.Composite#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Escaping1.cs#2)]
 [!code-vb[Formatting.Composite#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Escaping1.vb#2)]  
  
### <a name="processing-order"></a>Порядок обработки  
 Если вызов метода составного форматирования содержит аргумент <xref:System.IFormatProvider>, значение которого не равно `null`, среда выполнения вызывает метод <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>, чтобы запросить реализацию <xref:System.ICustomFormatter>. Если метод может возвращать реализацию <xref:System.ICustomFormatter>, он кэшируется на время вызова метода составного форматирования.
  
 Каждое значение в списке параметров, соответствующее элементу форматирования, преобразуется в строку следующим образом:  
  
1. Если форматируемое значение является значением `null`, возвращается пустая строка <xref:System.String.Empty?displayProperty=nameWithType>.  
  
2. Если реализация <xref:System.ICustomFormatter> доступна, среда выполнения вызывает ее метод <xref:System.ICustomFormatter.Format%2A>. Она передает в метод значение элемента форматирования *formatString* (при его наличии) или значение `null` (в случае его отсутствия) вместе с реализацией <xref:System.IFormatProvider>. Если вызов метода <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> возвращает `null`, выполнение переходит к следующему шагу; в противном случае возвращается результат вызова <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>.
  
3. Если значение реализует интерфейс <xref:System.IFormattable>, вызывается метод <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29> этого интерфейса. Методу передается значение *formatString* (при его наличии в элементе форматирования) или значение `null` (в случае его отсутствия). Аргумент <xref:System.IFormatProvider> определяется следующим образом:  
  
    - Для числового значения, если вызывается метод составного форматирования с аргументом <xref:System.IFormatProvider>, не равным null, то среда выполнения запрашивает объект <xref:System.Globalization.NumberFormatInfo> из метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. Если не удалось предоставить объект, если аргумент имеет значение `null` или метод составного форматирования не имеет параметра <xref:System.IFormatProvider>, то используется объект <xref:System.Globalization.NumberFormatInfo> для языка и региональных параметров текущего потока.  
  
    - Для значения даты и времени, если вызывается метод составного форматирования с аргументом <xref:System.IFormatProvider>, не равным null, то среда выполнения запрашивает объект <xref:System.Globalization.DateTimeFormatInfo> из метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. Если не удалось предоставить объект, если аргумент имеет значение `null` или метод составного форматирования не имеет параметра <xref:System.IFormatProvider>, то используется объект <xref:System.Globalization.DateTimeFormatInfo> для языка и региональных параметров текущего потока.  
  
    - Для объектов других типов, если метод составного форматирования вызывается с аргументом <xref:System.IFormatProvider>, то его значение передается непосредственно в реализацию <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>. В противном случае `null` передается в реализацию <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>.  
  
4. Вызывается метод `ToString` без параметров, который переопределяет <xref:System.Object.ToString?displayProperty=nameWithType> или наследует поведение базового класса. В этом случае строка формата, указанная в компоненте *formatString* в элементе форматирования (при его наличии), игнорируется.  
  
 После выполнения предшествующих шагов производится выравнивание.  
  
## <a name="code-examples"></a>Примеры кода  
 В приведенном ниже примере одна строка создается с помощью составного форматирования, а другая – с помощью метода `ToString`. Оба способа форматирования дают идентичные результаты.  
  
 [!code-csharp[Formatting.Composite#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#3)]
 [!code-vb[Formatting.Composite#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#3)]  
  
 Предположим, что сейчас май, а текущий день недели — четверг. Тогда значение обеих строк в предыдущем примере будет `Thursday May` для языка и региональных параметров "Английский (США)".  
  
 Метод <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> предоставляет те же функциональные возможности, что и метод <xref:System.String.Format%2A?displayProperty=nameWithType>. Единственное различие между этими двумя методами состоит в том, что метод <xref:System.String.Format%2A?displayProperty=nameWithType> возвращает результаты в виде строки, а метод <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> записывает результаты в поток вывода, связанный с объектом <xref:System.Console>. В следующем примере для форматирования значения переменной <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> в виде денежного значения используется метод `MyInt`.  
  
 [!code-csharp[Formatting.Composite#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#4)]
 [!code-vb[Formatting.Composite#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#4)]  
  
 В следующем примере демонстрируется форматирование нескольких объектов, в том числе форматирование одного и того же объекта двумя разными способами.  
  
 [!code-csharp[Formatting.Composite#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#5)]
 [!code-vb[Formatting.Composite#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#5)]  
  
 В следующем примере показывается использование выравнивания при форматировании. Форматируемые аргументы разделены знаками вертикальной черты ("|"), которые иллюстрируют выравнивание.  
  
 [!code-csharp[Formatting.Composite#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#6)]
 [!code-vb[Formatting.Composite#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#6)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Console.WriteLine%2A>
- <xref:System.String.Format%2A?displayProperty=nameWithType>
- [Интерполяция строк (C#)](../../csharp/language-reference/tokens/interpolated.md)
- [Интерполяция строк (Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)
- [Типы форматирования](../../../docs/standard/base-types/formatting-types.md)
- [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
- [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Строки стандартного формата TimeSpan](../../../docs/standard/base-types/standard-timespan-format-strings.md)
- [Строки настраиваемого формата TimeSpan](../../../docs/standard/base-types/custom-timespan-format-strings.md)
- [Строки форматов перечисления](../../../docs/standard/base-types/enumeration-format-strings.md)
