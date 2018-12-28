---
title: '&lt;disableCachingBindingFailures&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78ca269dacc33fb441310ad00ba2548826f5403e
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610519"
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a>&lt;disableCachingBindingFailures&gt; элемент
Указывает, следует ли отключить кэширование привязки ошибок, возникающих при проверке сборка не найдена.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<disableCachingBindingFailures >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, следует ли отключить кэширование привязки ошибок, возникающих при проверке сборка не найдена.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключайте кэширование привязки ошибок, возникающих при проверке сборка не найдена. Это поведение привязки по умолчанию, начиная с .NET Framework версии 2.0.|  
|1|Отключите кэширование привязки ошибок, возникающих при проверке сборка не найдена. Этот параметр возвращается к поведению привязки в .NET Framework версии 1.1.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с .NET Framework версии 2.0, поведение по умолчанию для загрузки сборок — все привязки и при загрузке сбоев. То есть при неудачной попытке загрузить сборку, последующие запросы на загрузку и той же сборки и не немедленно, любая попытка найти сборку. Этот элемент отключает поведение по умолчанию для ошибок привязки, возникающих, так как не удалось найти сборки в путь поиска сборок. Эти сбои throw <xref:System.IO.FileNotFoundException>.  
  
 Некоторые привязки и сбои при загрузке не затрагиваются этим элементом и всегда кэшируются. Эти сбои возникают, так как сборка найдена, но не может быть загружен. Они создают <xref:System.BadImageFormatException> или <xref:System.IO.FileLoadException>. В следующем списке приведены некоторые примеры таких сбоев.  
  
-   При попытке загрузить файл не является допустимой сборкой, последующие попытки загрузить сборку завершится ошибкой, даже если неправильный файл заменяется правильную сборку.  
  
-   При попытке загрузить сборку, который заблокирован в файловой системе, последующие попытки загрузить сборку не удастся даже после освобождения сборки файловой системой.  
  
-   Если один или несколько версий сборки, который вы пытаетесь загрузить в путь поиска сборок, но конкретной версии, для которого запрашивается не между ними, последующие попытки загрузить эту версию завершится ошибкой, даже если правильная версия перемещается в путь поиска сборок.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как отключить кэширование ошибок привязки сборок, возникающих при проверке сборка не найдена.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
