---
title: Элемент <gcServer>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df7ab070cc0a40f4e2f3d0545c5bc40ccb07f4d
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378039"
---
# <a name="gcserver-element"></a>\<gcServer > элемент
Указывает, выполняет ли среда CLR сборку мусора сервера.  
  
 \<configuration>  
\<Среда выполнения >  
\<gcServer >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, выполняет ли среда выполнения сборку мусора сервера.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не выполняет сборку мусора сервера. Это значение по умолчанию.|  
|`true`|Выполняет сборку мусора сервера.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR поддерживает два типа сборки мусора: сборку мусора рабочей станции, которая доступна во всех системах, и сборку мусора сервера, которая доступна в многопроцессорных системах. Для управления типом сборки мусора среды CLR можно использовать элемент `<gcServer>`. Используйте свойство <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>, чтобы определить, включена ли сборка мусора сервера.  
  
 Для однопроцессорных компьютеров сборка мусора рабочей станции по умолчанию должна быть самым быстрым вариантом. Для двухпроцессорных компьютеров можно использовать сборку мусора как рабочей станции, так и сервера. Сборка мусора сервера должно быть самым быстрым вариантом при наличии более двух процессоров.  
  
 Этот элемент может использоваться только в файле конфигурации приложения; в файле конфигурации компьютера он игнорируется.  
  
> [!NOTE]
>  В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора. С версии .NET Framework 4.5 серверная сборка мусора является параллельной. Чтобы использовать непараллельной серверной сборки мусора, задайте `<gcServer>` элемент `true` и [ \<gcConcurrent > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) для `false`.  
  
## <a name="example"></a>Пример  
 В следующем примере включается параллельная сборка мусора сервера.  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Отключение параллельной сборки мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
