---
title: '&lt;GCCpuGroup&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25d083b730117a791fb8ab550b36f7b2e6c5f5be
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613717"
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; элемент
Определяет, поддерживает ли сборка мусора несколько групп ЦП.  
  
 \<configuration>  
\<Среда выполнения >  
\<GCCpuGroup >  
  
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
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Сборка мусора не поддерживает несколько групп ЦП. Это значение по умолчанию.|  
|`true`|Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
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
- [Практическое руководство. Отключение параллельной сборки мусора](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
- [Сборка мусора рабочей станции и сборка мусора сервера](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
