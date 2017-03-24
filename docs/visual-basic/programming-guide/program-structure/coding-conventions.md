---
title: "Соглашения о написании кода Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5712f14d53b86552a0b82af38ecf579577ef3fa1
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-coding-conventions"></a>Соглашения о написании кода в Visual Basic
Корпорация Майкрософт разрабатывает примеры и документация, следуйте рекомендациям в этом разделе. Если следовать тем же правилам написания кода, могут получить следующие преимущества:  
  
-   Код будет иметь согласованный вид, чтобы читателям лучше сосредоточиться на содержимом, а не на макете.  
  
-   Читателям понимание кода более быстро, так как они могут делать предположения, основанные на опыте.  
  
-   Можно скопировать, изменение и обслуживание кода проще.  
  
-   Позволяет убедиться, что код демонстрирует «рекомендации» для Visual Basic.  
  
## <a name="naming-conventions"></a>Соглашения об именах  
  
-   Сведения о правилах именования см. в разделе [правила именования](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) раздела.  
  
-   Не использовать «Мои» или «my» как часть имени переменной. Такой подход создает путаницу с `My` объектов.  
  
-   Необходимо изменить имена объектов в автоматически сгенерированный код, чтобы сделать их соответствующими рекомендациям.  
  
## <a name="layout-conventions"></a>Соглашения о расположении  
  
-   Вставка табуляции в качестве пробелов и использовать интеллектуальных отступов с помощью отступов четыре пробела.  
  
-   Используйте **красивое оформление код (форматирование) из** переформатировать кода в редакторе кода. Дополнительные сведения см. в разделе [параметры, текстовый редактор, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Использование только одного оператора в строке. Не используйте знак разделителя строки Visual Basic (:).  
  
-   Избегайте использования символа продолжения строки явную «_» пользу неявное продолжение строки там, где язык допускает его.  
  
-   Используйте только одного объявления в строке.  
  
-   Если **красивое оформление код (форматирование) из** не продолжения строки формата автоматически, вручную отступ продолжения строки должен быть одним символом табуляции. Тем не менее всегда влево элементов в списке.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Добавьте по крайней мере одной пустой строки между определениями методов и свойств.  
  
## <a name="commenting-conventions"></a>Соглашения о комментариях  
  
-   Поместите комментарии на отдельной строке, а не в конце строки кода.  
  
-   Текст комментария с прописной буквы и end текст, содержащий точку начала.  
  
-   Вставьте один пробел между разделителем комментария (') и текстом комментария.  
  
     [!code-vb[VbVbalrGuidelines&#2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   Не заключайте комментарии с звездочек.  
  
## <a name="program-structure"></a>Структура программы  
  
-   При использовании `Main` метода, используйте конструктор по умолчанию для новых консольных приложений и использовать `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines&#3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>Рекомендации по работе с языком  
  
### <a name="string-data-type"></a>Тип данных String  
  
-   Для объединения строк, используйте амперсанд (&).  
  
     [!code-vb[VbVbalrGuidelines&#4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   Для добавления строк в циклы, используйте <xref:System.Text.StringBuilder>объекта.</xref:System.Text.StringBuilder>  
  
     [!code-vb[VbVbalrGuidelines&#5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>Ослабленные делегаты в обработчиках событий  
 Не присваивайте аргументы (Object и EventArgs) явно обработчикам событий. Если вы не используете аргументы события, переданные в событие (например, отправитель как объект e EventArgs), используйте ослабленные делегаты и пропускайте аргументы событий в коде:  
  
 [!code-vb[VbVbalrGuidelines&#7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>Беззнаковый тип данных  
  
-   Использование `Integer` вместо беззнаковых типов, за исключением того, где они необходимы.  
  
### <a name="arrays"></a>Массивы  
  
-   Используйте короткий синтаксис при инициализации массивов в строке объявления. Например используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines №&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines №&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   Установите обозначение массива, тип, отличный от переменной. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines&#10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines&#12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines&#13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>Используется с ключевым словом  
 При внесении ряда вызовов одного объекта, рассмотрите возможность использования `With` ключевое слово:  
  
 [!code-vb[VbVbalrGuidelines&#15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Использование операторов Try... С помощью инструкций, при использовании обработки исключений и catch  
 Не используйте `On Error Goto`.  
  
### <a name="use-the-isnot-keyword"></a>Используйте ключевое слово IsNot  
 Используйте `IsNot` ключевое слово `Not...Is Nothing`.  
  
### <a name="new-keyword"></a>New-ключевое слово  
  
-   Используйте короткий способ создания экземпляра. Например используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines&#21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines&#22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   Используйте инициализаторы объектов для новых объектов вместо конструкторов:  
  
     [!code-vb[VbVbalrGuidelines&#23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>Обработка событий  
  
-   Используйте `Handles` вместо `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines&#24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   Используйте `AddressOf`и не создавайте экземпляр делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines&#25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines&#26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   Проверяет, является ли событие `Nothing` (null), перед вызовом метода `RaiseEvent` метод. `RaiseEvent`проверяет наличие `Nothing` перед его событие.  
  
### <a name="using-shared-members"></a>Использование общих членов  
 Вызов `Shared` члены с помощью имени класса, а не переменной экземпляра.  
  
### <a name="use-xml-literals"></a>Использование XML-литералов  
 Литералы XML упрощают наиболее распространенных задач, возникающих при работе с XML (например, загрузки, запроса и преобразования). При разработке с использованием XML, придерживайтесь следующих рекомендаций:  
  
-   Используйте литералы XML для создания XML-документов и фрагментов вместо непосредственного вызова интерфейсов API.  
  
-   Импорт пространства имен XML на уровне проект или файл, чтобы воспользоваться преимуществами оптимизации производительности для XML-литералов.  
  
-   Используйте свойства оси XML для доступа к элементам и атрибутам в XML-документ.  
  
-   Использовать внедренные выражения для включения значений и создания XML из существующих значений вместо использования вызовов API, таких как `Add` метод:  
  
     [!code-vb[VbVbalrGuidelines&#27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines&#28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   Укажите имена для элементов в запросе, чтобы убедиться в том, что имена свойств анонимных типов верно используются прописные буквы с помощью языка Pascal регистр:  
  
     [!code-vb[VbVbalrGuidelines&#29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными. Например, если запрос возвращает клиента, имя и идентификатор заказа, переименуйте их не оставляйте как `Name` и `ID` в результате:  
  
     [!code-vb[VbVbalrGuidelines&#30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   Используйте вывод типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines&#31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   Выравнивайте предложения запроса под `From` инструкции:  
  
     [!code-vb[VbVbalrGuidelines&#32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   Используйте `Where` предложения перед другие предложения запроса, чтобы более поздние предложения запроса работают отфильтрованный набор данных:  
  
     [!code-vb[VbVbalrGuidelines&#33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   Используйте `Join` предложение для явного определения операции соединения вместо `Where` предложение для неявного определения операции соединения:  
  
     [!code-vb[VbVbalrGuidelines&#34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
