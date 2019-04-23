---
title: Элемент <developmentMode>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf840035150f08c894c984213af9a0abe6e95af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192060"
---
# <a name="developmentmode-element"></a>\<developmentMode > элемент
Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.  
  
 \<configuration>  
\<Среда выполнения >  
\<developmentMode >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**developerInstallation**|Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.|  
  
## <a name="developerinstallation-attribute"></a>developerInstallation атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|**true**|Поиск сборок в каталогах, указанных в переменной среды DEVPATH.|  
|**false**|Не выполняет поиск сборок в каталогах, указанных в переменной среды DEVPATH. Это значение по умолчанию|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр только во время разработки. Среда выполнения не проверяет версии на в DEVPATH сборок со строгим именем. Он просто использует первый найденную сборку.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как среда выполнения для поиска сборок в каталогах, указанных в переменной среды DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Практическое руководство. Поиск сборок с помощью DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
