---
title: Практическое руководство. Определение и использование поставщиков настраиваемых числовых форматов
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 5345c90d966ea9ce0a0bbf6c884b8d8abc8b5fa7
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523939"
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Практическое руководство. Определение и использование поставщиков настраиваемых числовых форматов
.NET Framework обеспечивает расширенный контроль над строковым представлением числовых значений. Эта платформа поддерживает указанные далее возможности для настройки форматов числовых значений.  
  
- Строки стандартных числовых форматов, которые предоставляют стандартный набор форматов для преобразования чисел в их строковое представление. Вы можете использовать их с любым методом числового форматирования, например <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType> с параметром `format`. Дополнительные сведения см. в статье [Строки стандартных числовых форматов](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
- Строки настраиваемых числовых форматов, предоставляющих набор символов, которые могут быть объединены для определения описателей настраиваемого числового формата. Их можно использовать с любым методом числового форматирования, например <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType> с параметром `format`. Дополнительные сведения см. в разделе [Строки настраиваемых числовых форматов](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
- Настраиваемые объекты <xref:System.Globalization.CultureInfo> и <xref:System.Globalization.NumberFormatInfo>, которые определяют символы и шаблоны форматирования для отображения строковых представлений числовых значений. Вы можете использовать их с любым методом числового форматирования, например <xref:System.Int32.ToString%2A> с параметром `provider`. Как правило, параметр `provider` используется для указания форматирования, зависящего от языка и региональных параметров.  
  
 В некоторых случаях (например, когда приложению необходимо отобразить отформатированный номер учетной записи, идентификационный номер или почтовый индекс) эти три метода неприменимы. Также .NET Framework позволяет определить объект форматирования, который не является объектом <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo>, для определения порядка форматирования числовых значений. Этот раздел содержит пошаговые инструкции по реализации таких объектов и пример форматирования телефонных номеров.  
  
### <a name="to-define-a-custom-format-provider"></a>Определение поставщика пользовательского формата  
  
1. Определите класс, реализующий интерфейсы <xref:System.IFormatProvider> и <xref:System.ICustomFormatter>.  
  
2. Выполните метод <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A> — это метод обратного вызова, с помощью которого метод форматирования (например, <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>) вызывает объект, отвечающий за выполнение пользовательского форматирования. Метод <xref:System.IFormatProvider.GetFormat%2A> в типичной реализации выполняет следующие действия:  
  
    1. Определяет, предоставляет ли объект <xref:System.Type>, полученный в качестве параметра, интерфейс <xref:System.ICustomFormatter>.  
  
    2. Если параметр представляет интерфейс <xref:System.ICustomFormatter>, то метод <xref:System.IFormatProvider.GetFormat%2A> возвращает объект, реализующий интерфейс <xref:System.ICustomFormatter>, который отвечает за применение пользовательского форматирования. Как правило, объект пользовательского форматирования возвращает сам себя.  
  
    3. Если параметр не представляет интерфейс <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> возвращает `null`.  
  
3. Выполните метод <xref:System.ICustomFormatter.Format%2A>. Этот метод вызывается из метода <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> и возвращает строковое представление числа. Реализация этого метода обычно включает в себя выполнение следующих действий.  
  
    1. Вы можете проверить параметр `provider`, чтобы убедиться, что метод действительно предназначен для форматирования. Для объектов форматирования, которые реализуют интерфейсы <xref:System.IFormatProvider> и <xref:System.ICustomFormatter>, нужно проверить еще и параметр `provider`, значение которого должно совпадать с текущим объектом форматирования.  
  
    2. Определите, должен ли объект форматирования поддерживать описатели настраиваемого формата. (Например, описатель формата "N" может указывать, что телефонный номер США следует выводить в формате NANP, а "I" может означать вывод в формате E.123 в соответствии с рекомендацией ITU-T.) Если используются описатели формата, то метод должен обрабатывать этот описатель определенного формата. Он передается методу в параметре `format`. Если описатель отсутствует, значением параметра `format` является <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3. Получите числовое значение, передаваемое методу в параметре `arg`. Выполните операции, необходимые для его преобразования в строковое представление.  
  
    4. Верните строковое представление параметра `arg`.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Использование объекта настраиваемого числового форматирования  
  
1. Создайте новый экземпляр класса настраиваемого форматирования.  
  
2. Вызовите метод форматирования <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, передав ему объект пользовательского форматирования, описатель форматирования (или <xref:System.String.Empty?displayProperty=nameWithType>, если описатель не используется) и числовое значение для форматирования.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется поставщик настраиваемого числового формата с именем `TelephoneFormatter`, который преобразует число, представляющее номер телефона в США, в формат NANP или E.123. Метод обрабатывает два описателя формата "N" (вывод в формате NANP) и "I" (вывод в международном формате E.123).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Поставщик настраиваемого числового формата можно использовать только с методом <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Другие перегрузки методов числового форматирования (например, `ToString`), у которых параметр имеет тип <xref:System.IFormatProvider>, передают в реализацию метода <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> объект <xref:System.Type>, представляющий тип <xref:System.Globalization.NumberFormatInfo>. В ответ они ожидают получить объект <xref:System.Globalization.NumberFormatInfo>. Если это не так, поставщик настраиваемого числового формата игнорируется, и вместо него используется объект <xref:System.Globalization.NumberFormatInfo> для текущих языка и региональных параметров. В нашем примере метод `TelephoneFormatter.GetFormat` обрабатывает случай некорректной передачи его в метод числового форматирования. Для этого он проверяет параметр метода и возвращает `null`, если его тип отличается от <xref:System.ICustomFormatter>.  
  
 Если поставщик настраиваемого числового формата поддерживает набор описателей формата, обязательно предоставьте поведение по умолчанию на случай, если описатель формата не указан в элементе форматирования при вызове метода <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. В приведенном примере "N" является описателем формата по умолчанию. Это позволяет преобразовать число в формат телефонного номера, явно предоставляя описатель формата. В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Но это также позволяет выполнить преобразование в случае, если описатель формата отсутствует. В следующем примере показан такой вызов метода.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Если описатель формата по умолчанию не определен, реализация метода <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> должна содержать код, аналогичный приведенному ниже, чтобы платформа .NET предоставила не поддерживаемое в коде форматирование.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 В нашем примере метод, который реализует <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>, будет использоваться как метод обратного вызова для метода <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Это значит, что он должен проверить параметр `formatProvider` на наличие ссылки на текущий объект `TelephoneFormatter`. Тем не менее, метод можно также вызвать непосредственно из кода. В этом случае вы можете использовать параметр `formatProvider` для предоставления объекта <xref:System.Globalization.CultureInfo> или <xref:System.Globalization.NumberFormatInfo> со сведениями о форматировании для выбранного языка и региональных параметров.
