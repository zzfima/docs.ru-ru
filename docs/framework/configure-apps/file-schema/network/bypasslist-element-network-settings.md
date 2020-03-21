---
title: Элемент <bypasslist> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154950"
---
# <a name="bypasslist-element-network-settings"></a>\<шунтиста> элемент (Настройки сети)
Предоставляет набор регулярных выражений, описывающие адреса, которые не используют прокси.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<обвахние>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[добавление](add-element-for-bypasslist-network-settings.md)|Добавляет IP-адрес или имя DNS в список обхода прокси.|  
|[Ясно](clear-element-for-bypasslist-network-settings.md)|Очищает список обхода.|  
|[удаление](remove-element-for-bypasslist-network-settings.md)|Удаляет IP-адрес или имя DNS из списка обхода прокси.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="remarks"></a>Remarks  
 Список обхода содержит регулярные выражения, <xref:System.Net.WebRequest> описывающие URIs, доступ к которым происходит непосредственно, а не через прокси-сервер.  
  
 При указании регулярного выражения для этого элемента следует соблюдать осторожность. Регулярное выражение «a-z»\\.contoso\\.com соответствует любому хозяину в домене contoso.com, но также соответствует любому хозяину в домене contoso.com.cpandl.com. Чтобы соответствовать только хостелу в домене contoso.com, используйте якорь («$»): «А-з.з\\.contoso\\.com$».  
  
 Для получения дополнительной информации о регулярных выражениях см. [.NET Рамки Регулярные выражения](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример добавляет два адреса в список обхода. Первый обходит прокси для всех серверов в домене contoso.com; второй обходит прокси для всех серверов, IP-адреса которых начинаются с 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема настройки сети](index.md)
