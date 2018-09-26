---
title: '&lt;IDN&gt; (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 1537c17cb3c16beeb41cfaa4103e0664e93facc7
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170604"
---
# <a name="ltidngt-element-uri-settings"></a>&lt;IDN&gt; (параметры Uri)
Указывает, применяется ли синтаксический анализ международных доменных имен (IDN) к имени домена.  
  
## <a name="schema-hierarchy"></a>Схема иерархии  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > (параметры Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
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
|`enabled`|Указывает, что синтаксический анализ международных доменных имен (IDN), применяемые к имени домена, значение по умолчанию — none.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).|  
  
## <a name="remarks"></a>Примечания  
 Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5. 3.0 с пакетом обновления 1 и 2.0 с пакетом обновления 1 с поддержкой международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN). Текущие пользователи не увидят любое изменение в .NET Framework 2.0, пока они не запустят IRI и IDN поддержки. Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Чтобы включить поддержку IRI, необходимы следующие два изменения:  
  
1.  Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Укажите, нужно ли синтаксический анализ международных доменных имен (IDN), применяемый к имени домена и должны ли применяться правила синтаксического анализа IRI. Это можно сделать в файле machine.config или в файле app.config.  
  
 Существует три возможных значения для IDN в зависимости от DNS-серверы, которые используются:  
  
-   IDN включена = All  
  
     Это значение преобразует имена доменов из Юникода в их эквиваленты в Punycode (IDN-имена).  
  
-   IDN включена = AllExceptIntranet  
  
     Это значение будет преобразовать все имена доменов из Юникода не в локальной интрасети эквиваленты в Punycode (IDN-имена). В этом случае чтобы обрабатывать международные имена в локальной интрасети, DNS-серверы, которые используются для интрасети должны поддерживать разрешение имен в Юникоде.  
  
-   IDN включена = нет  
  
     Это значение не будет преобразовать имена доменов из Юникода в Punycode. Это значение по умолчанию, которое совместимо с поведением .NET Framework 2.0.  
  
 При включенном IDN метки в Юникоде в доменном имени будут преобразованы в аналоги в кодировке Punicode. Имена Punicode содержат только символы ASCII и всегда начинаются с префикса "xn--". Это сделано для того, чтобы поддерживать существующие DNS-серверы в интрасети, так как большинство DNS-серверов поддерживает только символы ASCII (см. RFC 3940).  
  
### <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.  
  
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
