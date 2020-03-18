---
title: Сравнение строк без учета языка и региональных параметров
ms.date: 08/22/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.CompareTo method
- String.Compare method
- string comparison [.NET Framework], culture-insensitive
- strings [.NET Framework], comparing
- culture-insensitive string operations, comparisons
- culture parameter
ms.assetid: abae50ef-32f7-4a50-a540-fd256fd1aed0
ms.openlocfilehash: 85ba91b63ab0edbccc768e2d1ad4aaef31fd2f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73120833"
---
# <a name="performing-culture-insensitive-string-comparisons"></a>Сравнение строк без учета языка и региональных параметров
По умолчанию метод <xref:System.String.Compare%2A?displayProperty=nameWithType> выполняет сравнение с учетом языка и региона и регистра символов. Этот метод также содержит несколько перегрузок, которые предоставляют параметр `culture`, позволяющий задать используемый язык и региональные параметры, и параметр `comparisonType`, позволяющий указать используемые правила сравнения. При вызове этих методов вместо перегрузки по умолчанию удаляется любая неопределенность в отношении правил, используемых при вызове конкретного метода, и четко определяется, учитываются ли при конкретном сравнении язык и региональные параметры.  
  
> [!NOTE]
> Обе перегрузки метода <xref:System.String.CompareTo%2A?displayProperty=nameWithType> выполняют сравнение с учетом языка и региональных параметров и с учетом регистра; для сравнения без учета языка и региональных параметров этот метод использовать нельзя. Для получения более понятного кода рекомендуется вместо этого метода использовать метод <xref:System.String.Compare%2A?displayProperty=nameWithType>.  
  
 Для операций с учетом языка и региональных параметров в качестве параметра <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> следует указать значение перечисления <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> или `comparisonType`. Чтобы выполнить сравнение с учетом языка и региональных параметров, используя назначенный (отличный от текущего) язык и региональные параметры, в качестве параметра <xref:System.Globalization.CultureInfo> следует указать объект `culture`, представляющий этот язык и региональные параметры.  
  
 Поддерживаемые методом <xref:System.String.Compare%2A?displayProperty=nameWithType> операции сравнения строк без учета языка и региональных параметров могут быть лингвистическими (выполняемыми на основе правил сортировки инвариантного языка и региональных параметров) или нелингвистическими (выполняемыми на основе порядковых номерах символов в строке). Большинство операций сравнения строк без учета языка и региональных параметров являются нелингвистическими. Для таких операций сравнения в качестве параметра <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> следует указать значение перечисления <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> или `comparisonType`. Например, если решение, влияющее на безопасность (к примеру, сравнение имени пользователя или пароля), принимается на основе результата сравнения строк, операция должна быть нелингвистической и выполняться без учета языка и региональных параметров, чтобы на результат не повлияли правила конкретного языка и региональных параметров.  
  
 Если требуется согласованная лингвистическая обработка соответствующих строк из нескольких языков и региональных параметров, следует использовать лингвистическое сравнение строк без учета языка и региональных параметров. Например, если приложение отображает в списке слова, в которых используется несколько кодировок, может потребоваться отображать слова в одном и том же порядке независимо от текущего языка и региональных параметров. Для операций лингвистического сравнения без учета языка и региональных параметров платформа .NET Framework определяет инвариантный язык и региональные параметры на основе операций лингвистического сравнения для английского языка. Для выполнения лингвистического сравнения без учета языка и региональных параметров в качестве параметра <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> следует указать <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> или `comparisonType`.  
  
 В следующем примере выполняется два нелингвистических сравнения строк без учета языка и региональных параметров. В первом сравнении учитывается регистр, а во втором — нет.  
  
 [!code-csharp[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/cs/cultureinsensitive1.cs#1)]
 [!code-vb[Conceptual.Strings.CultureInsensitiveComparison#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.cultureinsensitivecomparison/vb/cultureinsensitive1.vb#1)]  

Можно скачать [таблицы коэффициентов сортировки](https://www.microsoft.com/download/details.aspx?id=10921) — набор текстовых файлов, которые содержат сведения о весовых коэффициентах символов, используемых в операциях сортировки и сравнения для операционных систем Windows, а также [таблицу параметров сортировки по умолчанию для элементов Юникод](https://www.unicode.org/Public/UCA/latest/allkeys.txt) — таблицу весовых коэффициентов сортировки для Linux и macOS.

## <a name="see-also"></a>См. также раздел

- <xref:System.String.Compare%2A?displayProperty=nameWithType>
- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- [Рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md)
