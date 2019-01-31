---
title: Элемент <iriParsing> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: a4d4df8c214efb955f8f9d6678aaf8d56de71ebc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256661"
---
# <a name="iriparsing-element-uri-settings"></a>\<iriParsing > (параметры Uri)
Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.  
  
## <a name="schema-hierarchy"></a>Схема иерархии  
 [Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<URI > (параметры Uri)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<iriParsing >](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|`enabled`|Указывает, включена ли синтаксического анализа IRI. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[URI](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).|  
  
## <a name="remarks"></a>Примечания  
 Существующий <xref:System.Uri> класс был расширен в .NET Framework 3.5. 3.0 с пакетом обновления 1 и 2.0 с пакетом обновления 1 для предоставления поддержки для международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN). Текущие пользователи не увидят любое изменение в .NET Framework 2.0, пока они не запустят IRI и IDN поддержки. Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Чтобы включить поддержку IRI, необходимы следующие два изменения:  
  
1.  Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2.0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  Укажите, должна ли применяться правила синтаксического анализа IRI. Это можно сделать в файле machine.config или в файле app.config.  
  
 Включение синтаксического анализа IRI (iriParsing включена = `true`) нормализация и проверка символов в соответствии с последней IRI правилами в RFC 3987. Значение по умолчанию — `false` и нормализации и символов проверку в соответствии с RFC 2396 и RFC 3986 (для литералов IPv6).  
  
### <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
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
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
