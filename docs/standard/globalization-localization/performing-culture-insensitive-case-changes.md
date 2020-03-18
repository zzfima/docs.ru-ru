---
title: Выполнение смены регистра независимо от языка и региональных параметров
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 7b2dee03619e24c5a2845699a06e88abab0c594b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160135"
---
# <a name="performing-culture-insensitive-case-changes"></a>Выполнение смены регистра независимо от языка и региональных параметров
Методы <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> и <xref:System.Char.ToLower%2A?displayProperty=nameWithType> предоставляют перегрузки, которые не принимают параметры. По умолчанию эти перегрузки без параметров выполняют изменения регистра на основе значения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>. Результат преобразования чувствителен к регистру и может быть разным для языков и региональных параметров. Чтобы четко указать, нужно ли учитывать язык и региональные параметры при изменении регистра, используйте перегрузки этих методов, принимающие параметр `culture` явным образом. Чтобы изменить регистр с учетом языка и региональных параметров, укажите значение `CultureInfo.CurrentCulture` для параметра `culture`. Чтобы изменить регистр без учета языка и региональных параметров, укажите значение `CultureInfo.InvariantCulture` для параметра `culture`.  
  
 Обычно строки преобразуются в стандартный регистр, чтобы упростить поиск по этим значениям. Если вы намерены применить такой подход, укажите значение `CultureInfo.InvariantCulture` для параметра `culture`, так как значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> может быть разным в момент преобразования регистра и в момент поиска.  
  
 Если регистр важен для работы системы безопасности, такие операции ни в коем случае не должны зависеть от языка и региона, чтобы значение параметра `CultureInfo.CurrentCulture` не влияло на результат. Пример строковых операций с учетом языка и региональных параметров, дающих противоречивые результаты, см. в разделе "Сравнение строк с использованием текущего языка и региональных параметров" статьи [Советы и рекомендации по использованию строк в .NET](../../../docs/standard/base-types/best-practices-strings.md).  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>Использование методов String.ToUpper и String.ToLower  
 Чтобы повысить читаемость кода, мы рекомендуем всегда использовать перегрузки методов `String.ToUpper` и `String.ToLower`, позволяющие явным образом указать параметр `culture`. Например, приведенный ниже код выполняет поиск идентификатора. Операция `key.ToLower` по умолчанию зависит от языка и региональных параметров, но это поведение никак не отражено в коде.  
  
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
  
 Если нужно, чтобы операция `key.ToLower` зависела от языка и региональных параметров, измените приведенный выше пример так, чтобы явно указать `CultureInfo.InvariantCulture` для изменения регистра.  
  
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
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>Использование методов Char.ToUpper и Char.ToLower  
 Методы `Char.ToUpper` и `Char.ToLower` действуют точно так же, как и методы `String.ToUpper` и `String.ToLower`, за исключением турецкого (Турция) и азербайджанского (латиница, Азербайджан) языков. Только для этих значений языка и региональных параметров изменяется применение регистра для одиночных символов. Дополнительные сведения об этом уникальном сопоставлении регистра см. в разделе "Регистр" описания класса <xref:System.String>. Чтобы повысить читаемость кода и стабильность результатов, мы рекомендуем всегда использовать перегрузки этих методов, позволяющие явным образом указать параметр `culture`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.String.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.String.ToLower%2A?displayProperty=nameWithType>
- <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.Char.ToLower%2A?displayProperty=nameWithType>
- [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
