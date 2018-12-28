---
title: '&lt;etwEnable&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6ea2f8a32a18dfce6be54ce52ce8fef4abf92ce
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610779"
---
# <a name="ltetwenablegt-element"></a>&lt;etwEnable&gt; элемент
Указывает, следует ли включить трассировку событий Windows для событий среды CLR.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<etwEnabled >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, должна ли быть включена трассировка событий Windows.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|true|Включение трассировки событий Windows. Это значение по умолчанию для версий Windows, начиная с операционными системами Windows Vista и Windows Server 2008.|  
|False|Отключение трассировки событий Windows. Это значение по умолчанию для более ранних версий Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с Windows Vista, ETW включена по умолчанию. Этот элемент используется для отключения трассировки событий Windows для приложения. В более ранних версиях Windows этот элемент используется для включения трассировки событий Windows для приложения.  
  
> [!NOTE]
>  Трассировки событий Windows может быть включен или отключен глобально на сервере с помощью параметра реестра. См. в разделе [контроль ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить отслеживание ETW для приложения.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Контроль ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md)
