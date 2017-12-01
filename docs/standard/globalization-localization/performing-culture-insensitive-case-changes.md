---
title: "Выполнение смены регистра независимо от языка и региональных параметров"
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
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a>Выполнение смены регистра независимо от языка и региональных параметров
<xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, И <xref:System.Char.ToLower%2A?displayProperty=nameWithType> методы предоставляют перегрузки, которые не принимают параметры. По умолчанию эти перегрузки без параметров выполняют изменения регистра, основанные на значении <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>. Это приводит к результатам, с учетом регистра, которые может зависеть от языка и региональных параметров. Для того чтобы ясно показать изменение регистра для языка и региональных параметров с учетом или без учета языка и региональных параметров, следует использовать перегрузки этих методов, которые требуют явного задания `culture` параметра. Для изменения регистра с учетом языка и региональных параметров, укажите `CultureInfo.CurrentCulture` для `culture` параметра. Без учета языка и региональных параметров изменения регистра, укажите `CultureInfo.InvariantCulture` для `culture` параметра.  
  
 Часто строки преобразуются в стандартный обращение, чтобы включить упрощает поиск более поздней версии. При использовании строки таким образом, следует указать `CultureInfo.InvariantCulture` для `culture` параметра, так как значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> может измениться между моментом изменения регистра и время поиска.  
  
 Если решение безопасности зависит от операции изменения регистра, операции должно быть от языка и региональных параметров, чтобы гарантировать, что результат не повлияет значение `CultureInfo.CurrentCulture`. В разделе «Строка сравнения, текущего языка и региональных параметров» [советы и рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md) статью для пример, демонстрирующий зависящие от языка и региональных параметров строковые операции может привести к непредсказуемым результатам.  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>Используя String.ToUpper и String.ToLower методы  
 Для получения более понятного кода рекомендуется всегда использовать перегрузки `String.ToUpper` и `String.ToLower` методы, которые позволяют указать `culture` параметр явным образом. Например следующий код производит поиск идентификатора. `key.ToLower` Операция язык и региональные параметры по умолчанию, но это поведение не ясно из в коде.  
  
### <a name="example"></a>Пример  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 Если вы хотите `key.ToLower` операции зависеть от языка и региональных параметров, следует изменить приведенный выше пример следующим образом, чтобы явно указать `CultureInfo.InvariantCulture` при изменении регистра.  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>С помощью Char.ToUpper и Char.ToLower методов  
 Несмотря на то что `Char.ToUpper` и `Char.ToLower` методы имеют те же характеристики, что `String.ToUpper` и `String.ToLower` методы только языки и региональные параметры, которые подпадают под, турецкий (Турция) и Азербайджанский (латиница, Азербайджан). Это единственные языки и региональные параметры регистра одного символа отличается. Дополнительные сведения об этом уникальном сопоставлении регистра см. в разделе "Регистр" описания класса <xref:System.String>. Для получения более понятного кода и добиться согласованных результатов, рекомендуется всегда использовать перегрузки этих методов, которые позволяют явным образом указывать `culture` параметра.  
  
## <a name="see-also"></a>См. также  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
