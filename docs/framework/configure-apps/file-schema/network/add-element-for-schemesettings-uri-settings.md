---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: e7606a1185d406384a926ca4dcb7c42586461574
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139936"
---
# <a name="add-element-for-schemesettings-uri-settings"></a>\<Добавить > элемент для schemeSettings (параметры Uri)
Добавляет параметр схемы для имени схемы.  
  
 \<configuration>  
\<URI >  
\<schemeSettings >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Имя схемы, к которому применяется этот параметр. Только поддерживаемые значения: имя = «http» и имя = «https».|  
  
## <a name="attribute-name-attribute"></a>{Атрибут name} Атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|genericUriParserOptions|Параметры средства синтаксического анализа для этой схемы. Поддерживается только значение genericUriParserOptions = «DontUnescapePathDotsAndSlashes».|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<schemeSettings> (параметры URI)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути. Это было реализовано в качестве механизма защиты от атак, следующим образом:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути. Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
