---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154651"
---
# <a name="schemesettings-element-uri-settings"></a>\<Элемент schemeSettings> (параметры URI)
Определяет, как <xref:System.Uri> анализируется для определенных схем.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 None  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[добавление](add-element-for-schemesettings-uri-settings.md)|Добавляет настройку схемы для имени схемы.|  
|[Ясно](clear-element-for-schemesettings-uri-settings.md)|Очищает все существующие настройки схемы.|  
|[удаление](remove-element-for-schemesettings-uri-settings.md)|Удаляет настройку схемы для имени схемы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|Содержит настройки, определяющие, как система .NET обрабатывает веб-адреса, выраженные с помощью единых идентификаторов ресурсов (URIs).|  
  
## <a name="remarks"></a>Remarks  
 По умолчанию <xref:System.Uri?displayProperty=nameWithType> класс оон избегает процентов закодированных делимитеров пути перед выполнением сжатия пути. Это было реализовано в качестве механизма безопасности от атак, как следующее:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Если этот URI передается модулям, не обрабатываемым закодированными символами процентов правильно, это может привести к тому, что следующая команда будет выполнена сервером:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 По этой <xref:System.Uri?displayProperty=nameWithType> причине, класс сначала ООН-побегов путь разграничения, а затем применяется путь сжатия. Результат передачи вредоносного URL <xref:System.Uri?displayProperty=nameWithType> выше к классу конструктора приводит к следующему URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Это поведение по умолчанию может быть изменено, чтобы не выходить из неизменяемых процентов закодированных делимитеров пути, используя опцию конфигурации schemeSettings для определенной схемы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показана <xref:System.Uri> конфигурация, используемая классом для поддержки не исследует делимитеров пути, закодированных процентом, для схемы http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||
|-|-|  
|Пространство имен|Система|  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Схема настройки сети](index.md)
