---
title: "Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов"
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
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Практическое руководство. Определение и использование настраиваемых поставщиков числовых форматов
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Предоставляет расширенный контроль над строковым представлением числовых значений. Эта платформа поддерживает указанные далее возможности для настройки форматов числовых значений.  
  
-   Строки стандартных числовых форматов, которые предоставляют стандартный набор форматов для преобразования чисел в их строковое представление. Их можно использовать с любым методом числового форматирования, такие как <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, который имеет `format` параметра. Дополнительные сведения см. в разделе [строки стандартного числового формата](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Строки настраиваемых числовых форматов, предоставляющих набор символов, которые могут быть объединены для определения описателей настраиваемого числового формата. Они также могут использоваться с любым методом числового форматирования, такие как <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, который имеет `format` параметра. Дополнительные сведения см. в разделе [строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Настраиваемый <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo> объектов, которые определяют символы и шаблоны, используемые при отображении строковые представления числовых значений форматирования. Их можно использовать с любым методом числового форматирования, такие как <xref:System.Int32.ToString%2A>, который имеет `provider` параметра. Как правило `provider` параметр используется для указания форматирования, зависящего от языка и региональных параметров.  
  
 В некоторых случаях (например, когда приложению необходимо отобразить отформатированный номер учетной записи, идентификационный номер или почтовый индекс) эти три метода неприменимы. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Также позволяет определить объект форматирования, который не является ни <xref:System.Globalization.CultureInfo> , ни <xref:System.Globalization.NumberFormatInfo> объектом, чтобы определить способ форматирования числового значения. Этот раздел содержит пошаговые инструкции по реализации таких объектов и пример форматирования телефонных номеров.  
  
### <a name="to-define-a-custom-format-provider"></a>Определение поставщика пользовательского формата  
  
1.  Определите класс, который реализует <xref:System.IFormatProvider> и <xref:System.ICustomFormatter> интерфейсов.  
  
2.  Выполните метод <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A>метод обратного вызова, метод форматирования (например, <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метод) вызывается для получения объекта, который фактически отвечает за выполнение пользовательского форматирования. Типичная реализация <xref:System.IFormatProvider.GetFormat%2A> делает следующее:  
  
    1.  Определяет, является ли <xref:System.Type> объект, переданный в качестве метода представляет параметр <xref:System.ICustomFormatter> интерфейса.  
  
    2.  Если параметр представляет <xref:System.ICustomFormatter> интерфейс, <xref:System.IFormatProvider.GetFormat%2A> возвращает объект, реализующий интерфейс <xref:System.ICustomFormatter> интерфейс, который отвечает за предоставление пользовательского форматирования. Как правило, объект пользовательского форматирования возвращает сам себя.  
  
    3.  Если параметр не представляет <xref:System.ICustomFormatter> интерфейс, <xref:System.IFormatProvider.GetFormat%2A> возвращает `null`.  
  
3.  Выполните метод <xref:System.ICustomFormatter.Format%2A>. Этот метод вызывается методом <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метод и возвращает строковое представление числа. Реализация этого метода обычно включает в себя выполнение следующих действий.  
  
    1.  При необходимости убедитесь, что метод предназначен для предоставления служб форматирования, проверив `provider` параметра. Для форматирования объектов, реализующих <xref:System.IFormatProvider> и <xref:System.ICustomFormatter>, это включает в себя проверку `provider` параметра на равенство с текущим объектом форматирования.  
  
    2.  Определите, должен ли объект форматирования поддерживать описатели настраиваемого формата. (Например, описатель формата "N" может указывать, что телефонный номер США следует выводить в формате NANP, а "I" может означать вывод в формате E.123 в соответствии с рекомендацией ITU-T.) Если используются описатели формата, то метод должен обрабатывать этот описатель определенного формата. Он передается методу в `format` параметра. Если спецификатор отсутствует, значение `format` параметр <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3.  Числовое значение, передаваемое в качестве метода получения `arg` параметра. Выполните операции, необходимые для его преобразования в строковое представление.  
  
    4.  Возвращает строковое представление `arg` параметра.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Использование объекта настраиваемого числового форматирования  
  
1.  Создайте новый экземпляр класса настраиваемого форматирования.  
  
2.  Вызовите <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метода форматирования, передавая ему объект пользовательского форматирования, спецификатор форматирования (или <xref:System.String.Empty?displayProperty=nameWithType>, если он не используется), а числовое значение для форматирования.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется поставщик настраиваемого числового формата с именем `TelephoneFormatter`, который преобразует число, представляющее номер телефона в США, в формат NANP или E.123. Метод обрабатывает два описателя формата "N" (вывод в формате NANP) и "I" (вывод в международном формате E.123).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Поставщик настраиваемого числового формата можно использовать только с <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метод. Другие перегрузки методов числового форматирования (например `ToString`) с параметром типа <xref:System.IFormatProvider> передают <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> реализацию <xref:System.Type> , представляющий <xref:System.Globalization.NumberFormatInfo> типа. Взамен они ожидают, что метод для возврата <xref:System.Globalization.NumberFormatInfo> объекта. Если этого не произошло, поставщика настраиваемого числового формата игнорируется и <xref:System.Globalization.NumberFormatInfo> объект для текущего языка и региональных параметров используется вместо него. В примере `TelephoneFormatter.GetFormat` метод обрабатывает возможность того, что может быть неверно передан методу числового форматирования, проверяя параметр метода и возвращая `null` , если он представляет тип, отличный от <xref:System.ICustomFormatter>.  
  
 Если поставщик настраиваемого числового формата поддерживает набор описателей формата, убедитесь, что предоставить поведение по умолчанию, если спецификатор формата предоставляется в элементе форматирования, используемых в <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> вызова метода. В приведенном примере "N" является описателем формата по умолчанию. Это позволяет преобразовать число в формат телефонного номера, явно предоставляя описатель формата. В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Но это также позволяет выполнить преобразование в случае, если описатель формата отсутствует. В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Если определен спецификатор формата по умолчанию реализация <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> метод должен включать следующий код, что платформа .NET можно обеспечить форматирование кода не поддерживает.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 В случае в этом примере метод, реализующий <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> предназначен для использования в качестве метода обратного вызова для <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> метод. Таким образом, он проверяет `formatProvider` параметра, чтобы определить, содержит ли ссылка на текущую `TelephoneFormatter` объекта. Тем не менее, метод можно также вызвать непосредственно из кода. В этом случае можно использовать `formatProvider` для предоставления <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo> объект, предоставляющий сведения о форматировании для определенного языка и региональных параметров.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скомпилируйте код из командной строки с помощью csc.exe или vb.exe. Для компиляции кода в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## <a name="see-also"></a>См. также  
 [Выполнение операций форматирования](../../../docs/standard/base-types/performing-formatting-operations.md)
