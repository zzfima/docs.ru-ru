---
title: '&lt;модуль&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 06c653d8759224e1112183a7e86e9797a97402af
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltmodulegt-element-network-settings"></a>&lt;модуль&gt; элемент (параметры сети)
Добавляет в приложение новый модуль прокси-сервера.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<модуль >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`type`|Полное имя типа (обозначается <xref:System.Type.FullName%2A> свойства) и имя сборки (обозначается <xref:System.Reflection.Assembly.FullName%2A> свойства), разделенных запятыми, реализующая прокси-сервер.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="remarks"></a>Примечания  
 `module` Элемент регистрирует прокси-классы, реализующие <xref:System.Net.IWebProxy> интерфейса. После регистрации прокси-класса элемент `module` может использоваться для запроса данных через поддерживаемый прокси.  
  
 Значение для `type` атрибут должен иметь имя класса, модуля и имя из его соответствующий динамических ссылок библиотеки (DLL).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере регистрируется пользовательский прокси-класс.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
