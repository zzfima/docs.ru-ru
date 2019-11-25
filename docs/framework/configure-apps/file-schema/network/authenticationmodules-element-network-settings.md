---
title: Элемент <authenticationModules> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: bacaaf92464a355804a9ea8307f6e6f1caac1f05
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087611"
---
# <a name="authenticationmodules-element-network-settings"></a>Элемент \<authenticationModules > (параметры сети)
Указывает модули, используемые для проверки подлинности сетевых запросов.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<authenticationModules >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](add-element-for-authenticationmodules-network-settings.md)|Добавляет модуль проверки подлинности в приложение.|  
|[clear](clear-element-for-authenticationmodules-network-settings.md)|Удаляет из приложения все модули проверки подлинности.|  
|[remove](remove-element-for-authenticationmodules-network-settings.md)|Удаляет модуль проверки подлинности из приложения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `authenticationModule` указывает модули проверки подлинности, которые выполняют процесс проверки подлинности с сервером. Модуль проверки подлинности должен реализовывать интерфейс <xref:System.Net.IAuthenticationModule>.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере включается модуль проверки подлинности. Необходимо заменить значения для Version и PublicKeyToken правильными значениями для указанного модуля.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [Схема параметров сети](index.md)
