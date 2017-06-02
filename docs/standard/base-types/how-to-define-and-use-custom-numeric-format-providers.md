---
title: "Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов | Microsoft Docs"
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
  - "строки пользовательского формата"
  - "строки настраиваемых числовых форматов"
  - "отображение данных даты и времени"
  - "поставщики формата [платформа .NET Framework]"
  - "форматирование [платформа .NET Framework], числа"
  - "форматирование чисел [платформа .NET Framework]"
  - "числа [платформа .NET Framework], строки настраиваемых числовых форматов"
  - "строки числовых форматов [платформа .NET Framework]"
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] предоставляет расширенный контроль над строковым представлением числовых значений.  Он поддерживает следующие возможности для настройки форматов числовых значений:  
  
-   Строки стандартных числовых форматов, которые предоставляют стандартный набор форматов для преобразования чисел в их строковое представление.  Их можно использовать с любым методом числового форматирования, например <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName> с параметром `format`.  Дополнительные сведения см. в разделе [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Строки пользовательских числовых форматов, предоставляющих набор символов, которые могут быть объединены для определения спецификаторов пользовательского числового формата.  Они также могут быть использованы с любым методом числового форматирования, например <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName> с параметром `format`.  Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Настраиваемые объекты <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo>, которые определяют символы и шаблоны форматирования, используемые при отображении строковых представлений числовых значений.  Их можно использовать с любым методом числового форматирования, например <xref:System.Int32.ToString%2A> с параметром `provider`.  Как правило, параметр `provider` используется для указания форматирования, зависящего от региональных параметров.  
  
 В некоторых случаях \(например, когда приложению необходимо отобразить отформатированный номер учетной записи, идентификационный номер или почтовый индекс\) эти три метода неприменимы.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] также позволяет определить объект форматирования, который не является ни <xref:System.Globalization.CultureInfo>, ни объектом <xref:System.Globalization.NumberFormatInfo>, для определения порядка форматирования числовых значений.  Этот раздел содержит подробные инструкции по реализации таких объектов и пример форматирования телефонных номеров.  
  
### Определение поставщика пользовательского формата  
  
1.  Определите класс, который реализует интерфейсы <xref:System.IFormatProvider> и <xref:System.ICustomFormatter>.  
  
2.  Реализуйте метод <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName>.  <xref:System.IFormatProvider.GetFormat%2A> представляет собой метод обратного вызова, который вызывается методом форматирования \(таким как метод [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\) для получения объекта, фактически отвечающего за выполнение пользовательского форматирования.  Обычно реализация метода <xref:System.IFormatProvider.GetFormat%2A> выполняет следующие действия.  
  
    1.  Определяет, представляет ли объект <xref:System.Type>, передаваемый в качестве параметра метода, интерфейс <xref:System.ICustomFormatter>.  
  
    2.  Если параметр представляет собой интерфейс <xref:System.ICustomFormatter>, то метод <xref:System.IFormatProvider.GetFormat%2A> возвращает объект, реализующий интерфейс <xref:System.ICustomFormatter>, который отвечает за предоставление пользовательского форматирования.  Как правило, объект пользовательского форматирования возвращает сам себя.  
  
    3.  Если параметр не представляет собой интерфейс <xref:System.ICustomFormatter>, то метод <xref:System.IFormatProvider.GetFormat%2A> возвращает `null`.  
  
3.  Реализуйте метод <xref:System.ICustomFormatter.Format%2A>.  Этот метод вызывается методом [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> и возвращает строковое представление числа.  Реализация этого метода обычно включает в себя следующее:  
  
    1.  При необходимости убедитесь, что метод предназначен для предоставления служб форматирования, проверив параметр `provider`.  Для объектов форматирования, реализующих <xref:System.IFormatProvider> и <xref:System.ICustomFormatter>, это включает в себя проверку параметра `provider` на равенство с текущим объектом форматирования.  
  
    2.  Определите, должен ли объект форматирования поддерживать спецификаторы пользовательского формата. \(Например, спецификатор формата "N" может указать, что телефонный номер США следует выводить в формате NANP, а "I" может означать вывод по рекомендации ITU\-T формата E.123.\). Если используются спецификаторы формата, то метод должен обрабатывать этот спецификатор определенного формата.  Он передается методу в качестве параметра `format`.  Если спецификатор отсутствует, то значением параметра `format` является <xref:System.String.Empty?displayProperty=fullName>.  
  
    3.  Получите числовое значение, передаваемое в метод в качестве параметра `arg`.  Выполните операции, необходимые для его преобразования в строковое представление.  
  
    4.  Верните строковое представление параметра `arg`.  
  
### Использование объекта пользовательского числового форматирования  
  
1.  Создайте новый экземпляр класса пользовательского форматирования.  
  
2.  Вызовите метод форматирования [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>, передавая ему объект пользовательского форматирования, спецификатор форматирования \(или <xref:System.String.Empty?displayProperty=fullName>, если он не используется\) и числовое значение, подлежащее форматированию.  
  
## Пример  
 В следующем примере определяется поставщик пользовательского числового формата с именем `TelephoneFormatter`, который преобразует число, представляющее номер телефона в США, в формат NANP или E.123.  Метод обрабатывает два спецификатора формата, "N" \(вывод в формате NANP\) и "I" \(вывод в международном формате E.123\).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Поставщик пользовательского числового формата может использоваться только с методом [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  Другие перегрузки методов числового форматирования \(например `ToString`\) с параметром типа <xref:System.IFormatProvider> передают реализацию метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName> для объекта <xref:System.Type>, представляющего тип <xref:System.Globalization.NumberFormatInfo>.  В свою очередь, они ожидают, что метод возвратит объект <xref:System.Globalization.NumberFormatInfo>.  Если это не так, то поставщик пользовательского числового формата игнорируется, и вместо него используется объект <xref:System.Globalization.NumberFormatInfo>, соответствующий текущим региональным параметрам.  В этом примере метод `TelephoneFormatter.GetFormat` обрабатывает вероятность некорректной передачи методу числового форматирования, проверяя параметр метода и возвращая `null`, если он представляет тип, отличный от <xref:System.ICustomFormatter>.  
  
 Если поставщик пользовательского числового формата поддерживает набор спецификаторов формата, убедитесь, что также предоставлено поведение по умолчанию, если спецификатор формата не предоставляется в элементе форматирования, используемом при вызове метода [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  В приведенном примере "N" — это спецификатор формата по умолчанию.  Это позволяет преобразовать число в формат телефонного номера, явно предоставляя спецификатор формата.  В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Но это также позволяет произвести преобразование в случае, если спецификатор формата отсутствует.  В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Если не определен спецификатор формата по умолчанию, то реализация метода <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName> должна содержать код, аналогичный приведенному ниже, чтобы в .NET Framework могло быть представлено форматирование, которое не поддерживается кодом.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 В таком случае в этом примере метод, реализующий <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName>, служит методом обратного вызова для метода [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  Таким образом, он проверяет параметр `formatProvider` на наличие ссылки на текущий объект `TelephoneFormatter`.  Тем не менее, метод можно также вызвать непосредственно из кода.  В этом случае можно использовать параметр `formatProvider` для предоставления <xref:System.Globalization.CultureInfo> или объекта <xref:System.Globalization.NumberFormatInfo>, предоставляющего сведения о форматировании для соответствующих региональных параметров.  
  
## Компиляция кода  
 Откомпилируйте код из командной строки, используя csc.exe или vb.exe.  Чтобы откомпилировать код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)