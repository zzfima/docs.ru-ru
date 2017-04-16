---
title: "Выполнение смены регистра независимо от языка и региональных параметров | Microsoft Docs"
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
  - "String.ToLower - метод"
  - "язык и региональные параметры, учет регистра"
  - "Char.ToLower - метод"
  - "регистр, изменения в строках, независимых от языка и региональных параметров"
  - "Char.ToUpper - метод"
  - "операции со строками без учета языка и региональных параметров, изменения регистра"
  - "String.ToUpper - метод"
  - "языковый и региональный параметр"
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Выполнение смены регистра независимо от языка и региональных параметров
Методы <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> и <xref:System.Char.ToLower%2A?displayProperty=fullName> предоставляют перегрузки, которые не принимают никакие параметры.  По умолчанию эти перегрузки без параметров выполняют изменения регистра, основанные на значении <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.  Это приводит к результатам, зависящим от регистра, которые могут меняться в зависимости от языка и региональных параметров.  Чтобы указать, требуется ли изменение регистра, учитывающее язык и региональные параметры, необходимо использовать перегрузки этих методов, которые требуют явного задания параметра `culture`.  Для изменения регистра с учетом языка и региональных параметров присвойте параметру `culture` значение `CultureInfo.CurrentCulture`.  Для изменения регистра независимо от языка и региональных параметров присвойте параметру `culture` значение `CultureInfo.InvariantCulture`.  
  
 Обычно строки приводятся к стандартному регистру для облегчения последующего просмотра.  Если используется этот способ, параметру `culture` необходимо присвоить значение `CultureInfo.InvariantCulture`, поскольку значение свойства <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName> может измениться в период между изменением регистра и выполнением поиска.  
  
 Если решение безопасности зависит от операции изменения регистра, она не должна зависеть от языка и региональных параметров, чтобы гарантировать независимость результата от значения `CultureInfo.CurrentCulture`.  Пример, в котором демонстрируются строковые операции с учетом языка и региональных параметров, дающие противоречивые результаты, см. в подразделе "Сравнения строк, использующие текущие язык и региональные параметры" статьи [Рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md).  
  
## Использование методов String.ToUpper и String.ToLower  
 Для получения более понятного кода рекомендуется всегда использовать перегрузки методов `String.ToUpper` и `String.ToLower`, которые позволяют явно задать значение параметра `culture`.  Например, следующий код производит поиск идентификатора.  Операция `key.ToLower` является по умолчанию зависящей от языка и региона, но это явно не показано в коде.  
  
### Пример  
  
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
  
 Чтобы операция `key.ToLower` не зависела от языка и региональных параметров, измените приведенный выше пример кода так, как показано ниже, чтобы явно использовать значение `CultureInfo.InvariantCulture` при изменении регистра.  
  
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
  
## Использование методов Char.ToUpper и Char.ToLower  
 Методы `Char.ToUpper` и `Char.ToLower`  обладают такими же характеристиками, что и методы `String.ToUpper` и `String.ToLower`, однако единственные языки и региональные параметры, для которых это имеет значение — это турецкий \(Турция\) и азербайджанский \(латиница, Азербайджан\).  Изменение регистра одиночного символа отличается только в этих двух языках.  Дополнительные сведения об этом уникальном сопоставлении регистра см. в разделе «Регистр» описания класса <xref:System.String>.  Для получения более понятного кода и непротиворечивых результатов рекомендуется всегда использовать перегрузки этих методов, позволяющие явно задавать значение параметра `culture`.  
  
## См. также  
 <xref:System.String.ToUpper%2A?displayProperty=fullName>   
 <xref:System.String.ToLower%2A?displayProperty=fullName>   
 <xref:System.Char.ToUpper%2A?displayProperty=fullName>   
 <xref:System.Char.ToLower%2A?displayProperty=fullName>   
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)