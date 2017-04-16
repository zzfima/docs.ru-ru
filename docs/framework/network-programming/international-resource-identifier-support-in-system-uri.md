---
title: "Поддержка международного кода ресурса в System.Uri | Microsoft Docs"
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
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Поддержка международного кода ресурса в System.Uri
Класс <xref:System.Uri?displayProperty=fullName> был расширен с международным идентификатор ресурса \(IRI\) и интернационализированной поддержкой имен домена \(IDN\).  Эти улучшения доступные в .NET Framework 3.5, 3,0 SP1, 2.0 SP1.  
  
## Поддержка IRI и IDN  
 Веб\-адрес обычно выражаются с помощью универсальных кодов ресурса \(uri\), составляющие весьма ограниченного набора символов:  
  
-   буквы верхнего и нижнего регистра английского алфавита в кодировке ASCII;  
  
-   цифры от 0 до 9;  
  
-   небольшое количество других знаков кодировки ASCII.  
  
 Спецификации URI документально зафиксированы в стандартах RFC 2396 и RFC 3986, опубликованных IETF.  
  
 По мере расширения Интернета потребность в использовании, для идентификации ресурсов, отличных от английского языков становится все более насущной.  Идентификаторы, которые способствуют удовлетворению этой потребности и позволяют использовать символы, не принадлежащие к кодировке ASCII \(символы из кодировок Unicode\/ISO 10646\), называются международными кодами ресурсов \(IRI\).  Спецификации IRI документально зафиксированы в стандарте RFC 3987, опубликованном IETF.  Использование IRI позволяет применять в URL символы Юникода.  
  
 Существующий класс <xref:System.Uri?displayProperty=fullName> расширен, чтобы обеспечивать поддержку IRI на основе стандарта RFC 3987.  Нынешние пользователи не увидят никаких функциональных изменений, внесенных после платформы .NET Framework 2.0, пока специально не включат поддержку IRI.  Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Приложение может указать, следует ли использовать интернационализировало разбора имени домена \(IDN\), примененный к именам доменов и правила синтаксического анализа IRI должна ли быть применено.  Это можно сделать в файле machine.config или в файле app.config.  
  
 Включение IDN все метки в Юникоде в именах доменов будут преобразовываться в их эквиваленты в Punycode.  Имена в Punycode содержат только символы ASCII и всегда начинаются с приставки xn\-\-.  Это сделано для того, чтобы поддерживать существующие DNS\-серверы в интрасети, так как большинство DNS\-серверов поддерживает только символы ASCII \(см. RFC 3940\).  
  
 Активация использования IRI и IDN влияет на значение свойства <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>.  Активация IRI и IDN может также привести к изменению принципа действия методов <xref:System.Uri.Equals%2A?displayProperty=fullName>, <xref:System.Uri.OriginalString%2A?displayProperty=fullName>, <xref:System.Uri.GetComponents%2A?displayProperty=fullName> и <xref:System.Uri.IsWellFormedOriginalString%2A>.  
  
 Расширен был также и класс <xref:System.GenericUriParser?displayProperty=fullName>, который теперь позволяет создавать настраиваемые средства синтаксического анализа, поддерживающие IRI и IDN.  Поведение объекта <xref:System.GenericUriParser?displayProperty=fullName> задается путем передачи побитового сочетания значений, доступных в перечислении <xref:System.GenericUriParserOptions?displayProperty=fullName>, конструктору <xref:System.GenericUriParser?displayProperty=fullName>.  Тип <xref:System.GenericUriParserOptions?displayProperty=fullName> указывает на то, что средство синтаксического анализа поддерживает правила анализа, определенные стандартом RFC 3987 для международных кодов ресурсов \(IRI\).  Фактически, используемые ли IRI зависит от если IRI включено.  
  
 Тип <xref:System.GenericUriParserOptions?displayProperty=fullName> указывает на то, что средство синтаксического анализа поддерживает анализ международных доменных имен \(IDN\) узлов.  Фактически, используемые ли IDN, зависит от того, включен ли IDN.  
  
 Включить анализ IRI выполняет нормализацию и последним проверку в соответствии с правилами IRI в RFC 3987.  Значение по умолчанию для синтаксического анализа IRI непредоставляемых поэтому проверка нормализации и знака выполняется в соответствии с RFC 2396 и RFC 3986.  
  
 При обработке IRI и IDN в классе <xref:System.Uri?displayProperty=fullName> также можно отслеживать с помощью классов параметра конфигурации <xref:System.Configuration.IriParsingElement?displayProperty=fullName> и <xref:System.Configuration.IdnElement?displayProperty=fullName>.  Параметр <xref:System.Configuration.IriParsingElement?displayProperty=fullName> включает или отключает обработку IRI в классе <xref:System.Uri?displayProperty=fullName>.  Параметр <xref:System.Configuration.IdnElement?displayProperty=fullName> включает или отключает обработку IDN в классе <xref:System.Uri>.  Параметр <xref:System.Configuration.IriParsingElement?displayProperty=fullName> обеспечивает также опосредованное управление IDN.  Система IRI должна включаться для работы с данными IDN.  Если IRI система не включена, то обработка IDN данных будет происходить по умолчанию, когда режим платформы .NET Framework 2.0 является совместимым и имена IDN не используются.  
  
 Параметр конфигурации для классов конфигурации <xref:System.Configuration.IriParsingElement?displayProperty=fullName> и <xref:System.Configuration.IdnElement?displayProperty=fullName> будет сразу же считан, когда будет создан первый класс <xref:System.Uri?displayProperty=fullName>.  Изменения в параметрах конфигурации после этого игнорируются.  
  
## См. также  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>