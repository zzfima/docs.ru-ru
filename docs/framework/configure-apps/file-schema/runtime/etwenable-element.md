---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3510cbf0a63a8031669bb7a819a8b3c7321aaea4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920766"
---
# <a name="etwenable-element"></a>\<Элемент > Етвенабле
Указывает, следует ли включить трассировку событий Windows для событий среды CLR.  
  
 \<Элемент Configuration >  
\<Элемент > среды выполнения  
\<Етвенаблед >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, включена ли трассировка событий Windows.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|Включите ETW. Это значение по умолчанию для версий Windows, начинающихся с операционных систем Windows Vista и Windows Server 2008.|  
|false|Отключите трассировку событий Windows. Это значение по умолчанию для более ранних версий Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с Windows Vista трассировка событий Windows включена по умолчанию. Используйте этот элемент, чтобы отключить ETW для приложения. В более ранних версиях Windows этот элемент используется для включения ETW для приложения.  
  
> [!NOTE]
> Трассировку событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра. См. раздел [Управление ведением журнала .NET Framework](../../../performance/controlling-logging.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить трассировку ETW для приложения.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Контроль ведения журнала .NET Framework](../../../performance/controlling-logging.md)
