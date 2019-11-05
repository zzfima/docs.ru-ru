---
title: Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
dev_langs:
- csharp
- vb
ms.openlocfilehash: 51142a168aba4408e6ce550a032960c4df6c3ae7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138733"
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей
Веб-страницы могут отображаться в любой точке мира, поэтому в операциях синтаксического анализа и форматирования значений даты и времени при взаимодействии с пользователем не должен использоваться формат по умолчанию (который обычно определяется форматом языка и региональных параметров, установленным для веб-сервера). Вместо этого при обработке строк даты и времени, вводимых пользователем, веб-формы должны выполнять их синтаксический анализ с учетом значений языка и региональных параметров, установленных для пользователя. Аналогичным образом, отображать данные даты и времени для пользователя следует в формате, соответствующем языку и региональным параметрам пользователя. В настоящем разделе показано, как это делается.  
  
## <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Синтаксический анализ строк даты и времени, вводимых пользователем  
  
1. Определите, заполнен ли массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. Если нет, перейдите к шагу 6.  
  
2. Если массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>, заполнен, извлеките его первый элемент. Первый элемент определяет язык и регион, установленные для пользователя по умолчанию или выбранные им в настройках.  
  
3. Создайте экземпляр объекта <xref:System.Globalization.CultureInfo>, который представляет выбранные пользователем язык и региональные параметры, вызвав конструктор <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4. Вызовите метод `TryParse` или `Parse` для типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, чтобы выполнить преобразование. Используйте перегрузку метода `TryParse` или `Parse` с параметром `provider` и передайте в него один из следующих объектов:  
  
    - объект <xref:System.Globalization.CultureInfo>, созданный на шаге 3;  
  
    - объект <xref:System.Globalization.DateTimeFormatInfo> из свойства <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> объекта <xref:System.Globalization.CultureInfo>, созданного на шаге 3.  
  
5. Если преобразование завершается сбоем, повторите шаги 2–4 поочередно для каждого из остальных элементов в массиве строк, полученных в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6. Если преобразование по-прежнему завершается сбоем или свойство <xref:System.Web.HttpRequest.UserLanguages%2A> содержит пустой массив строк, используйте для синтаксического анализа инвариантные язык и региональные параметры, которые возвращаются в свойстве <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
## <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Синтаксический анализ локальной даты и времени из запроса пользователя  
  
1. Добавьте элемент управления <xref:System.Web.UI.WebControls.HiddenField> в веб-форму.  
  
2. Создайте функцию JavaScript, которая обрабатывает событие `onClick` для кнопки `Submit`, сохраняя в свойство <xref:System.Web.UI.WebControls.HiddenField.Value%2A> текущую дату и время, а также сдвиг часового пояса (разницу между местным часовым поясом и временем в формате UTC). Поместите разделитель (например, точку с запятой) между двумя компонентами строки.  
  
3. Примените событие веб-формы <xref:System.Web.UI.Control.PreRender>, чтобы вставить эту функцию в выходной поток HTML, передав методу <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> текст скрипта.  
  
4. Подключите обработчик событий к событию `onClick`кнопки `Submit`, указав имя функции JavaScript в атрибуте `OnClientClick` кнопки `Submit`.  
  
5. Создайте обработчик для события <xref:System.Web.UI.WebControls.Button.Click> кнопки `Submit`.  
  
6. В этом обработчике определите, заполнен ли массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. Если нет, перейдите к шагу 14.  
  
7. Если массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>, заполнен, извлеките его первый элемент. Первый элемент определяет язык и регион, установленные для пользователя по умолчанию или выбранные им в настройках.  
  
8. Создайте экземпляр объекта <xref:System.Globalization.CultureInfo>, который представляет выбранные пользователем язык и региональные параметры, вызвав конструктор <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
9. Передайте строку, назначенную свойству <xref:System.Web.UI.WebControls.HiddenField.Value%2A>, в метод <xref:System.String.Split%2A>, чтобы сохранить в отдельных элементах массива строковое представление локальной даты и времени пользователя, а также строковое представление сдвига часового пояса пользователя.  
  
10. Вызовите метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> или <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType>, чтобы преобразовать дату и время из запроса пользователя в значение <xref:System.DateTime>. Используйте перегрузку метода с параметром `provider` и передайте в него один из следующих объектов:  
  
    - объект <xref:System.Globalization.CultureInfo>, созданный на шаге 8;  
  
    - объект <xref:System.Globalization.DateTimeFormatInfo> из свойства <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> объекта <xref:System.Globalization.CultureInfo>, созданного на шаге 8.  
  
11. Если операция синтаксического анализа на шаге 10 завершится сбоем, перейдите к шагу 13. В противном случае вызовите метод <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType>, чтобы преобразовать строковое представление сдвига часового пояса пользователя в целое число.  
  
12. Создайте экземпляр объекта <xref:System.DateTimeOffset>, который представляет локальное время пользователя, вызвав конструктор <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType>.  
  
13. Если преобразование на шаге 10 завершается сбоем, повторите шаги 7–12 поочередно для каждого из остальных элементов в массиве строк, полученных в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
14. Если преобразование по-прежнему завершается сбоем или свойство <xref:System.Web.HttpRequest.UserLanguages%2A> содержит пустой массив строк, используйте для синтаксического анализа инвариантные язык и региональные параметры, которые возвращаются в свойстве <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Теперь повторите шаги 7–12.  
  
 В результате вы получите объект <xref:System.DateTimeOffset>, представляющий локальное время пользователя, открывшего вашу веб-страницу. Теперь вы можете определить эквивалентное время в формате UTC, вызвав метод <xref:System.DateTimeOffset.ToUniversalTime%2A>. Также вы можете определить эквивалентные дату и время на веб-сервере, вызвав метод <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> и передав ему значение <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> со значением часового пояса, в которых нужно преобразовать время.  
  
