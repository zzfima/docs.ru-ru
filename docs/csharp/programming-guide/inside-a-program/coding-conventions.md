---
title: "Соглашения о написании кода на C# (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a>Соглашения о написании кода на C# (Руководство по программированию на C#)
[Спецификация языка C#](http://go.microsoft.com/fwlink/?LinkId=199552) не определяет стандарт кодирования. Однако корпорация Майкрософт использует приведенные в этом разделе рекомендации для разработки примеров и документации.  
  
 Соглашения о написании кода предназначены для реализации следующих целей.  
  
-   Создание согласованного вида кода, позволяющего читателям сосредоточиться на содержимом, а не на структуре.  
  
-   Предоставление читателям возможности делать предположения, основанные на опыте, и поэтому быстрее понимать код.  
  
-   Упрощение процессов копирования, изменения и обслуживания кода.  
  
-   Предоставление лучших методик C#.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
-   В коротких примерах, не содержащих [директив using](../../../csharp/language-reference/keywords/using-directive.md), рекомендуется использовать полные указания для пространства имен. Если известно, что пространство имен импортировано в проект по умолчанию, не требуется указывать полные имена из этого пространства имен. Полные имена, если они слишком длинные для одной строки, можно разбить после точки (.), как показано в следующем примере.  
  
     [!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]  
  
-   Нет необходимости изменять имена объектов, созданных с помощью инструментов разработки Visual Studio, чтобы привести их в соответствие с другими соглашениями.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  
 Чтобы выделить структуру кода и облегчить чтение кода, в хорошем макете используется форматирование. Примеры и образцы корпорации Майкрософт соответствуют следующим соглашениям.  
  
-   Использование параметров редактора кода по умолчанию (логичные отступы, отступы по четыре символа, использование пробелов для табуляции). Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор", C#, "Форматирование"](/visualstudio/ide/reference/options-text-editor-csharp-formatting).  
  
-   Запись только одного оператора в строке.  
  
-   Запись только одного объявления в строке.  
  
-   Если отступ для дополнительных строк не ставится автоматически, необходимо сделать для них отступ на одну позицию табуляции (четыре пробела).  
  
-   Добавление по крайней мере одной пустой строки между определениями методов и свойств.  
  
-   Использование скобок для ясности предложений в выражениях, как показано в следующем коде.  
  
     [!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
-   Комментарий размещается на отдельной строке, а не в конце строки кода.  
  
-   Текст комментария начинается с заглавной буквы.  
  
-   Текст комментария завершается точкой.  
  
-   Между разделителем комментария (/ /) и текстом комментария вставляется один пробел, как показано в следующем примере.  
  
     [!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]  
  
-   Вокруг комментариев не должно быть звездочек.  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
 В следующих подразделах описаны методики, которыми руководствуется команда C# для подготовки примеров и образцов кода.  
  
### <a name="string-data-type"></a>Тип данных String  
  
-   Для сцепления коротких строк рекомендуется использовать оператор `+`, как показано в следующем коде.  
  
     [!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]  
  
-   Для добавления строк в циклы, особенно при работе с текстами больших размеров, рекомендуется использовать объект <xref:System.Text.StringBuilder>.  
  
     [!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]  
  
### <a name="implicitly-typed-local-variables"></a>Неявно типизированные локальные переменные  
  
-   В случаях, когда тип переменной понятен из правой части назначения или когда точный тип не важен, рекомендуется использовать [неявное типизирование](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) для локальных переменных.  
  
     [!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]  
  
-   Если тип из правой части назначения не является очевидным, не рекомендуется использовать [var](../../../csharp/language-reference/keywords/var.md).  
  
     [!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]  
  
-   При указании типа переменной не следует полагаться на имя переменной. Имя может быть неверным.  
  
     [!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]  
  
-   Рекомендуется избегать использования `var` вместо [dynamic](../../../csharp/language-reference/keywords/dynamic.md).  
  
-   Рекомендуется использовать неявное типизирование для определения типа переменной цикла в циклах [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
     В следующем примере неявное типизирование используется в операторе `for`.  
  
     [!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]  
  
     В следующем примере неявное типизирование используется в операторе `foreach`.  
  
     [!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
-   Как правило, рекомендуется использовать `int` вместо беззнаковых типов. В C# обычно используется `int`. Использование `int` упрощает взаимодействие с другими библиотеками.  
  
### <a name="arrays"></a>Массивы  
  
-   При инициализации массивов в строке объявления рекомендуется использовать сокращенный синтаксис.  
  
     [!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]  
  
### <a name="delegates"></a>Делегаты  
  
-   Для создания экземпляров типа делегата рекомендуется использовать сокращенный синтаксис.  
  
     [!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a>Операторы try-catch и using в процессе обработки исключений  
  
-   Рекомендуется использовать оператор [try-catch](../../../csharp/language-reference/keywords/try-catch.md) для обработки большей части исключений.  
  
     [!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]  
  
-   Использование [оператора C# using](../../../csharp/language-reference/keywords/using-statement.md) упрощает код. При наличии оператора [try-finally](../../../csharp/language-reference/keywords/try-finally.md), код которого в блоке `finally` содержит только вызов метода <xref:System.IDisposable.Dispose%2A>, вместо него рекомендуется использовать оператор `using`.  
  
     [!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]  
  
### <a name="-and-124124-operators"></a>Операторы && и ||  
  
-   Чтобы избежать возникновения исключений и увеличить производительность за счет пропуска необязательных сравнений, рекомендуется использовать [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) вместо [&](../../../csharp/language-reference/operators/and-operator.md) и [||](../../../csharp/language-reference/operators/conditional-or-operator.md) вместо [|](../../../csharp/language-reference/operators/or-operator.md) при выполнении сравнений, как показано в следующем примере.  
  
     [!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]  
  
### <a name="new-operator"></a>Оператор New  
  
-   Рекомендуется использовать сокращенную форму создания экземпляра для объекта с неявным типизированием, как показано в следующем объявлении.  
  
     [!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]  
  
     Предыдущая строка соответствует следующему объявлению.  
  
     [!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]  
  
-   Рекомендуется использовать инициализаторы объектов для упрощения создания объектов.  
  
     [!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]  
  
### <a name="event-handling"></a>Обработка событий  
  
-   При определении обработчика событий, которого не требуется удалять позднее, рекомендуется использовать лямбда-выражение.  
  
     [!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]  
  
     [!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]  
  
### <a name="static-members"></a>Статический члены  
  
-   Для вызова [статических](../../../csharp/language-reference/keywords/static.md) членов следует использовать имя класса: *ClassName.StaticMember*. В этом случае код становится более удобочитаемым за счет четкого доступа.  Не присваивайте статическому члену, определенному в базовом классе, имя производного класса.  Во время компиляции кода его читаемость нарушается, и если добавить статический член с тем же именем в производный классе, код может быть поврежден.  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса. В следующем примере используется `seattleCustomers` для клиентов, находящихся в Сиэтле.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Рекомендуется использовать псевдонимы для уверенности в том, что в именах свойств анонимных типов верно используются прописные буквы при помощи правил использования прописных и строчных букв языка Pascal.  
  
     [!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает имя клиента и идентификатор распространителя, не оставляйте имена в виде `Name` и `ID`, а переименуйте их, чтобы было ясно, что `Name` — имя клиента и `ID` — идентификатор распространителя.  
  
     [!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]  
  
-   Рекомендуется использовать неявное типизирование в объявлении переменных запроса и переменных диапазона.  
  
     [!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]  
  
-   Выравнивайте предложения запроса под предложением [from](../../../csharp/language-reference/keywords/from-clause.md), как показано в предыдущих примерах.  
  
-   Чтобы гарантировать, что более поздние предложения запроса работают с ограниченным, отфильтрованным набором данных, используйте предложение [where](../../../csharp/language-reference/keywords/where-clause.md) перед другими предложениями запроса.  
  
     [!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]  
  
-   Используйте несколько предложений `from` для доступа к внутренним коллекциям вместо предложения [join](../../../csharp/language-reference/keywords/join-clause.md). Например, коллекция объектов `Student` может содержать коллекцию результатов тестирования. При выполнении следующего запроса возвращаются результаты, превышающие 90 балов, а также фамилии учащихся, получивших такие оценки.  
  
     [!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]  
  
## <a name="security"></a>Безопасность  
 Следуйте указаниям, изложенным в [правилах написания безопасного кода](../../../standard/security/secure-coding-guidelines.md).  
  
## <a name="see-also"></a>См. также  
 [Соглашения о написании кода в Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)   
 [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)

