---
title: Соглашения о написании кода
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: 36cd3a927d2fdf197e6b496d9308fc43a555d59b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346155"
---
# <a name="visual-basic-coding-conventions"></a>Соглашения о написании кода в Visual Basic
Корпорация Майкрософт разрабатывает образцы и документацию, которые соответствуют рекомендациям, приведенным в этом разделе. Если следовать тем же соглашениям о написании кода, вы можете получить следующие преимущества:  
  
- Ваш код будет иметь единообразный вид, чтобы читатели могли лучше сосредоточиться на содержимом, а не на макете.  
  
- Читатели смогут быстрее понять код, так как они могут делать предположения на основе предыдущего опыта.  
  
- Вы можете легко копировать, изменять и обслуживать код.  
  
- Вы сможете убедиться в том, что код демонстрирует "рекомендации" для Visual Basic.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
- Сведения о правилах именования см. в разделе [рекомендации по именованию](../../../standard/design-guidelines/naming-guidelines.md) .  
  
- Не используйте "My" или "My" как часть имени переменной. Такой подход создает путаницу с `My` объектами.  
  
- Не нужно изменять имена объектов в автоматически создаваемом коде, чтобы они соответствовали рекомендациям.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  
  
- Вставьте табуляцию в качестве пробелов и используйте интеллектуальные отступы с отступами в четырех пробелах.  
  
- Чтобы переформатировать код в редакторе кода, используйте **достаточное переформатирование** . Дополнительные сведения см. в разделе [Параметры, текстовый редактор, базовый (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
- Используйте только один оператор в строке. Не используйте Visual Basic символ разделителя строки (:).  
  
- Старайтесь не использовать явный символ продолжения строки "_" в пользу неявного продолжения строки везде, где это разрешено языком.  
  
- Используйте только одно объявление в строке.  
  
- Если **Перечисление (переформатирование) кода** не приводит к автоматическому форматированию строк продолжения, следует вручную задать отступ для строк продолжения на одну позицию табуляции. Однако всегда выровняйте элементы в списке по левому краю.  
  
    ```vb  
    a As Integer,  
    b As Integer  
    ```  
  
- Добавьте хотя бы одну пустую строку между определениями методов и свойств.  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
- Заключите комментарии в отдельную строку, а не в конец строки кода.  
  
- Начинать текст комментария с прописной буквы и заканчивать текст комментария точкой.  
  
- Вставьте один пробел между разделителем комментария (') и текстом комментария.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
- Не заключайте комментарии в форматированные блоки звездочек.  
  
## <a name="program-structure"></a>Структура программы  
  
- При использовании метода `Main` используйте конструкцию по умолчанию для новых консольных приложений и используйте `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
  
### <a name="string-data-type"></a>Тип данных String  
  
- Для сцепления коротких строк рекомендуется использовать [интерполяцию строк](https://docs.microsoft.com/dotnet/visual-basic/programming-guide/language-features/strings/interpolated-strings), как показано в следующем коде.
  
     ```vb
     MsgBox($"hello{vbCrLf}goodbye")
     ```
  
- Чтобы добавить строки в циклы, используйте объект <xref:System.Text.StringBuilder>.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Ослабленные делегаты в обработчиках событий  
 Не следует явно уточнять аргументы (объект и EventArgs) обработчиками событий. Если вы не используете аргументы события, передаваемые в событие (например, отправитель как объект, e как EventArgs), используйте ослабленные делегаты и оставьте аргументы событий в коде:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
- Используйте `Integer`, а не неподписанные типы, за исключением тех случаев, когда они необходимы.  
  
### <a name="arrays"></a>Массивы  
  
- Используйте короткий синтаксис при инициализации массивов в строке объявления. Например, используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
- Установите обозначение массива на тип, а не на переменную. Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
- Используйте синтаксис {} при объявлении и инициализации массивов базовых типов данных. Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Использование ключевого слова WITH  
 При выполнении серии вызовов одного объекта рассмотрите возможность использования ключевого слова `With`:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Используйте параметр try... Перехватывать и использовать операторы при использовании обработки исключений  
 Не используйте `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Использование ключевого слова IsNot  
 Вместо `Not...Is Nothing`используйте ключевое слово `IsNot`.  
  
### <a name="new-keyword"></a>Создать ключевое слово  
  
- Используйте короткий экземпляр. Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
- Используйте инициализаторы объектов для новых объектов вместо конструктора без параметров:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Обработка событий  
  
- Используйте `Handles`, а не `AddHandler`.  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
- Используйте `AddressOf`и не создавайте делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
- При определении события используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
- Не проверяйте, является ли событие `Nothing`ным (null) перед вызовом метода `RaiseEvent`. `RaiseEvent` проверяет наличие `Nothing` перед вызовом события.  
  
### <a name="using-shared-members"></a>Использование общих членов  
 Вызывайте `Shared` членов с помощью имени класса, а не из переменной экземпляра.  
  
### <a name="use-xml-literals"></a>Использовать литералы XML  
 XML-литералы упрощают наиболее распространенные задачи, возникающие при работе с XML (например, Загрузка, запрос и преобразование). При разработке с использованием XML-кода следуйте приведенным ниже рекомендациям.  
  
- Используйте литералы XML для создания XML-документов и фрагментов вместо непосредственного вызова API XML.  
  
- Импортируйте пространства имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.  
  
- Используйте свойства осей XML для доступа к элементам и атрибутам в XML-документе.  
  
- Используйте внедренные выражения для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как метод `Add`:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
- Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
- Укажите имена элементов в запросе, чтобы убедиться, что имена свойств анонимных типов правильно заменяются прописными буквами, используя регистр языка Pascal:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
- Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает имя клиента и идентификатор заказа, переименуйте их вместо того, чтобы покинуть их как `Name` и `ID` в результате:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
- Используйте определение типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
- Выровняйте предложения запроса в операторе `From`:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
- Используйте `Where` предложения перед другими предложениями запроса, чтобы последующие предложения запроса работали с отфильтрованным набором данных:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
- Используйте предложение `Join`, чтобы явно определить операцию объединения вместо использования предложения `Where` для неявного определения операции объединения:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также

- [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)
