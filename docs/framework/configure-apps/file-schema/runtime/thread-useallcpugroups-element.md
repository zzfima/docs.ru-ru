---
title: Элемент <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 236953cc1a430a1dd2a2fbb633c7ef06e6ba200f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230841"
---
# <a name="threaduseallcpugroups-element"></a>\<Thread_UseAllCpuGroups > элемент
Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.  
  
 \<configuration>  
\<Среда выполнения >  
<Thread_UseAllCpuGroups>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, распределяет ли среда выполнения управляемые потоки во всех группах ЦП.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения не распространяет управляемые потоки по нескольким группам ЦП. Это значение по умолчанию.|  
|`true`|Среда выполнения распространяет управляемые потоки по нескольким группам ЦП, если компьютер имеет несколько групп ЦП и [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) включен элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Если компьютер имеет несколько групп ЦП, позволяя причины этого элемента выполнение распределенного управляемые потоки во всех группах ЦП. Чтобы использовать эту функцию, необходимо также включить [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент, который учитывает все ядра во время создания и распределения куч и расширяет их возможности сбора мусора для всех групп ЦП. Включение [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент требует включения [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемент. Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемент не оказывает влияния.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как включить поддержку нескольких групп ЦП.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<GCCpuGroup > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
