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
ms.openlocfilehash: aa03179df1cd2595b4be428106dd3ec10b309317
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252553"
---
# <a name="gcserver-element"></a>\<Элемент > gcServer
Указывает, выполняет ли среда CLR сборку мусора сервера.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<gcServer >**  
  
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
 Нет.  
  
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
> В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора. С версии .NET Framework 4.5 серверная сборка мусора является параллельной. Чтобы использовать непараллельную сборку мусора сервера, `<gcServer>` установите для `true` элемента значение, а `false` [ \<для элемента gcConcurrent >](gcconcurrent-element.md) значение.  
  
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
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Отключение параллельной сборки мусора](gcconcurrent-element.md#to-disable-background-garbage-collection)
