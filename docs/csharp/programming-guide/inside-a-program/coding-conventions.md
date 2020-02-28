---
title: Руководство по программированию на C#. Соглашения о написании кода на C#
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 77b173a420f26834855e0bdca3c8d04406ac65d4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452010"
---
# <a name="c-coding-conventions-c-programming-guide"></a>Соглашения о написании кода на C# (Руководство по программированию на C#)

Соглашения о написании кода предназначены для реализации следующих целей.  
  
- Создание согласованного вида кода, позволяющего читателям сосредоточиться на содержимом, а не на структуре.  
  
- Предоставление читателям возможности делать предположения, основанные на опыте, и поэтому быстрее понимать код.  
  
- Упрощение процессов копирования, изменения и обслуживания кода.  
  
- Предоставление лучших методик C#.  

Майкрософт использует приведенные в этой статье рекомендации для разработки примеров и документации.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
- В коротких примерах, не содержащих [директив using](../../language-reference/keywords/using-directive.md), рекомендуется использовать полные указания для пространства имен. Если известно, что пространство имен импортировано в проект по умолчанию, не требуется указывать полные имена из этого пространства имен. Полные имена, если они слишком длинные для одной строки, можно разбить после точки (.), как показано в следующем примере.  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- Нет необходимости изменять имена объектов, созданных с помощью инструментов разработки Visual Studio, чтобы привести их в соответствие с другими соглашениями.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  

Чтобы выделить структуру кода и облегчить чтение кода, в хорошем макете используется форматирование. Примеры и образцы корпорации Майкрософт соответствуют следующим соглашениям.  
  
- Использование параметров редактора кода по умолчанию (логичные отступы, отступы по четыре символа, использование пробелов для табуляции). Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор", C#, "Форматирование"](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
- Запись только одного оператора в строке.  
  
- Запись только одного объявления в строке.  
  
- Если отступ для дополнительных строк не ставится автоматически, необходимо сделать для них отступ на одну позицию табуляции (четыре пробела).  
  
- Добавление по крайней мере одной пустой строки между определениями методов и свойств.  
  
- Использование скобок для ясности предложений в выражениях, как показано в следующем коде.  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
- Комментарий размещается на отдельной строке, а не в конце строки кода.  
  
- Текст комментария начинается с заглавной буквы.  
  
- Текст комментария завершается точкой.  
  
- Между разделителем комментария (/ /) и текстом комментария вставляется один пробел, как показано в следующем примере.  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- Вокруг комментариев не должно быть звездочек.  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  

В следующих подразделах описаны методики, которыми руководствуется команда C# для подготовки примеров и образцов кода.  
  
### <a name="string-data-type"></a>Тип данных String  
  
- Для сцепления коротких строк рекомендуется использовать [интерполяцию строк](../../language-reference/tokens/interpolated.md), как показано в следующем коде.  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- Для добавления строк в циклы, особенно при работе с текстами больших размеров, рекомендуется использовать объект <xref:System.Text.StringBuilder>.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a>Неявно типизированные локальные переменные  
  
- В случаях, когда тип переменной понятен из правой части назначения или когда точный тип не важен, рекомендуется использовать [неявное типизирование](../classes-and-structs/implicitly-typed-local-variables.md) для локальных переменных.  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- Если тип из правой части назначения не является очевидным, не рекомендуется использовать [var](../../language-reference/keywords/var.md).  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- При указании типа переменной не следует полагаться на имя переменной. Имя может быть неверным.  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- Рекомендуется избегать использования `var` вместо [dynamic](../../language-reference/builtin-types/reference-types.md).  
  
- Рекомендуется использовать неявное типизирование для определения типа переменной цикла в циклах [for](../../language-reference/keywords/for.md).  
  
     В следующем примере неявное типизирование используется в операторе `for`.  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- Не используйте неявное типизирование для определения типа переменной цикла в циклах [foreach](../../language-reference/keywords/foreach-in.md).

     В следующем примере явное типизирование используется в операторе `foreach`.

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > Следите за тем, чтобы случайно не изменить тип элемента итерируемой коллекции. Например, можно легко переключиться с <xref:System.Linq.IQueryable?displayProperty=nameWithType> на <xref:System.Collections.IEnumerable?displayProperty=nameWithType> в инструкции `foreach`, изменяющей выполнение запроса.

### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
Как правило, рекомендуется использовать `int` вместо беззнаковых типов. В C# обычно используется `int`. Использование `int` упрощает взаимодействие с другими библиотеками.  
  
### <a name="arrays"></a>Массивы  
  
При инициализации массивов в строке объявления рекомендуется использовать сокращенный синтаксис.  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a>Делегаты  
  
Для создания экземпляров типа делегата рекомендуется использовать сокращенный синтаксис.  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>Операторы try-catch и using в процессе обработки исключений  
  
- Рекомендуется использовать оператор [try-catch](../../language-reference/keywords/try-catch.md) для обработки большей части исключений.  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- Использование [оператора C# using](../../language-reference/keywords/using-statement.md) упрощает код. При наличии оператора [try-finally](../../language-reference/keywords/try-finally.md), код которого в блоке `finally` содержит только вызов метода <xref:System.IDisposable.Dispose%2A>, вместо него рекомендуется использовать оператор `using`.  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a>Операторы && и ||  
  
Чтобы избежать возникновения исключений и увеличить производительность за счет пропуска необязательных сравнений, рекомендуется использовать [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) вместо [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) и [||](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) вместо [|](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) при выполнении сравнений, как показано в следующем примере.  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a>Оператор New  
  
- Рекомендуется использовать сокращенную форму создания экземпляра для объекта с неявным типизированием, как показано в следующем объявлении.  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     Предыдущая строка соответствует следующему объявлению.  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- Рекомендуется использовать инициализаторы объектов для упрощения создания объектов.  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a>Обработка событий  
  
При определении обработчика событий, которого не требуется удалять позднее, рекомендуется использовать лямбда-выражение.  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a>Статический члены  
  
Для вызова [статических](../../language-reference/keywords/static.md) членов следует использовать имя класса: *ClassName.StaticMember*. В этом случае код становится более удобочитаемым за счет четкого доступа.  Не присваивайте статическому члену, определенному в базовом классе, имя производного класса.  Во время компиляции кода его читаемость нарушается, и если добавить статический член с тем же именем в производный классе, код может быть поврежден.  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
- Используйте значимые имена для переменных запроса. В следующем примере используется `seattleCustomers` для клиентов, находящихся в Сиэтле.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Рекомендуется использовать псевдонимы для уверенности в том, что в именах свойств анонимных типов верно используются прописные буквы при помощи правил использования прописных и строчных букв языка Pascal.  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает имя клиента и идентификатор распространителя, не оставляйте имена в виде `Name` и `ID`, а переименуйте их, чтобы было ясно, что `Name` — имя клиента и `ID` — идентификатор распространителя.  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- Рекомендуется использовать неявное типизирование в объявлении переменных запроса и переменных диапазона.  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- Выравнивайте предложения запроса под предложением [from](../../language-reference/keywords/from-clause.md), как показано в предыдущих примерах.  
  
- Чтобы гарантировать, что более поздние предложения запроса работают с ограниченным, отфильтрованным набором данных, используйте предложение [where](../../language-reference/keywords/where-clause.md) перед другими предложениями запроса.  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- Используйте несколько предложений `from` для доступа к внутренним коллекциям вместо предложения [join](../../language-reference/keywords/join-clause.md). Например, коллекция объектов `Student` может содержать коллекцию результатов тестирования. При выполнении следующего запроса возвращаются результаты, превышающие 90 балов, а также фамилии учащихся, получивших такие оценки.  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a>Безопасность  

Следуйте указаниям, изложенным в [правилах написания безопасного кода](../../../standard/security/secure-coding-guidelines.md).  
  
## <a name="see-also"></a>См. также

- [Соглашения о написании кода в Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)
