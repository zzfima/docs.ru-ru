---
title: "Смена регистра в .NET Framework | Microsoft Docs"
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
  - "учет регистра"
  - "строчные буквы"
  - "строки [платформа .NET Framework], регистр знаков"
  - "ToLower - метод"
  - "ToUpper - метод"
  - "прописные буквы"
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Смена регистра в .NET Framework
При написании приложения, которое принимает входные данные от пользователя, невозможно предугадать, какой регистр будет использоваться для ввода данных.  Часто требуется обеспечить согласованность регистра строк, особенно если они отображаются в пользовательском интерфейсе.  В таблице ниже описаны три метода изменения регистра.  Для первых двух методов имеются перегруженные варианты, учитывающие язык и региональные параметры.  
  
|Имя метода|Применение|  
|----------------|----------------|  
|<xref:System.String.ToUpper%2A?displayProperty=fullName>|Преобразует все символы в строке в верхний регистр.|  
|<xref:System.String.ToLower%2A?displayProperty=fullName>|Преобразует все символы в строке в нижний регистр.|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>|Преобразует первые символы всех слов в строке в заглавные.|  
  
> [!WARNING]
>  Обратите внимание, что методы <xref:System.String.ToUpper%2A?displayProperty=fullName> и <xref:System.String.ToLower%2A?displayProperty=fullName> не следует использовать для преобразования строк с целью их сравнения или проверки на равенство.  Подробнее см. в разделе [Сравнение строк, содержащих символы в разных регистрах](#Comparing).  
  
<a name="Comparing"></a>   
## Сравнение строк, содержащих символы в разных регистрах  
 Чтобы сравнить строки, содержащие символы в разных регистрах, для их упорядочения, вызовите одну из перегрузок метода <xref:System.String.CompareTo%2A?displayProperty=fullName> с параметром `comparisonType` и укажите значение <xref:System.StringComparison?displayProperty=fullName>, <xref:System.StringComparison?displayProperty=fullName> или <xref:System.StringComparison?displayProperty=fullName> для аргумента `comparisonType`.  Для сравнения с использованием определенного языка, отличного от текущего языка и региональных параметров, вызовите перегрузку метода <xref:System.String.CompareTo%2A?displayProperty=fullName> с параметрами `culture` и `options` и укажите значение <xref:System.Globalization.CompareOptions?displayProperty=fullName> для аргумента `options`.  
  
 Чтобы сравнить строки, содержащие символы в разных регистрах, для определения их равенства, вызовите одну из перегрузок метода <xref:System.String.Equals%2A?displayProperty=fullName> с параметром `comparisonType` и укажите значение <xref:System.StringComparison?displayProperty=fullName>, <xref:System.StringComparison?displayProperty=fullName> или <xref:System.StringComparison?displayProperty=fullName> для аргумента `comparisonType`.  
  
 Подробнее см. в разделе [Рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md).  
  
## ToUpper  
 Метод <xref:System.String.ToUpper%2A?displayProperty=fullName> преобразует все символы в строке в верхний регистр.  В примере ниже смешанный регистр строки "Hello World\!" изменяется на верхний.  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 В предыдущем примере по умолчанию учитываются язык и региональные параметры. В нем применяются соглашения об использовании регистров, действующие для текущих языка и региональных параметров.  Чтобы изменить регистр с учетом языка и региональных параметров или применить соглашения об использовании регистров, принятые для определенного языка и региональных параметров, воспользуйтесь перегруженным методом <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=fullName> и укажите в качестве параметра *culture* значение <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo?displayProperty=fullName>, определяющее язык и региональные параметры.  Пример, демонстрирующий использование метода <xref:System.String.ToUpper%2A> для изменения регистра без учета языка и региональных параметров, см. в разделе [Изменение регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## ToLower  
 Метод <xref:System.String.ToLower%2A?displayProperty=fullName> аналогичен предыдущему методу, однако преобразует все символы в строке в нижний регистр.  В примере ниже регистр строки "Hello World\!" изменяется на нижний.  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 В предыдущем примере по умолчанию учитываются язык и региональные параметры. В нем применяются соглашения об использовании регистров, действующие для текущих языка и региональных параметров.  Чтобы изменить регистр с учетом языка и региональных параметров или применить соглашения об использовании регистров, принятые для определенного языка и региональных параметров, воспользуйтесь перегруженным методом <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=fullName> и укажите в качестве параметра *culture* значение <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo?displayProperty=fullName>, определяющее язык и региональные параметры.  Пример, демонстрирующий использование метода <xref:System.String.ToLower%28System.Globalization.CultureInfo%29> для изменения регистра без учета языка и региональных параметров, см. в разделе [Изменение регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## ToTitleCase  
 Метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> преобразует первый символ каждого слова в верхний регистр, а остальные символы — в нижний.  Однако слова, состоящие только из прописных букв, считаются сокращениями и не преобразуются.  
  
 Метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> учитывает регистр, то есть он использует соглашения об использовании регистров, действующие для определенного языка и региональных параметров.  Чтобы вызвать этот метод, сначала нужно получить объект <xref:System.Globalization.TextInfo>, представляющий соглашения об использовании регистров, из свойства <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=fullName> конкретного языка и региональных параметров.  
  
 В примере ниже каждая строка из массива передается в метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName>.  Среди строк есть как строки заголовков, так и сокращения.  Строки преобразуются в последовательности слов, начинающихся с заглавных букв, согласно соглашениям об использовании регистров для языка и региональных параметров "Английский \(США\)".  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 Обратите внимание на то, что хотя метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=fullName> и учитывает язык и региональные параметры, он не обеспечивает лингвистическую правильность использования прописных и строчных букв.  Например, в предыдущем примере метод преобразует строку "a tale of two cities" в "A Tale Of Two Cities".  При этом лингвистически правильным для языка и региональных параметров en\-US будет преобразование "A Tale of Two Cities".  
  
## См. также  
 [Основные операции со строками](../../../docs/standard/base-types/basic-string-operations.md)   
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)