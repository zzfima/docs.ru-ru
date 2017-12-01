---
title: "Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей
Поскольку веб-страницы могут отображаться в любом месте в мире, операции, которые синтаксического анализа и форматирования значений даты и времени, не следует полагаться на формат по умолчанию (который чаще всего является формат локального языка и региональных параметров веб-сервера) при взаимодействии с пользователем. Вместо этого веб-форм, которые обрабатывают даты и времени строки ввода пользователя следует выполнить синтаксический анализ строк с использованием языка и региональных параметров пользователя. Аналогичным образом данные даты и времени должны отображаться для пользователя в формате, который соответствует языку и региональным параметрам пользователя. В настоящем разделе показано, как это делается.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Для разбора даты и времени строки ввода пользователя  
  
1.  Определить, является ли массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> свойство заполняется. Если это не так, перейдите к шагу 6.  
  
2.  Если массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство заполняется, извлеките его первый элемент. Первый элемент указывает пользователя по умолчанию или предпочитаемый язык и регион.  
  
3.  Создать экземпляр <xref:System.Globalization.CultureInfo> объект, представляющий пользователя предпочитаемый язык и региональные параметры, вызвав <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> конструктор.  
  
4.  Вызвать либо метод `TryParse` или `Parse` метод <xref:System.DateTime> или <xref:System.DateTimeOffset> типа, чтобы выполнить преобразование. Используйте перегрузку `TryParse` или `Parse` метод с `provider` параметра и передайте ему один из следующих:  
  
    -   <xref:System.Globalization.CultureInfo> Объекта, созданного на шаге 3.  
  
    -   <xref:System.Globalization.DateTimeFormatInfo> Объект, возвращаемый <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> свойство <xref:System.Globalization.CultureInfo> объекта, созданного на шаге 3.  
  
5.  Если преобразование завершается сбоем, повторите шаги 2 – 4 для каждого оставшегося элемента в массиве строк, возвращенных <xref:System.Web.HttpRequest.UserLanguages%2A> свойство.  
  
6.  Если преобразование по-прежнему не удается или массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство пусто, синтаксический анализ строки с помощью инвариантного языка и региональных параметров, который возвращается методом <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> свойство.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Для разбора локальной даты и времени запроса пользователя  
  
1.  Добавить <xref:System.Web.UI.WebControls.HiddenField> управления на веб-форму.  
  
2.  Создать функцию JavaScript, которая обрабатывает `onClick` событие `Submit` кнопки, написав текущую дату и время и смещение местного часового пояса от времени UTC в <xref:System.Web.UI.WebControls.HiddenField.Value%2A> свойство. Используйте разделители (например, точка с запятой) для разделения двух компонентов строки.  
  
3.  Использовать веб-формы <xref:System.Web.UI.Control.PreRender> событий для вставки этой функции в HTML, поток вывода, передав текст скрипта <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> метод.  
  
4.  Подключите обработчик событий для `Submit` кнопки `onClick` событий, указав имя функции JavaScript, которая `OnClientClick` атрибут `Submit` кнопки.  
  
5.  Создание обработчика для `Submit` кнопки <xref:System.Web.UI.WebControls.Button.Click> событий.  
  
6.  В обработчике событий, определить, является ли массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> свойство заполняется. Если это не так, перейдите к шагу 14.  
  
7.  Если массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство заполняется, извлеките его первый элемент. Первый элемент указывает пользователя по умолчанию или предпочитаемый язык и регион.  
  
8.  Создать экземпляр <xref:System.Globalization.CultureInfo> объект, представляющий пользователя предпочитаемый язык и региональные параметры, вызвав <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> конструктор.  
  
9. Передайте строку, назначенный <xref:System.Web.UI.WebControls.HiddenField.Value%2A> свойства <xref:System.String.Split%2A> для сохранения строковое представление пользователя локальной даты и времени и строковое представление смещение местного часового пояса пользователя в отдельных элементах массива.  
  
10. Вызвать либо метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> или <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> метод, чтобы преобразовать дату и время запроса пользователя на <xref:System.DateTime> значение. Используйте перегрузку метода с `provider` параметра и передайте ему один из следующих:  
  
    -   <xref:System.Globalization.CultureInfo> Объекта, созданного на шаге 8.  
  
    -   <xref:System.Globalization.DateTimeFormatInfo> Объект, возвращаемый <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> свойство <xref:System.Globalization.CultureInfo> объекта, созданного на шаге 8.  
  
11. Если операция анализа на шаге 10 не удается, перейдите к шагу 13. В противном случае вызов <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> метод для преобразования строкового представления смещения часового пояса пользователя в целое число.  
  
12. Создать экземпляр <xref:System.DateTimeOffset> , представляющий местное время пользователя путем вызова <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType> конструктор.  
  
13. Если преобразование на шаге 10 завершается сбоем, повторите шаги 7 – 12 для каждого оставшегося элемента в массиве строк, возвращенных <xref:System.Web.HttpRequest.UserLanguages%2A> свойство.  
  
