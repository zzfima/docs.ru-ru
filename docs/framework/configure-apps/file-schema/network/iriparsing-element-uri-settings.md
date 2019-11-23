---
title: Элемент <iriParsing> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698096"
---
# <a name="iriparsing-element-uri-settings"></a>Элемент \<элемент iriParsing > (Параметры URI)
Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<URI >** ](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент iriparsing >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|`enabled`|Указывает, включен ли синтаксический анализ IRI. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[URI](uri-element-uri-settings.md)|Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).|  
  
## <a name="remarks"></a>Примечания  
 Существующий класс <xref:System.Uri> был расширен в .NET Framework 3,5. 3,0 с пакетом обновления 1 (SP1) и 2,0 SP1 для предоставления поддержки международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN). Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN. Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.  
  
 Чтобы включить поддержку IRI, требуются следующие два изменения:  
  
1. Добавьте следующую строку в файл Machine. config в каталоге .NET Framework 2,0.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Укажите, следует ли применять правила синтаксического анализа IRI. Это можно сделать в файле machine.config или в файле app.config.  
  
 Включение синтаксического анализа IRI (элемент iriParsing enabled = `true`) будет выполнять нормализацию и проверку символов в соответствии с последними правилами IRI в RFC 3987. Значение по умолчанию — `false` и будет выполнять нормализацию и проверку символов в соответствии с RFC 2396 и RFC 3986 (для литералов IPv6).  
  
### <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN.  
  
### <a name="code"></a>Код  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
