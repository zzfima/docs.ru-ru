---
title: '&lt;Thread_UseAllCpuGroups&gt; элемент'
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47d8bcdb9bbb7ec6f5a5386a5ac5951ad8891c28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltthreaduseallcpugroupsgt-element"></a>&lt;Thread_UseAllCpuGroups&gt; элемент
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
|`false`|Среда выполнения не распределяют управляемые потоки несколько групп ЦП. Это значение по умолчанию.|  
|`true`|Среда выполнения распределяет управляемые потоки несколько групп ЦП, если компьютер имеет несколько групп ЦП и [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) включен элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Если компьютер имеет несколько групп ЦП, включение этого элемента заставляет среду выполнения для распространения управляемые потоки во всех группах ЦП. Чтобы использовать эту функцию, необходимо также включить [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемент, который расширяет сбора мусора для всех групп, ЦП и учитывает все ядра при создании и балансировки кучи. Включение [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) элемента необходимо включить [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) элемента. Если эти элементы не включены, включение `<Thread_UseAllCpuGroups>` элемент не оказывает влияния.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как включить поддержку несколько групп ЦП.  
  
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
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<GCCpuGroup > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