14. Если преобразование по-прежнему не удается или массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство пусто, синтаксический анализ строки с помощью инвариантного языка и региональных параметров, который возвращается методом <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> свойство. Повторите шаги 7 – 12.  
  
 В результате <xref:System.DateTimeOffset> , представляющий местное время пользователя на веб-странице. Затем можно определить эквивалент UTC, вызвав <xref:System.DateTimeOffset.ToUniversalTime%2A> метод. Можно также определить эквивалентную дату и время на веб-сервере путем вызова <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> метод и при передаче значения <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> как преобразовать время в часовом поясе.  
  
## <a name="example"></a>Пример  
 Следующий пример содержит исходный код HTML и код для веб-формы ASP.NET с запросом у пользователя ввод значения даты и времени. Клиентский сценарий также записывает сведения о локальной даты и времени запроса пользователя и смещение часового пояса пользователя от времени UTC в скрытое поле. Эти сведения затем анализируется сервером, который возвращает веб-страницы, отображающий входные данные пользователя. Он также отображает дату и время запроса пользователя, с помощью пользователя местное время, время на сервере, а в формате UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Клиентский сценарий вызывает JavaScript `toLocaleString` метод. Это создает строку, которая соответствует правилам форматирования языкового стандарта пользователя, который, скорее всего, будет успешно обработана на сервере.  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Свойство заполняется из имен языка и региональных параметров, содержащихся в `Accept-Language` заголовков, включенных в HTTP-запроса. Однако не все браузеры включают в себя `Accept-Language` заголовки запросов, а пользователям можно также полностью запретить заголовки. Это делает важным наличие резервного языка и региональных параметров, если синтаксический анализ вводимых пользователем данных. Обычно резервная языка и региональных параметров является инвариантного языка и региональных параметров, возвращаемых <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Пользователи могут также предоставлять Internet Explorer с именами языка и региональных параметров они введены в текстовое поле, которое возникает вероятность, что имена языка и региональных параметров могут оказаться недопустимыми. Это делает важным использовать обработку исключений при создании экземпляра <xref:System.Globalization.CultureInfo> объекта.  
  
 При извлечении из HTTP-запроса, отправленные в Internet Explorer <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> массив заполняется в порядке предпочтения пользователя. Первый элемент массива содержит имя основного языка и региональных параметров пользователя или региона. Если массив содержит другие элементы, Internet Explorer произвольно назначит им спецификатор качества, который отделяется от имени языка и региональных параметров точкой с запятой. Например, запись региональных параметров fr-FR может принять форму `fr-FR;q=0.7`.  
  
 В примере вызывается <xref:System.Globalization.CultureInfo.%23ctor%2A> конструктор с его `useUserOverride` равным `false` для создания нового <xref:System.Globalization.CultureInfo> объекта. Это гарантирует, что, если имя языка и региональных параметров является имя языка и региональных параметров по умолчанию на сервере нового <xref:System.Globalization.CultureInfo> , созданное конструктором класса объектов содержит региональные параметры по умолчанию и не зависит от настроек, заданных с помощью сервера  **Язык и региональные стандарты** приложения. Значения всех скорректированных настроек на сервере вряд ли существовать на компьютере пользователя или обработать входные данные пользователя.  
  
 Поскольку в этом примере выполняется разбор двух строковых представлений даты и времени (одно, введенное пользователем, другое, сохраненное в скрытом поле), он определяет возможные <xref:System.Globalization.CultureInfo> объекты, которые могут потребоваться заранее. Создает массив <xref:System.Globalization.CultureInfo> объектов, которыми на единицу больше, чем число элементов, возвращаемых методом <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> свойство. Затем он создает <xref:System.Globalization.CultureInfo> объекта для каждой строки языка или региона, а также создается <xref:System.Globalization.CultureInfo> , представляющий <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 Код может вызвать либо метод <xref:System.DateTime.Parse%2A> или <xref:System.DateTime.TryParse%2A> метод, чтобы преобразовать пользователя строковое представление даты и времени в <xref:System.DateTime> значение. Повторные вызовы метода parse может потребоваться для отдельной операции синтаксического анализа. В результате <xref:System.DateTime.TryParse%2A> метод лучше, поскольку он возвращает `false` при сбое операции синтаксического анализа. Напротив, обработка повторяющихся исключений, которые могут быть получены <xref:System.DateTime.Parse%2A> метод может быть слишком затратной для веб-приложения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, создайте [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] веб-страницы без выделенного кода. Затем скопируйте пример в веб-страницу, чтобы он заменил весь существующий код. [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Веб-страница должна содержать следующие элементы управления:  
  
-   Объект <xref:System.Web.UI.WebControls.Label> элемента управления, который не указан в коде. Задайте его <xref:System.Web.UI.WebControls.TextBox.Text%2A> свойства» введите число:».  
  
-   элемент управления <xref:System.Web.UI.WebControls.TextBox> с именем `DateString`;  
  
-   элемент управления <xref:System.Web.UI.WebControls.Button> с именем `OKButton`; Задайте его <xref:System.Web.UI.WebControls.Button.Text%2A> свойство «ОК».  
  
-   элемент управления <xref:System.Web.UI.WebControls.HiddenField> с именем `DateInfo`;  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы предотвратить добавление скрипта в поток HTML, вводимые данные никогда не должны непосредственно передаваться обратно в ответе сервера. Вместо этого они должны быть зашифрованы с помощью <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> метод.  
  
## <a name="see-also"></a>См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [Анализ строк даты и времени](../../../docs/standard/base-types/parsing-datetime.md)
