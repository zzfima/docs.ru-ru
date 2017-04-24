---
title: "Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "отображение данных даты и времени"
  - "форматирование [платформа .NET Framework], даты"
  - "форматирование [платформа .NET Framework], локализованные данные"
  - "локализация [платформа .NET Framework], отображение даты и времени"
  - "отображение локализованных дат [платформа .NET Framework]"
  - "разбор строк [платформа .NET Framework], строки даты и времени"
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Отображение сведений о локализованной дате и времени для веб-пользователей
Поскольку веб\-страница может отображаться в любой точке мира, то при взаимодействии с пользователем операции, которые производят разбор и форматирование значений даты и времени, не должны базироваться на формате по умолчанию \(которым чаще всего является формат локального веб\-сервера\).  Вместо этого, веб\-формы, которые обрабатывают строки даты и времени, введенные пользователем, должны производить разбор строк с использованием выбранных пользователем языка и региональных параметров.  Аналогично данные о дате и времени следует отображать пользователю в формате, который соответствует его пользовательскому языку и региональным параметрам.  В этом разделе показано, как это сделать.  
  
### Для разбора строк даты и времени, введенных пользователем  
  
1.  Определите, заполняется ли массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>.  Если это не так, то перейдите к шагу 6.  
  
2.  Если массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A> заполнен, то извлеките его первый элемент.  Первый элемент указывает на язык и регион по умолчанию или выбранный пользователем.  
  
3.  Создайте объект <xref:System.Globalization.CultureInfo>, представляющий выбранные пользователем региональные параметры, путем вызова конструктора <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
4.  Вызовите метод `TryParse`, либо метод `Parse` типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, чтобы выполнить преобразование.  Используйте перегрузку метода `TryParse` или `Parse` с параметром `provider` и передайте ему один из следующих объектов:  
  
    -   Объект <xref:System.Globalization.CultureInfo>, созданный на шаге 3.  
  
    -   Объект <xref:System.Globalization.DateTimeFormatInfo>, возвращаемый свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> объекта <xref:System.Globalization.CultureInfo>, созданного на шаге 3.  
  
5.  Если выполнить преобразование не удалось, повторите шаги со второго по четвертый для каждого оставшегося элемента в массиве строк, возвращаемого свойством <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6.  Если преобразование по\-прежнему не удается или массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A> пуст, произведите разбор строки с использованием инвариантных региональных параметров, которые возвращаются свойством <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
### Для разбора локальной даты и времени запроса пользователя  
  
1.  Добавьте элемент управления <xref:System.Web.UI.WebControls.HiddenField> в веб\-форму.  
  
2.  Создайте функцию JavaScript, которая будет обрабатывать событие `onClick` от кнопки `Submit`, записывая текущую дату и время, а также смещение местного часового пояса от универсального синхронизированного времени \(UTC\) в свойство <xref:System.Web.UI.WebControls.HiddenField.Value%2A>.  Используйте разделители \(такие как точка с запятой\) для разделения двух компонентов строки.  
  
3.  Используйте событие <xref:System.Web.UI.Control.PreRender> веб\-формы для вставки этой функции в выходной поток HTML, передав текст скрипта методу <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
4.  Соедините обработчик событий с событием `onClick` кнопки `Submit`, предоставив имя функции JavaScript атрибуту `OnClientClick` кнопки `Submit`.  
  
5.  Создайте обработчик для события <xref:System.Web.UI.WebControls.Button.Click> кнопки `Submit`.  
  
6.  В обработчике событий определите, заполняется ли массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>.  Если это не так, то перейдите к шагу 14.  
  
7.  Если массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A> заполнен, то извлеките его первый элемент.  Первый элемент указывает на язык и регион по умолчанию или выбранный пользователем.  
  
8.  Создайте объект <xref:System.Globalization.CultureInfo>, представляющий выбранные пользователем региональные параметры, путем вызова конструктора <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
9. Передайте строку, присвоенную свойству <xref:System.Web.UI.WebControls.HiddenField.Value%2A>, методу <xref:System.String.Split%2A> для сохранения строкового представления локальной даты и времени пользователя и строкового представления смещения местного часового пояса пользователя в отдельных элементах массива.  
  
10. Вызовите либо метод <xref:System.DateTime.Parse%2A?displayProperty=fullName>, либо метод <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=fullName> для преобразования даты и времени запроса пользователя в значение <xref:System.DateTime>.  Используйте перегруженный метод с параметром `provider` и передайте ему одно из нижеследующего:  
  
    -   Объект <xref:System.Globalization.CultureInfo>, созданный на шаге 8.  
  
    -   Объект <xref:System.Globalization.DateTimeFormatInfo>, возвращаемый свойством <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> объекта <xref:System.Globalization.CultureInfo>, созданного на шаге 8.  
  
11. Если операция анализа на шаге 10 завершается сбоем, перейдите к шагу 13.  В противном случае вызовите метод <xref:System.UInt32.Parse%28System.String%29?displayProperty=fullName> для преобразования строкового представления смещения часового пояса пользователя в целое число.  
  
12. Создайте экземпляр <xref:System.DateTimeOffset>, представляющий локальное время пользователя, вызвав конструктор <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=fullName>.  
  
13. Если преобразование на шаге 10 не удалось, то повторите шаги с 7 по 12 для каждого оставшегося элемента в массиве строк, возвращаемого свойством <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
14. Если преобразование по\-прежнему не удается или массив строк, возвращаемый свойством <xref:System.Web.HttpRequest.UserLanguages%2A> пуст, произведите разбор строки с использованием инвариантных региональных параметров, которые возвращаются свойством <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Затем повторите шаги с 7 по 12.  
  
 В результате появится объект <xref:System.DateTimeOffset>, представляющий локальное время пользователя веб\-страницы.  Затем можно определить эквивалент UTC, вызвав метод <xref:System.DateTimeOffset.ToUniversalTime%2A>.  Можно также определить эквивалентную дату и время на веб\-сервере, вызвав метод <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> и передав ему значение <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> как часовой пояс, к которому требуется преобразовать время.  
  
