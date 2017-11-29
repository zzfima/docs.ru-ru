---
title: "&lt;IDN&gt; элемент (параметры Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1f631f41c256e74e9b7bf7dc2d771ee156538820
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltidngt-element-uri-settings"></a>&lt;IDN&gt; элемент (параметры Uri)
Указывает, применяется ли синтаксический анализ международного доменного имени (IDN) к имени домена.  
  
## <a name="schema-hierarchy"></a>Схема иерархии  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > элемент (параметры Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<IDN >](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|`enabled`|Указывает, является ли синтаксический анализ международного доменного имени (IDN) применяется к имени домена по умолчанию none.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).|  
  
## <a name="remarks"></a>Примечания  
 Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5. 3.0 с пакетом обновления 1 и 2.0 SP1 с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN). Текущие пользователи не увидят любые изменения в работе платформы .NET Framework 2.0, пока они не запустят IRI и IDN поддержки. Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Чтобы обеспечить поддержку IRI, необходимы следующие два изменения:  
  
1.  Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Укажите, следует ли синтаксический анализ международного доменного имени (IDN), применяемый к имени домена и следует ли применять правила синтаксического анализа IRI. Это можно сделать в файле machine.config или в файле app.config.  
  
 Существует три возможных значения для IDN в зависимости от используемых серверов DNS.  
  
-   включить IDN = All  
  
     Это значение преобразует имена доменов в Юникоде в их эквиваленты в Punycode (имена IDN).  
  
-   включить IDN = AllExceptIntranet  
  
     Это значение преобразует все имена доменов в Юникоде не локальной интрасети эквиваленты в Punycode (имена IDN). В этом случае для обработки международных имен в локальной интрасети, DNS-серверы, которые используются для интрасети должны поддерживать разрешение имен в Юникоде.  
  
-   включить IDN = нет  
  
     Это значение не станет преобразовывать имена доменов в Юникоде в Punycode. Это значение по умолчанию, которое совместимо с поведением .NET Framework 2.0.  
  
 При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode. Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--". Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).  
  
### <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и имен IDN.  
  
### <a name="code"></a>Код  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
