---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: e036792cf33082fa78cf243887b8ac7db7f8ad5a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981495"
---
# <a name="visual-basic-coding-conventions"></a>Соглашения о написании кода в Visual Basic
Корпорация Microsoft разрабатывает примеры и документация, следуйте указаниям, изложенным в этом разделе. Если следовать тем же правилам кодирования, может получить следующие преимущества:  
  
-   Код будет иметь согласованный вид, таким образом, чтобы читателям сосредоточиться на содержимом, а не на макете.  
  
-   Читателям понять ваш код более быстро, так как они могут делать предположения, основанные на опыте.  
  
-   Можно скопировать, изменить и сохранить код проще.  
  
-   Позволяет убедиться, что код демонстрирует «рекомендации» для Visual Basic.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
-   Сведения о рекомендациях по именованию см. в разделе [рекомендации по именованию](../../../standard/design-guidelines/naming-guidelines.md) раздела.  
  
-   Не используйте «Mу» или «my» как часть имени переменной. Этом создается путаница с `My` объектов.  
  
-   У вас нет необходимости изменять имена объектов в автоматически созданный код, чтобы сделать их соответствие с правилами.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  
  
-   Вставьте табуляции как пробелы и используйте автоматический отступы с 4 пробела.  
  
-   Используйте **автоматическое форматирование (переформатирование) кода** чтобы переформатировать код в редакторе кода. Дополнительные сведения см. в разделе ["Параметры", "Текстовый редактор, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Используйте только одну инструкцию в строке. Не используйте Visual Basic символ разделения строки (:).  
  
-   Избегайте использования символа продолжения явные строки «_» лучше неявное продолжение строки, везде, где это позволяет язык.  
  
-   Используйте только одно объявление в строке.  
  
-   Если **автоматическое форматирование (переформатирование) кода** не форматирует строки продолжения автоматически, вручную отступ продолжения строки одним символом табуляции. Тем не менее всегда влево элементов в списке.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Добавьте по крайней мере одну пустую строку между определениями методов и свойств.  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
-   Размещение комментария в отдельной строке, а не в конце строки кода.  
  
-   Текст комментария с прописной буквы и заканчивайте текст комментария точкой начала.  
  
-   Вставьте один пробел между разделителем комментария (') и текстом комментария.  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
-   Не окружайте комментарии звездочками.  
  
## <a name="program-structure"></a>Структура программы  
  
-   При использовании `Main` метод, применяйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
  
### <a name="string-data-type"></a>Тип данных String  
  
-   Для объединения строк, используется амперсанд (&).  
  
     [!code-vb[VbVbalrGuidelines#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#4)]  
  
-   Для добавления строк в циклы, рекомендуется использовать <xref:System.Text.StringBuilder> объекта.  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Ослабленные делегаты в обработчиках событий  
 Не надо явным образом квалифицировать аргументы (объект и EventArgs) обработчикам событий. Если вы не используете аргументы события, которые передаются на событие (например, отправитель как объект, e как EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
-   Используйте `Integer` вместо беззнаковых типов, за исключением случаев, когда они необходимы.  
  
### <a name="arrays"></a>Массивы  
  
-   Используйте короткий синтаксис при инициализации массивов в строке объявления. Например используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
-   Установите обозначение массива как тип, а не на переменную. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
-   Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a>Используется с ключевым словом  
 При выполнении ряда вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Использование операторов Try... Catch и операторы Using при использовании обработки исключений  
 Не используйте `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Используйте ключевое слово IsNot  
 Используйте `IsNot` ключевое слово `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Новое ключевое слово  
  
-   Используйте короткий способ создания экземпляра. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
-   Используйте инициализаторы объектов для новых объектов вместо конструкторов:  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a>Обработка событий  
  
-   Используйте `Handles` вместо `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
-   Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
-   При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
-   Не проверять, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод. `RaiseEvent` проверяет наличие `Nothing` прежде, чем он вызывает событие.  
  
### <a name="using-shared-members"></a>Использование общих членов  
 Вызовите `Shared` члены с помощью имени класса, а не переменной экземпляра.  
  
### <a name="use-xml-literals"></a>Использование XML-литералов  
 Литералы XML упрощают наиболее распространенных задач, возникающих при работе с XML (например, нагрузки, запроса и преобразования). При разработке с использованием XML, придерживайтесь следующих рекомендаций.  
  
-   Используйте литералы XML для создания XML-документов и фрагментов вместо прямого вызова интерфейсов API.  
  
-   Импортируйте пространство имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.  
  
-   Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документа.  
  
-   Используйте внедренные выражения для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как `Add` метод:  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
-   Обозначайте элементы в запросе, чтобы убедиться в том, что имена свойств анонимных типов правильно капитализированы при помощи языка Pascal регистр:  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает клиента, имя и идентификатор заказа, переименовать их вместо использования их в виде `Name` и `ID` в результате:  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
-   Используйте определение типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
-   Выравнивайте предложения запроса под `From` инструкции:  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
-   Используйте `Where` предложения перед другими предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
-   Используйте `Join` предложение для явного определения операции соединения вместо использования `Where` предложение для неявного определения операции соединения:  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также
- [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)
