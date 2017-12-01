---
title: "Практическое руководство. Преобразование числовых данных, введенных пользователем в веб-элементах управления, в числа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Практическое руководство. Преобразование числовых данных, введенных пользователем в веб-элементах управления, в числа
Поскольку веб-страницы могут отображаться в любом месте в мире, пользователи могут вводить числовые данные в <xref:System.Web.UI.WebControls.TextBox> управления практически неограниченное число форматов. Поэтому очень важно для определения языкового стандарта и языка и региональных параметров пользователя на веб-странице. При синтаксическом анализе ввод данных пользователем, затем можно применить соглашения о форматировании, определяемый языка и региональных параметров пользователя.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Преобразование входных числовых данных из элемента управления Web TextBox в число  
  
1.  Определить, является ли массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> свойство заполняется. Если это не так, перейдите к шагу 6.  
  
2.  Если массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство заполняется, извлеките его первый элемент. Первый элемент указывает пользователя по умолчанию или предпочитаемый язык и регион.  
  
3.  Создать экземпляр <xref:System.Globalization.CultureInfo> объект, представляющий пользователя предпочитаемый язык и региональные параметры, вызвав <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> конструктор.  
  
4.  Вызвать либо метод `TryParse` или `Parse` метод числового типа, который требуется преобразовать введенные пользователем данные. Используйте перегрузку `TryParse` или `Parse` метод с `provider` параметра и передайте ему один из следующих:  
  
    -   <xref:System.Globalization.CultureInfo> Объекта, созданного на шаге 3.  
  
    -   <xref:System.Globalization.NumberFormatInfo> Объект, возвращаемый <xref:System.Globalization.CultureInfo.NumberFormat%2A> свойство <xref:System.Globalization.CultureInfo> объекта, созданного на шаге 3.  
  
5.  Если преобразование завершается сбоем, повторите шаги 2 – 4 для каждого оставшегося элемента в массиве строк, возвращенных <xref:System.Web.HttpRequest.UserLanguages%2A> свойство.  
  
6.  Если преобразование по-прежнему не удается или массив строк, возвращаемый <xref:System.Web.HttpRequest.UserLanguages%2A> свойство пусто, синтаксический анализ строки с помощью инвариантного языка и региональных параметров, который возвращается методом <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> свойство.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный-страница с выделенным кодом веб-формы, пользователю предлагается ввести числовое значение в <xref:System.Web.UI.WebControls.TextBox> управления и преобразует его в число. Затем это количество вдвое и отображаются с помощью тех же правил форматирования как исходных входных данных.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Свойство заполняется из имен языка и региональных параметров, содержащихся в `Accept-Language` заголовков, включенных в HTTP-запроса. Однако не все браузеры включают в себя `Accept-Language` заголовки запросов, а пользователям можно также полностью запретить заголовки. Это делает важным наличие резервного языка и региональных параметров, если синтаксический анализ вводимых пользователем данных. Обычно резервная языка и региональных параметров является инвариантного языка и региональных параметров, возвращаемых <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Пользователи могут также предоставлять Internet Explorer с именами языка и региональных параметров они введены в текстовое поле, которое возникает вероятность, что имена языка и региональных параметров могут оказаться недопустимыми. Это делает важным использовать обработку исключений при создании экземпляра <xref:System.Globalization.CultureInfo> объекта.  
  
 При извлечении из HTTP-запроса, отправленные в Internet Explorer <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> массив заполняется в порядке предпочтения пользователя. Первый элемент массива содержит имя основного языка и региональных параметров пользователя или региона. Если массив содержит другие элементы, Internet Explorer произвольно назначит им спецификатор качества, который отделяется от имени языка и региональных параметров точкой с запятой. Например, запись региональных параметров fr-FR может принять форму `fr-FR;q=0.7`.  
  
 В примере вызывается <xref:System.Globalization.CultureInfo.%23ctor%2A> конструктор с его `useUserOverride` равным `false` для создания нового <xref:System.Globalization.CultureInfo> объекта. Это гарантирует, что, если имя языка и региональных параметров является имя языка и региональных параметров по умолчанию на сервере нового <xref:System.Globalization.CultureInfo> , созданное конструктором класса объектов содержит региональные параметры по умолчанию и не зависит от настроек, заданных с помощью сервера  **Язык и региональные стандарты** приложения. Значения всех скорректированных настроек на сервере вряд ли существовать на компьютере пользователя или обработать входные данные пользователя.  
  
 Код может вызвать либо метод `Parse` или `TryParse` будут преобразованы в метод числового типа, введенный пользователем. Повторные вызовы метода parse может потребоваться для отдельной операции синтаксического анализа. В результате `TryParse` метода является более эффективным, поскольку он возвращает `false` при сбое операции синтаксического анализа. Напротив, обработка повторяющихся исключений, которые могут быть получены `Parse` метод может быть слишком затратной для веб-приложения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать код, скопируйте его в [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] страница с выделенным кодом, чтобы он заменяет весь существующий код. [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Веб-страница должна содержать следующие элементы управления:  
  
-   Объект <xref:System.Web.UI.WebControls.Label> элемента управления, который не указан в коде. Задайте его <xref:System.Web.UI.WebControls.TextBox.Text%2A> свойства» введите число:».  
  
-   элемент управления <xref:System.Web.UI.WebControls.TextBox> с именем `NumericString`;  
  
-   элемент управления <xref:System.Web.UI.WebControls.Button> с именем `OKButton`; Задайте его <xref:System.Web.UI.WebControls.Button.Text%2A> свойство «ОК».  
  
 Измените имя класса из `NumericUserInput` к имени класса, который определяется `Inherits` атрибут [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] страницы `Page` директивы. Измените имя `NumericInput` ссылки на имя, определенное на объект `id` атрибут [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] страницы `form` тег.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Чтобы предотвратить добавление скрипта в поток HTML, вводимые данные никогда не должны непосредственно передаваться обратно в ответе сервера. Вместо этого они должны быть зашифрованы с помощью <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> метод.  
  
## <a name="see-also"></a>См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Анализ числовых строк](../../../docs/standard/base-types/parsing-numeric.md)
