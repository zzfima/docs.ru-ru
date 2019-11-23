---
title: Элемент <uri> (параметры URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697442"
---
# <a name="uri-element-uri-settings"></a>Элемент > \<URI (Параметры URI)
Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<uri >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[IDN](idn-element-uri-settings.md)|Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).|  
|[Элемент iriParsing](iriparsing-element-uri-settings.md)|Указывает, применяется ли синтаксический анализ международного идентификатора ресурса (IRI) к <xref:System.Uri> и должны применяться правила синтаксического анализа IRI.|  
|[schemeSettings](schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Настройка](../configuration-element.md)|Содержит параметры для всех пространств имен.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `uri` содержит параметры для членов класса <xref:System.Uri>, используемых классами в пространстве имен <xref:System.Net>. Параметры настраивают поддержку для IRI и IDN.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN. В этом примере также очищаются все параметры схемы, а затем добавляется поддержка не экранирования процентов для пути, закодированного для схемы HTTP.  
  
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
  
## <a name="see-also"></a>См. также:

- [Схема параметров сети](index.md)
