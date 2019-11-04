---
title: Практическое руководство. Преобразование числовых данных, введенных пользователем в веб-элементах управления, в числа
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
ms.openlocfilehash: 78ba284ad2e75b39c0fb1001b0f65b48c519dbb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140105"
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Практическое руководство. Преобразование числовых данных, введенных пользователем в веб-элементах управления, в числа
Веб-страницы могут отображаться в любой части света, а значит пользователи будут вводить числовые данные в элемент управления <xref:System.Web.UI.WebControls.TextBox> в самых разных форматах. Поэтому очень важно правильно определить язык и региональные параметры каждого посетителя веб-страницы. Тогда вы сможете применить соглашения о форматировании, соответствующие языку и региональным параметрам пользователя, при синтаксическом анализе вводимых данных.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Преобразование входных данных из элемента управления Web TextBox в числовое значение  
  
1. Определите, заполнен ли массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. Если нет, перейдите к шагу 6.  
  
2. Если массив строк, возвращаемый в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>, заполнен, извлеките его первый элемент. Первый элемент определяет язык и регион, установленные для пользователя по умолчанию или выбранные им в настройках.  
  
3. Создайте экземпляр объекта <xref:System.Globalization.CultureInfo>, который представляет выбранные пользователем язык и региональные параметры, вызвав конструктор <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4. Вызовите метод `TryParse` или `Parse` для числового типа, в который вы хотите преобразовать пользовательские данные. Используйте перегрузку метода `TryParse` или `Parse` с параметром `provider` и передайте в него один из следующих объектов:  
  
    - объект <xref:System.Globalization.CultureInfo>, созданный на шаге 3;  
  
    - объект <xref:System.Globalization.NumberFormatInfo> из свойства <xref:System.Globalization.CultureInfo.NumberFormat%2A> объекта <xref:System.Globalization.CultureInfo>, созданного на шаге 3.  
  
5. Если преобразование завершается сбоем, повторите шаги 2–4 поочередно для каждого из остальных элементов в массиве строк, полученных в свойстве <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6. Если все преобразования завершатся сбоем или свойство <xref:System.Web.HttpRequest.UserLanguages%2A> вернет пустой массив строк, используйте для синтаксического анализа инвариантные язык и региональные параметры, которые возвращаются в свойстве <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример кода программной части для веб-формы, которая предлагает пользователю ввести числовое значение в элемент управления <xref:System.Web.UI.WebControls.TextBox>, а затем преобразует эти данные в число. Затем программа удваивает полученное число и отображает его с использованием тех же правил форматирования, которые применялись для входных данных.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 Свойство <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> заполняется именами языков и региональных параметров из заголовков `Accept-Language`, включенных в HTTP-запрос. Но не все браузеры включают в запрос заголовки `Accept-Language`, а пользователь может принудительно запретить такие заголовки. Это означает, что для синтаксического анализа введенных пользователем данных требуется наличие языка и региональных параметров по умолчанию. Обычно в таких случаях используются инвариантные язык и региональные параметры, возвращаемые в свойстве <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. В Internet Explorer пользователи могут вводить имена языков и региональных стандартов в обычное текстовое поле, а значит эти имена могут оказаться недопустимыми. Поэтому при создании экземпляра объекта <xref:System.Globalization.CultureInfo> необходимо обрабатывать исключения.  
  
 Массив <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> заполняется данными, извлеченными из HTTP-запроса, полученного от Internet Explorer, в порядке пользовательских предпочтений. Первый элемент массива содержит основное имя региона или языка и региональных параметров пользователя. Если массив содержит другие элементы, Internet Explorer в произвольном порядке присваивает им описатели качества, отделенные от имени языка и региональных параметров точкой с запятой. Например, запись для языка и региональных параметров fr-FR может принять форму `fr-FR;q=0.7`.  
  
 Этот пример вызывает конструктор <xref:System.Globalization.CultureInfo.%23ctor%2A>, присваивая параметру `useUserOverride` значение `false`, чтобы создать объект <xref:System.Globalization.CultureInfo>. Это означает, что если используется стандартное для сервера имя языка и региональных параметров, конструктор класса создает объект <xref:System.Globalization.CultureInfo> с региональными параметрами по умолчанию без учета настроек, указанных на сервере в приложении  **Язык и региональные стандарты**. Маловероятно, что измененные в настройках сервера значения будут сохранены на компьютере пользователя или учтены при вводе данных.  
  
 Вы можете вызвать метод `Parse` или `TryParse` для того числового типа, в который вы намерены преобразовать введенные данные. Для одной операции синтаксического анализа может потребоваться несколько вызовов метода parse. А значит, метод `TryParse` предпочтителен, ведь при сбое операции синтаксического анализа он возвращает `false`. Обработка же нескольких исключений, которые могут быть созданы в методе `Parse`, потребует больших затрат при выполнении веб-приложения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его в файл кода программной части ASP.NET, заменив этим текстом весь существующий код. Веб страница ASP.NET должна содержать следующие элементы управления:  
  
- элемент управления <xref:System.Web.UI.WebControls.Label>, который не указан в коде (для его свойства <xref:System.Web.UI.WebControls.TextBox.Text%2A> задайте значение "Введите число:");  
  
- элемент управления <xref:System.Web.UI.WebControls.TextBox> с именем `NumericString`;  
  
- элемент управления <xref:System.Web.UI.WebControls.Button> с именем `OKButton`; (для его свойства <xref:System.Web.UI.WebControls.Button.Text%2A> задайте значение "ОК").  
  
 Замените имя класса `NumericUserInput` именем класса, которое определено в атрибуте `Inherits` директивы `Page` страницы ASP.NET. Замените имя ссылки на объект `NumericInput` именем, которое определено в атрибуте `id` тега `form` страницы ASP.NET.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы пользователи не могли внедрять скрипты в поток HTML, никогда не передавайте введенные данные напрямую в ответе сервера. Всегда шифруйте ответ с помощью метода <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Анализ числовых строк](../../../docs/standard/base-types/parsing-numeric.md)
