---
title: Поддержка международного кода ресурса в System.Uri
ms.date: 03/30/2017
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
ms.openlocfilehash: f78fff250aae177b5f0360e77a1c41a2f2bb0527
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "64647338"
---
# <a name="international-resource-identifier-support-in-systemuri"></a>Поддержка международного кода ресурса в System.Uri
Класс <xref:System.Uri?displayProperty=nameWithType> был расширен за счет поддержки международного идентификатора ресурса (IRI) и международных доменных имен (IDN). Эти улучшения доступны в .NET Framework 3.5, 3.0 с пакетом обновления 1 (SP1) и 2.0 с пакетом обновления 1 (SP1).  
  
## <a name="iri-and-idn-support"></a>Поддержка IRI и IDN  
 Веб-адреса обычно выражаются с помощью унифицированных идентификаторов ресурса (URI), которые состоят из очень ограниченного набора символов:  
  
- буквы верхнего и нижнего регистра английского алфавита в кодировке ASCII;  
  
- цифры от 0 до 9;  
  
- небольшое количество других символов ASCII.  
  
 Спецификации URI документально зафиксированы в стандартах RFC 2396 и RFC 3986, опубликованных IETF.  
  
 По мере расширения Интернета потребность в идентификации ресурсов на языках, отличных от английского, становится все более насущной. Идентификаторы, которые способствуют удовлетворению этой потребности и позволяют использовать символы, не принадлежащие к кодировке ASCII (символы из кодировок Unicode/ISO 10646), называются международными кодами ресурсов (IRI). Спецификации IRI документально зафиксированы в стандарте RFC 3987, опубликованном IETF. Использование IRI позволяет применять в URL символы Юникода.  
  
 Существующий класс <xref:System.Uri?displayProperty=nameWithType> был расширен, чтобы обеспечивать поддержку IRI на основе стандарта RFC 3987. Пользователи не увидят никаких функциональных изменений, внесенных после платформы .NET Framework 2.0, пока специально не включат поддержку IRI. Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Приложение может указать, должен ли применяться синтаксический анализ международных доменных имен (IDN) к доменным именам и должны ли применяться правила синтаксического анализа IRI. Это можно сделать в файле machine.config или в файле app.config.  
  
 При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode. Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--". Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).  
  
 Включение IRI и IDN влияет на значение свойства <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>. Включение IRI и IDN может также привести к изменению принципа действия методов <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> и <xref:System.Uri.IsWellFormedOriginalString%2A>.  
  
 Расширен был также и класс <xref:System.GenericUriParser?displayProperty=nameWithType>, который теперь позволяет создавать настраиваемые средства синтаксического анализа, поддерживающие IRI и IDN. Поведение объекта <xref:System.GenericUriParser?displayProperty=nameWithType> задается путем передачи побитового сочетания значений, доступных в перечислении <xref:System.GenericUriParserOptions?displayProperty=nameWithType>, конструктору <xref:System.GenericUriParser?displayProperty=nameWithType>. Тип <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType> указывает на то, что средство синтаксического анализа поддерживает правила анализа, определенные стандартом RFC 3987 для международных кодов ресурсов (IRI). Фактически использование IRI зависит от того, включен ли IRI.  
  
 Тип <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType> указывает на то, что средство синтаксического анализа поддерживает анализ международных доменных имен (IDN) узлов. Фактически использование IDN зависит от того, включен ли IDN.  
  
 Синтаксический анализ IRI будет выполнять проверку нормализации и символов в соответствии с последними правилами IRI стандарта RFC 3987. Значение по умолчанию для синтаксического анализа отключается, поэтому нормализация и проверка символов выполняются в соответствии с RFC 2396 и RFC 3986.  
  
 Обработку IRI и IDN в классе <xref:System.Uri?displayProperty=nameWithType> также можно контролировать с помощью классов параметров конфигурации <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> и <xref:System.Configuration.IdnElement?displayProperty=nameWithType>. Параметр <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> включает или отключает обработку IRI в классе <xref:System.Uri?displayProperty=nameWithType>. Параметр <xref:System.Configuration.IdnElement?displayProperty=nameWithType> включает или отключает обработку IDN в классе <xref:System.Uri>. Параметр <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> также косвенно управляет IDN. Обработка IRI должна быть включена для обработки IDN. Если IRI-система не включена, то обработка IDN данных будет происходить по умолчанию, когда режим платформы .NET Framework 2.0 является совместимым и имена IDN не используются.  
  
 Параметр конфигурации для классов конфигурации <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> и <xref:System.Configuration.IdnElement?displayProperty=nameWithType> будет считан, когда будет создан первый класс <xref:System.Uri?displayProperty=nameWithType>. Изменения, внесенные в параметры конфигурации после этого, игнорируются.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>
