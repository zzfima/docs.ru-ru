---
title: "Соглашения о написании кода в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "соглашения о написании кода, Visual Basic"
  - "примеры [Visual Basic], соглашения о написании кода"
  - "код Visual Basic, соглашения"
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 48
---
# Соглашения о написании кода в Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Корпорация Microsoft разрабатывает примеры и документацию, которые следует рекомендациям в этом разделе.  Если вы следуете тем же соглашениям о написании кода, можно получить следующие преимущества:  
  
-   Код будет иметь согласованный вид, позволяющий читателям сосредоточиться на содержимом, а не на форме.  
  
-   Читателям могут делать предположения, основанные на опыте, и поэтому быстрее понимать код.  
  
-   Можно копировать, менять и сопровождать код гораздо проще.  
  
-   Позволяет убедиться, что код демонстрирует «рекомендации» для Visual Basic.  
  
## Соглашения об именах  
  
-   Дополнительные сведения о рекомендациях по именованию см. в разделе [Правила именования](../Topic/Naming%20Guidelines.md).  
  
-   Не используйте "Mу" или "mу" как часть имени переменной.  При этом создается путаница с `My` объектами.  
  
-   Нет необходимости изменять имена объектов в автоматически созданном коде, чтобы привести их в соответствие с правилами.  
  
## Cоглашения о расположении  
  
-   Вставьте табуляции как пробелы и используйте Автоматический отступы с отступами по 4 пробела  
  
-   Используйте команду **Автоматическое форматирование кода**, чтобы переформатировать код в редакторе кода.  Для получения дополнительной информации см. ["Параметры", "Текстовый редактор", Basic \(Visual Basic\)](/visual-studio/ide/reference/options-text-editor-basic-visual-basic).  
  
-   Используйте только одну инструкцию в строке.  Не используйте в Visual Basic символ разделения строки \(:\).  
  
-   Избегайте использования символа явного продолжения строки «\_», лучше неявное продолжение строки, если это позволяет язык.  
  
-   Используйте только одно объявление в строке.  
  
-   Если **Автоматическое форматирование кода** не форматирует строки продолжения автоматически, вручную сделайте отступ строк продолжения на одну позиции табуляции.  Однако всегда выровнять элементы в списке по левому краю.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   Добавьте по крайней мере одну пустую строку между определениями методов и свойств.  
  
## Соглашения о комментариях  
  
-   Размещение комментария в отдельной строке, а не в конце строки кода.  
  
-   Начинайте текст комментария с прописной буквы и заканчивайте текст комментария точкой.  
  
-   Вставьте один пробел между разделителем комментария \('\) и текстом комментария.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#2)]  
  
-   Не окружайте комментарии звездочками.  
  
## Структура программы  
  
-   При использовании метода `Main` применяйте конструктор по умолчанию для новых консольных приложений и используйте `My` для аргументов командной строки.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#3)]  
  
## Правила языка  
  
### Тип данных String  
  
-   Для сцепления строк используйте амперсанд \(&\).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#4)]  
  
-   Для присоединения строк к циклу, используйте объект <xref:System.Text.StringBuilder>:  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#5)]  
  
### Ослабленные делегаты в обработчиках событий  
 Не надо явным образом квалифицировать аргументы \(объект и EventArgs\) обработчикам событий.  Если вы не используете аргументы событий, передаваемые в событие \(например, отправитель как объект, e как EventArgs\), используйте ослабленные делегаты и пропускайте аргументы событий в коде.  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#7)]  
  
### Беззнаковый тип данных  
  
-   Используйте `Integer` вместо беззнаковых типов, за исключением случаев, когда они необходимы.  
  
### Массивы  
  
-   Рекомендуется использовать краткий синтаксис при инициализации массивов в строке объявления.  Например, используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#8)]  
  
     Не используйте следующий синтаксис.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#9)]  
  
-   Установите обозначение массива как тип, а не как переменную.  Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#11)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#10)]  
  
-   Используйте синтаксис {} при объявлении и инициализации массивов основных типов данных.  Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#12)]  
  
     Не используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#13)]  
  
### Используйте ключевое слово With  
 При выполнении ряда вызовов одного объекта, рассмотрите возможность использования ключевого слова `With`:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#15)]  
  
### Использование операторов Try...Catch и Using для обработки исключений  
 Не используйте `On Error Goto`.  
  
### Используйте ключевое слово IsNot  
 Вместо `Not...Is Nothing`, используйте ключевое слово `IsNot`.  
  
### Ключевое слово New  
  
-   Используйте короткий способ создания экземпляра.  Например, используйте следующий синтаксис:  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#21)]  
  
     Предыдущая строка эквивалентна следующей:  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#22)]  
  
-   Используйте инициализаторы объектов для новых объектов вместо конструкторов без параметров:  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#23)]  
  
### Обработка событий  
  
-   Используйте `Handles` вместо `AddHandler`.  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#24)]  
  
-   Используйте `AddressOf` и не создавайте экземпляр делегата явным образом:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#25)]  
  
-   При определении события, используйте короткий синтаксис и позвольте компилятору определить делегат:  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#26)]  
  
-   Не проверяйте, возникает ли событие `Nothing` \(null\) перед вызовом метода `RaiseEvent`.  Метод `RaiseEvent` проверит наличие `Nothing` перед тем, как он вызовет событие.  
  
### Использование общих членов  
 Вызывайте `Shared` члены с помощью имени класса, а не переменной экземпляра.  
  
### Использование XML\-литералов  
 Литералы XML упрощают большинство общих задач, с которыми можно столкнуться при работе с XML \(например, загрузка, запрос и преобразование\).  При разработке с использованием XML, следуйте данным принципам:  
  
-   Используйте литералы XML для создания XML\-документов и фрагментов вместо прямого вызова интерфейсов API.  
  
-   Импортируйте пространство имен XML в файл или на уровень проекта, чтобы воспользоваться преимуществами оптимизации производительности для XML\-литералов.  
  
-   Используйте свойства оси XML для обращения к элементам и атрибутам в XML\-документе.  
  
-   Используйте внедренные выражения для включения значений и создания XML из существующих значений вместо использования вызовов API, таких как метод `Add`:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#27)]  
  
### Запросы LINQ  
  
-   Используйте значимые имена для переменных запроса:  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#28)]  
  
-   Обозначайте элементы запроса именами, чтобы быть уверенным, что имена свойств анонимных типов правильно капитализированы при помощи правил использования прописных и строчных букв языка Pascal:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#29)]  
  
-   Переименуйте свойства, если имена свойств в результате могут быть неоднозначными.  Например, если запрос возвращает имя клиента и идентификатор заказа, не оставляйте их имена в виде `Name` и `ID`, а переименуйте их:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#30)]  
  
-   Используйте определение типа в объявлении переменных запроса и переменных диапазона:  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#31)]  
  
-   Выровняйте предложения запроса в операторе `From`:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#32)]  
  
-   Используйте предложения `Where` перед другими предложениями запроса, чтобы более поздние предложения будут работать с отфильтрованными наборами данных:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#33)]  
  
-   Используйте предложение `Join` для явного определения операции соединения вместо использования предложения `Where` для неявного определения операции соединения:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/visualbasic/VBProject/Class1.vb#34)]  
  
## См. также  
 [Secure Coding Guidelines](../Topic/Secure%20Coding%20Guidelines.md)