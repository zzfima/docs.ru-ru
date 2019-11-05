---
title: Смена регистра в .NET
description: Сведения об изменении регистра строк в .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], case
- case sensitivity
- ToUpper method
- ToLower method
- uppercase
- lowercase
ms.assetid: 6805f81b-e9ad-4387-9f4c-b9bdb21b87c0
ms.custom: seodec18
ms.openlocfilehash: a8eb45e45a905f0b366642050f4845460e14aaf8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132903"
---
# <a name="changing-case-in-net"></a>Смена регистра в .NET
При написании приложения, которое принимает входные данные от пользователя, невозможно предугадать, какой регистр будет использоваться для ввода данных. Часто требуется обеспечить согласованность регистра строк, особенно если они отображаются в пользовательском интерфейсе. В таблице ниже описаны три метода изменения регистра. Для первых двух методов имеются перегруженные варианты, учитывающие язык и региональные параметры.  
  
|Имя метода|Использовать|  
|-----------------|---------|  
|<xref:System.String.ToUpper%2A?displayProperty=nameWithType>|Преобразует все символы в строке в верхний регистр.|  
|<xref:System.String.ToLower%2A?displayProperty=nameWithType>|Преобразует все символы в строке в нижний регистр.|  
|<xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>|Преобразует первые символы всех слов в строке в заглавные.|  
  
> [!WARNING]
> Обратите внимание, что методы <xref:System.String.ToUpper%2A?displayProperty=nameWithType> и <xref:System.String.ToLower%2A?displayProperty=nameWithType> не следует использовать для преобразования строк с целью их сравнения или проверки на равенство. См. дополнительные сведения о [сравнении строк, содержащих символы в разных регистрах](#Comparing).  
  
<a name="Comparing"></a>   
## <a name="comparing-strings-of-mixed-case"></a>Сравнение строк, содержащих символы в разных регистрах  
 Чтобы сравнить строки, содержащие символы в разных регистрах, для их упорядочения, вызовите одну из перегрузок метода <xref:System.String.CompareTo%2A?displayProperty=nameWithType> с параметром `comparisonType` и укажите значение <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>, <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> или <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> для аргумента `comparisonType`. Для сравнения с использованием определенного языка, отличного от текущего языка и региональных параметров, вызовите перегрузку метода <xref:System.String.CompareTo%2A?displayProperty=nameWithType> с параметрами `culture` и `options` и укажите значение <xref:System.Globalization.CompareOptions.IgnoreCase?displayProperty=nameWithType> для аргумента `options`.  
  
 Чтобы сравнить строки, содержащие символы в разных регистрах, для определения их равенства, вызовите одну из перегрузок метода <xref:System.String.Equals%2A?displayProperty=nameWithType> с параметром `comparisonType` и укажите значение <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType>, <xref:System.StringComparison.InvariantCultureIgnoreCase?displayProperty=nameWithType> или <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> для аргумента `comparisonType`.  
  
 Дополнительные сведения см. в разделе [Рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md).  
  
## <a name="toupper"></a>ToUpper  
 Метод <xref:System.String.ToUpper%2A?displayProperty=nameWithType> преобразует все символы в строке в верхний регистр. В примере ниже смешанный регистр строки "Hello World!" изменяется на верхний.  
  
 [!code-csharp[Strings.ChangingCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#1)]
 [!code-vb[Strings.ChangingCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#1)]  
  
 В предыдущем примере по умолчанию учитываются язык и региональные параметры. В нем применяются соглашения об использовании регистров, действующие для текущих языка и региональных параметров. Чтобы изменить регистр с учетом языка и региональных параметров или применить соглашения об использовании регистров, принятые для определенного языка и региональных параметров, воспользуйтесь перегрузку метода <xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType> и укажите в качестве параметра *culture* значение <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> или <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>, определяющее язык и региональные параметры. Пример, демонстрирующий использование метода <xref:System.String.ToUpper%2A> для изменения регистра без учета языка и региональных параметров, см. в инструкциях по [изменению регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="tolower"></a>ToLower  
 Метод <xref:System.String.ToLower%2A?displayProperty=nameWithType> аналогичен предыдущему методу, однако преобразует все символы в строке в нижний регистр. В примере ниже смешанный регистр строки "Hello World!" изменяется на нижний.  
  
 [!code-csharp[Strings.ChangingCase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.ChangingCase/cs/Example.cs#2)]
 [!code-vb[Strings.ChangingCase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.ChangingCase/vb/Example.vb#2)]  
  
 В предыдущем примере по умолчанию учитываются язык и региональные параметры. В нем применяются соглашения об использовании регистров, действующие для текущих языка и региональных параметров. Чтобы изменить регистр с учетом языка и региональных параметров или применить соглашения об использовании регистров, принятые для определенного языка и региональных параметров, воспользуйтесь перегрузку метода <xref:System.String.ToLower%28System.Globalization.CultureInfo%29?displayProperty=nameWithType> и укажите в качестве параметра *culture* значение <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> или <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>, определяющее язык и региональные параметры. Пример, демонстрирующий использование метода <xref:System.String.ToLower%28System.Globalization.CultureInfo%29> для изменения регистра без учета языка и региональных параметров, см. в инструкциях по [изменению регистра без учета языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md).  
  
## <a name="totitlecase"></a>ToTitleCase  
 Метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> преобразует первый символ каждого слова в верхний регистр, а остальные символы — в нижний. Однако слова, состоящие только из прописных букв, считаются сокращениями и не преобразуются.  
  
 Метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> учитывает регистр, то есть он использует соглашения об использовании регистров, действующие для определенного языка и региональных параметров. Чтобы вызвать этот метод, сначала нужно получить объект <xref:System.Globalization.TextInfo>, представляющий соглашения об использовании регистров, из свойства <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=nameWithType> конкретного языка и региональных параметров.  
  
 В примере ниже каждая строка из массива передается в метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType>.  Среди строк есть как строки заголовков, так и сокращения. Строки преобразуются в последовательности слов, начинающихся с заглавных букв, согласно соглашениям об использовании регистров для языка и региональных параметров "Английский (США)".  
  
 [!code-csharp[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/cs/totitlecase2.cs#1)]
 [!code-vb[System.Globalization.TextInfo.ToTitleCase#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.textinfo.totitlecase/vb/totitlecase2.vb#1)]  
  
 Обратите внимание на то, что хотя метод <xref:System.Globalization.TextInfo.ToTitleCase%2A?displayProperty=nameWithType> и учитывает язык и региональные параметры, он не обеспечивает лингвистическую правильность использования прописных и строчных букв. Например, в предыдущем примере метод преобразует строку "a tale of two cities" в "A Tale Of Two Cities". При этом лингвистически правильным для языка и региональных параметров en-US будет преобразование "A Tale of Two Cities".  
  
## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
- [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
