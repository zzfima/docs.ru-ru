---
title: '&lt;URI&gt; элемент (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 05b2fb4255643f657f37012ec51a1b29ed68095d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lturigt-element-uri-settings"></a>&lt;URI&gt; элемент (параметры Uri)
Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).  
  
## <a name="schema-hierarchy"></a>Схема иерархии  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI >](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[IDN](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Указывает, применяется ли синтаксический анализ международного кода ресурса (IRI) к <xref:System.Uri> и следует ли применять правила синтаксического анализа IRI.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Конфигурации](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Содержит параметры для всех пространств имен.|  
  
## <a name="remarks"></a>Примечания  
 `uri` Элемент содержит настройки для членов <xref:System.Uri> класс, используемый классами в <xref:System.Net> пространства имен. Параметры настройки поддержки IRI и IDN.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и имен IDN. В примере также сбрасываются все параметры схем и добавляется поддержка не экранирования разделителей закодированные пути для схемы http.  
  
### <a name="code"></a>Код  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
