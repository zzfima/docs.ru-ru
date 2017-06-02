---
title: "Изменения пространства имен System.Uri в версии 2.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Изменения пространства имен System.Uri в версии 2.0
Были внесены некоторые изменения в класс <xref:System.Uri?displayProperty=fullName>.  Эти изменения зафиксировали неправильную расширения функциональности, удобство использования и усиленную безопасность.  
  
## Устаревшие члены и нерекомендуемые  
 Конструкторы.  
  
-   Все конструкторы, которые имеют параметр `dontEscape` .  
  
 Методы:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## Изменения  
  
-   Для схем uri, известно, что имеется часть запроса \(файл, ftp и др.\), "?" символ всегда избегается и не считается началом части <xref:System.Uri.Query%2A>.  
  
-   Для неявного файла \(Uri @name.txt формы "c:\\directory\\file"\), \(" \# "\) символов избегается фрагмента всегда полностью unescaping если не спрошен или <xref:System.Uri.LocalPath%2A>`true`.  
  
-   Поддержка hostname UNC, была удалена; спецификация IDN для представления международные именена узла.  
  
-   <xref:System.Uri.LocalPath%2A> всегда возвращает полностью unescaped строку.  
  
-   <xref:System.Uri.ToString%2A> не делает unescape преобразованное в escape\-последовательность "%", "? " или "&#124;".  
  
-   <xref:System.Uri.Equals%2A> теперь включает часть <xref:System.Uri.Query%2A> в обновлений равенства.  
  
-   "\=\=" Операторов и "\! \=" можно выполнить переопределение и ссылка на <xref:System.Uri.Equals%2A> метод.  
  
-   <xref:System.Uri.IsLoopback%2A> теперь содержит последовательные.  
  
-   Универсальный код ресурса \(uri\) "`file:///path`" больше не преобразуется в "file:\/\/path".  
  
-   "&#124;" теперь распознает как признак имени узла.  То есть "http:\/\/consoto.com\#fragment" теперь преобразован значение "http:\/\/contoso.com\/\#fragment".  
  
-   Ошибка при комбинировании будет зафиксирован базовый универсальный код ресурса \(uri\) с фрагментом.  
  
-   Ошибка в <xref:System.Uri.HostNameType%2A> исправить.  
  
-   Ошибка при анализе протокол NNTP исправить.  
  
-   Универсальный код ресурса \(uri\) HTTP формы: теперь выдает исключение contoso.com синтаксического анализа.  
  
-   .NET Framework правильно обрабатывает userinfo в универсальный код ресурса \(uri\).  
  
-   Сжатие пути универсального кода ресурса \(uri\) исправлена, чтобы сломленное универсальный код ресурса \(uri\) не сможет просматривать файловую систему на корень.  
  
## См. также  
 <xref:System.Uri?displayProperty=fullName>