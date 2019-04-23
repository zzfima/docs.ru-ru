---
title: Элемент <GCCpuGroup>
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85cfe57f7a3b8cfecfae4c4ae00efaea464e6120
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090346"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup > элемент
Определяет, поддерживает ли сборка мусора несколько групп ЦП.  
  
 \<configuration>  
\<Среда выполнения >  
\<GCCpuGroup>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, поддерживает ли сборка мусора несколько групп ЦП.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Сборка мусора не поддерживает несколько групп ЦП. Это значение по умолчанию.|  
|`true`|Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Когда компьютер имеет несколько групп ЦП и сборка мусора сервера включена (см. в разделе [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент), включение этого элемента расширяет сбор мусора во всех группах ЦП и использует все ядра в Учетная запись, при создании и балансировки куч.  
  
> [!NOTE]
>  Этот элемент применяется только к потоки сборки мусора. Чтобы включить выполнение распределенного пользовательские потоки во всех группах ЦП, необходимо также включить [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) элемент.  
  
## <a name="example"></a>Пример  
 В следующем примере показано включение сбора мусора для нескольких групп ЦП.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Отключение параллельной сборки мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Сборка мусора рабочей станции и сборка мусора сервера](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
