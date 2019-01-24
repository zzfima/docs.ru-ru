---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f2b1676ae959c5426af3021bbd340980115c5da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724886"
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
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Не окружайте комментарии звездочками.  
  
## <a name="program-structure"></a>Структура программы  
  
-   При использовании `Main` метод, применяйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
  
### <a name="string-data-type"></a>Тип данных String  
  
-   Для объединения строк, используется амперсанд (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Для добавления строк в циклы, рекомендуется использовать <xref:System.Text.StringBuilder> объекта.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Ослабленные делегаты в обработчиках событий  
 Не надо явным образом квалифицировать аргументы (объект и EventArgs) обработчикам событий. Если вы не используете аргументы события, которые передаются на событие (например, отправитель как объект, e как EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
-   Используйте `Integer` вместо беззнаковых типов, за исключением случаев, когда они необходимы.  
  
### <a name="arrays"></a>Массивы  
  
-   Используйте короткий синтаксис при инициализации массивов в строке объявления. Например используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Установите обозначение массива как тип, а не на переменную. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Используется с ключевым словом  
 При выполнении ряда вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Использование операторов Try... Catch и операторы Using при использовании обработки исключений  
 Не используйте `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Используйте ключевое слово IsNot  
 Используйте `IsNot` ключевое слово `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Новое ключевое слово  
  
-   Используйте короткий способ создания экземпляра. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Используйте инициализаторы объектов для новых объектов вместо конструкторов:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Обработка событий  
  
-   Используйте `Handles` вместо `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Не проверять, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод. `RaiseEvent` проверяет наличие `Nothing` прежде, чем он вызывает событие.  
  
### <a name="using-shared-members"></a>Использование общих членов  
 Вызовите `Shared` члены с помощью имени класса, а не переменной экземпляра.  
  
### <a name="use-xml-literals"></a>Использование XML-литералов  
 Литералы XML упрощают наиболее распространенных задач, возникающих при работе с XML (например, нагрузки, запроса и преобразования). При разработке с использованием XML, придерживайтесь следующих рекомендаций.  
  
-   Используйте литералы XML для создания XML-документов и фрагментов вместо прямого вызова интерфейсов API.  
  
-   Импортируйте пространство имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.  
  
-   Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документа.  
  
-   Используйте внедренные выражения для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как `Add` метод:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Обозначайте элементы в запросе, чтобы убедиться в том, что имена свойств анонимных типов правильно капитализированы при помощи языка Pascal регистр:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает клиента, имя и идентификатор заказа, переименовать их вместо использования их в виде `Name` и `ID` в результате:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Используйте определение типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Выравнивайте предложения запроса под `From` инструкции:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Используйте `Where` предложения перед другими предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Используйте `Join` предложение для явного определения операции соединения вместо использования `Where` предложение для неявного определения операции соединения:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>См. также
- [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)
