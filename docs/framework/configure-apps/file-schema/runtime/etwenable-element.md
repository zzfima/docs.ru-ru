---
title: '&lt;etwEnable&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 267a4a29282881d18201d0cb2062e91b4ff974a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
|enabled|Обязательный атрибут.<br /><br /> Указывает, включены ли трассировки событий Windows.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|Включение трассировки событий Windows. Это значение по умолчанию для версий Windows, начиная с ОС Windows Vista и Windows Server 2008.|  
|False|Отключение трассировки событий Windows. Это значение по умолчанию для более ранних версиях Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с Windows Vista, Трассировка включена по умолчанию. Этот элемент используется для отключения трассировки событий Windows для приложения. В более ранних версиях Windows этот элемент используется для включения ETW для приложения.  
  
> [!NOTE]
>  Трассировки событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра. В разделе [управление ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).  
  
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
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Контроль ведения журнала .NET Framework](../../../../../docs/framework/performance/controlling-logging.md)