## <a name="example"></a>Пример  
 Следующий пример содержит исходный код HTML и код для веб-формы ASP.NET, который предлагает пользователю ввести значение даты и времени. Кроме того, скрипт на стороне клиента при отправке пользовательского запроса сохраняет в скрытое поле локальные значения даты и времени, а также сдвиг часового пояса пользователя относительно времени в формате UTC. Сервер анализирует эти сведения и возвращает веб-страницу с информацией, введенной пользователем. Также он отображает дату и время запроса пользователя в формате локального времени, времени на сервере и UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Скрипт на стороне клиента вызывает метод JavaScript `toLocaleString`. Этот метод создает строку, которая соответствует правилам форматирования для языкового стандарта пользователя. Это самый надежный метод передать серверу строку, которую тот сможет правильно обработать.  
  
 Свойство <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> заполняется именами языков и региональных параметров, которые содержатся в заголовках `Accept-Language` HTTP-запроса. Но не все браузеры включают в запрос заголовки `Accept-Language`, а пользователь может принудительно запретить такие заголовки. Это означает, что для синтаксического анализа введенных пользователем данных нужен резервный вариант региональных параметров. Обычно в таких случаях используются инвариантные язык и региональные параметры, возвращаемые в свойстве <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. В Internet Explorer пользователи могут вводить имена языков и региональных стандартов в обычное текстовое поле, а значит эти имена могут оказаться недопустимыми. Поэтому при создании экземпляра объекта <xref:System.Globalization.CultureInfo> необходимо обрабатывать исключения.  
  
 Массив <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> заполняется данными, извлеченными из HTTP-запроса, полученного от Internet Explorer, в порядке пользовательских предпочтений. Первый элемент массива содержит основное имя региона или языка и региональных параметров пользователя. Если массив содержит другие элементы, Internet Explorer в произвольном порядке присваивает им описатели качества, отделенные от имени языка и региональных параметров точкой с запятой. Например, запись для языка и региональных параметров fr-FR может принять форму `fr-FR;q=0.7`.  
  
 Этот пример вызывает конструктор <xref:System.Globalization.CultureInfo.%23ctor%2A>, присваивая параметру `useUserOverride` значение `false`, чтобы создать объект <xref:System.Globalization.CultureInfo>. Это означает, что если используется стандартное для сервера имя языка и региональных параметров, конструктор класса создает объект <xref:System.Globalization.CultureInfo> с региональными параметрами по умолчанию без учета настроек, указанных на сервере в приложении  **Язык и региональные стандарты**. Маловероятно, что измененные в настройках сервера значения существуют на компьютере пользователя или учитываются при вводе данных.  
  
 Так как в этом примере выполняется синтаксический анализ двух строковых представлений даты и времени (одно из них вводится пользователем, а другое сохраняется в скрытом поле), мы заранее определяем возможные объекты <xref:System.Globalization.CultureInfo>, которые могут нам потребоваться. Этот код создает массив объектов <xref:System.Globalization.CultureInfo>, число которых на один больше, чем число элементов, возвращаемых свойством <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. Затем код создает отдельный объект <xref:System.Globalization.CultureInfo> для каждой строки языка и региона, а также создает экземпляр объекта <xref:System.Globalization.CultureInfo>, который представляет <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 Код может вызвать метод <xref:System.DateTime.Parse%2A> или <xref:System.DateTime.TryParse%2A>, чтобы преобразовать введенное пользователем строковое представление даты и времени в значение <xref:System.DateTime>. Для одной операции синтаксического анализа может потребоваться несколько вызовов метода Parse. А значит, метод <xref:System.DateTime.TryParse%2A> предпочтителен, ведь при сбое операции синтаксического анализа он возвращает `false`. Обработка же нескольких исключений, которые могут быть созданы в методе <xref:System.DateTime.Parse%2A>, потребует больших затрат при выполнении веб-приложения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот код, создайте веб-страницу ASP.NET без кода программной части. Затем скопируйте наш пример на эту веб-страницу, заменив им весь существующий код. Веб страница ASP.NET должна содержать следующие элементы управления:  
  
- элемент управления <xref:System.Web.UI.WebControls.Label>, который не указан в коде (для его свойства <xref:System.Web.UI.WebControls.TextBox.Text%2A> задайте значение "Введите число:");  
  
- элемент управления <xref:System.Web.UI.WebControls.TextBox> с именем `DateString`;  
  
- элемент управления <xref:System.Web.UI.WebControls.Button> с именем `OKButton`; (для его свойства <xref:System.Web.UI.WebControls.Button.Text%2A> задайте значение "ОК").  
  
- элемент управления <xref:System.Web.UI.WebControls.HiddenField> с именем `DateInfo`;  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы пользователи не могли внедрять скрипты в поток HTML, никогда не передавайте введенные данные напрямую в ответе сервера. Всегда шифруйте ответ с помощью метода <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
- [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Анализ строк даты и времени](../../../docs/standard/base-types/parsing-datetime.md)