## Пример  
 Следующий пример содержит исходный код HTML и код для веб\-формы ASP.NET, который запрашивает у пользователя ввод значения даты и времени.  Клиентский скрипт записывает сведения о локальной дате и времени запроса пользователя, а также смещение часового пояса пользователя от времени UTC в скрытое поле.  Эти сведения затем анализируются сервером, который возвращает веб\-страницу, отображающую введенные пользователем данные.  Она также отображает дату и время запроса пользователя, используя локальное время пользователя, время на сервере и время UTC.  
  
 <!-- TODO: review snippet reference [!code-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]  -->
 <!-- TODO: review snippet reference [!code-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]  -->  
  
 Клиентский скрипт вызывает метод JavaScript `toLocaleString`.  Он создает строку, которая соответствует правилам форматирования локальной системы пользователя, которая, вероятнее всего, будет успешно обработана на сервере.  
  
 Свойство <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> заполняется на основании имен региональных параметров, содержащихся в заголовках `Accept-Language`, включенных в HTTP\-запрос.  Однако не все браузеры включают заголовки `Accept-Language` в свои запросы, кроме того, пользователи могут полностью запретить заголовки.  В связи с этим при разборе данных, введенных пользователем, возникает необходимость иметь резервный набор региональных параметров.  Обычно резервный язык и региональные параметры являются инвариантными региональными параметрами, возвращаемые <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Пользователи также могут ввести в Internet Explorer название языка и региональных параметров, которое они вводят в текстовое поле, а это создает вероятность того, что такое название может оказаться недопустимым.  Всвязи с этим возникает необходимость обработки исключений при создании объекта <xref:System.Globalization.CultureInfo>.  
  
 При извлечении из HTTP\-запроса, посланного Internet Explorer, массив <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> заполняется в порядке, определенном в пользовательских настройках.  Первый элемент массива содержит название основного национального языка\/региона пользователя.  Если массив содержит другие элементы, то Internet Explorer произвольно назначит им спецификатор качества, который отделяется от имени региональных параметров точкой с запятой.  Например, запись региональных параметров fr\-FR может принять форму `fr-FR;q=0.7`.  
  
 В примере вызывается конструктор <xref:System.Globalization.CultureInfo.%23ctor%2A> с параметром `useUserOverride` с настройкой `false`для создания нового объекта <xref:System.Globalization.CultureInfo>.  В этом случае, если региональные параметры по умолчанию используются на сервере, то новый объект <xref:System.Globalization.CultureInfo>, созданный конструктором класса, содержит все региональные параметры по умолчанию и не зависит от настроек, заданных при помощи серверного приложения **Язык и региональные параметры**.  Значения всех скорректированных настроек на сервере вряд ли появятся на компьютере пользователя или отразятся в данных, введенных пользователем.  
  
 Поскольку в этом примере выполняется разбор двух строковых представлений даты и времени \(одно, введенное пользователем, другое, сохраненное в скрытом поле\), то здесь определяются возможные объекты <xref:System.Globalization.CultureInfo>, которые могут понадобиться заранее.  Создается массив объектов <xref:System.Globalization.CultureInfo>, который содержит на один элемент больше, чем число элементов, возвращенных свойством <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>.  Затем создается объект <xref:System.Globalization.CultureInfo> для каждой строки языка\/региона, а также создается объект <xref:System.Globalization.CultureInfo>, представляющий <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
 Код может вызывать либо метод <xref:System.DateTime.Parse%2A>, либо метод <xref:System.DateTime.TryParse%2A> для преобразования пользовательского строкового представления даты и времени в значение <xref:System.DateTime>.  Для отдельной операции разбора может потребоваться повторный вызов метода синтаксического анализа.  В результате метод <xref:System.DateTime.TryParse%2A> оказывается эффективней, поскольку он возвращает `false` при ошибке в выполнении операции синтаксического анализа.  Напротив, обработка повторяющихся исключений, которые могут посылаться методом <xref:System.DateTime.Parse%2A>, может быть слишком дорогостоящей задачей для веб\-приложений.  
  
## Компиляция кода  
 Для компиляции кода создайте веб\-страницу [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] без программной части \(code\-behind\).  Затем скопируйте пример в веб\-страницу таким образом, чтобы он заменил весь существующий код.  Веб\-страница [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] должна содержать следующие элементы управления:  
  
-   Элемент управления <xref:System.Web.UI.WebControls.Label>, который не указан в коде.  Присвойте его свойству <xref:System.Web.UI.WebControls.TextBox.Text%2A> значение "Введите число:".  
  
-   Элемент управления <xref:System.Web.UI.WebControls.TextBox> с именем `DateString`.  
  
-   Элемент управления <xref:System.Web.UI.WebControls.Button> с именем `OKButton`.  Присвойте его свойству <xref:System.Web.UI.WebControls.Button.Text%2A> значение "ОК".  
  
-   Элемент управления <xref:System.Web.UI.WebControls.HiddenField> с именем `DateInfo`.  
  
## Безопасность платформы .NET Framework  
 Чтобы предостеречь пользователя от добавления скрипта в поток HTML, вводимые пользователем данные никогда не должны непосредственно передаваться обратно в ответе сервера.  Вместо этого они должны быть зашифрованы с помощью метода <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName>.  
  
## См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Строки стандартных форматов даты и времени](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)   
 [Разбор строк даты и времени](../../../docs/standard/base-types/parsing-datetime.md)