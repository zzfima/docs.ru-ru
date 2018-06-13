---
title: Соглашения о написании кода в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655365"
---
# <a name="visual-basic-coding-conventions"></a>Соглашения о написании кода в Visual Basic
Корпорация Майкрософт разрабатывает примеров и документации, следуйте указаниям, изложенным в этом разделе. При таком же соглашения о написании кода, может получить следующие преимущества:  
  
-   Код будет иметь согласованный внешний вид, чтобы читатели может лучше сосредоточиться на содержимом, а не на макете.  
  
-   Читатели понимание кода более быстро, так как они могут делать предположения, основанные на опыте.  
  
-   Копирование, изменение и обслуживать код проще.  
  
-   Позволяет убедиться, что коде показано, как «рекомендации» для Visual Basic.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
-   Сведения о рекомендациях по именованию см. в разделе [правила именования](../../../standard/design-guidelines/naming-guidelines.md) раздела.  
  
-   Не используйте «My» или «my» как часть имени переменной. Такой подход создает путаницы с `My` объектов.  
  
-   Необходимо изменить имена объектов в автоматически создаваемый код, чтобы сделать их соответствующими рекомендациям.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  
  
-   Вставка табуляции в качестве пробелов и используйте интеллектуальных отступов с помощью отступов четыре пробела.  
  
-   Используйте **довольно листинг кода (изменения форматирования)** переформатирование кода в редакторе кода. Дополнительные сведения см. в разделе [параметры, текстовый редактор, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Используйте только одну инструкцию в строке. Не используйте знак разделителя строки Visual Basic (:).  
  
-   Избегайте использования символа продолжения явные строки «_» пользу неявное продолжение строки там, где язык позволяет его.  
  
-   Используйте только одно объявление в строке.  
  
-   Если **довольно листинг кода (изменения форматирования)** не продолжения строки формата автоматически, вручную отступ продолжения строки должен быть одним символом табуляции. Однако всегда влево элементов в списке.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Добавьте по крайней мере одной пустой строки между определениями методов и свойств.  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
-   Поместите комментарии на отдельной строке, а не в конце строки кода.  
  
-   Текст комментария с заглавной буквы и end текст, содержащий точку начала.  
  
-   Вставьте один пробел между разделителем комментария (') и текст комментария.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Не заключайте комментарии с звездочек.  
  
## <a name="program-structure"></a>Структура программы  
  
-   При использовании `Main` метода, используйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
  
### <a name="string-data-type"></a>Тип данных String  
  
-   Для объединения строк, используйте амперсанд (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Для добавления строк в циклы, используйте <xref:System.Text.StringBuilder> объекта.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Ослабленные делегаты в обработчиках событий  
 Не определены аргументы (Object и EventArgs) явно обработчикам событий. Если вы не используете аргументы события, которые передаются на событие (например, отправитель как объект e EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
-   Используйте `Integer` вместо беззнаковых типов, за исключением того, где они необходимы.  
  
### <a name="arrays"></a>Массивы  
  
-   Используйте короткий синтаксис при инициализации массивов в строке объявления. Например используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Установите обозначение массива, тип, отличный от переменной. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Используется с ключевым словом  
 Если вы внесли ряд вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Использование Try... С помощью инструкций, при использовании обработки исключений и catch  
 Не используйте `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Используйте ключевое слово IsNot  
 Используйте `IsNot` ключевое слово, а не `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>Новое ключевое слово  
  
-   Используйте короткие при создании экземпляра. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Для новых объектов, а не конструктор без параметров, используйте инициализаторы объектов:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Обработка событий  
  
-   Используйте `Handles` вместо `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Не проверять, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод. `RaiseEvent` проверяет наличие `Nothing` перед его вызывает событие.  
  
### <a name="using-shared-members"></a>Использование общих членов  
 Вызовите `Shared` члены с помощью имени класса, а не переменной экземпляра.  
  
### <a name="use-xml-literals"></a>Использование XML-литералов  
 Литералы XML упрощают наиболее распространенные задачи, которые возникают при работе с XML (например, загрузки, запроса и преобразования). При разработке с использованием XML, придерживайтесь следующих правил:  
  
-   Используйте литералы XML для создания XML-документы и фрагменты вместо непосредственного вызова интерфейсов API.  
  
-   Импорт пространства имен XML на уровне файла или проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.  
  
-   Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документа.  
  
-   Использование внедренных выражений для включения значений и создания XML на основе существующих значений вместо использования вызовов API, таких как `Add` метод:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Укажите имена элементов в запросе, чтобы убедиться в том, что имена свойств анонимных типов верно используются прописные буквы с помощью языка Pascal регистр:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает клиента, имя и идентификатор заказа, переименуйте их не оставляйте их в виде `Name` и `ID` в результате:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Используйте определение типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Выравнивайте предложения запроса под `From` инструкции:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Используйте `Where` перед другие предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Используйте `Join` предложений, чтобы явно определить операцию join, вместо использования `Where` предложение для неявного определения операции соединения:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](../../../standard/security/secure-coding-guidelines.md)
