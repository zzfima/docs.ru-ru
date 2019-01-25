---
title: '&lt;gcConcurrent&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c83576c5c46d9a32f990d23fa20b116be36e4c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612002"
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcConcurrent&gt; элемент
Указывает, выполняет ли среда CLR сборку мусора в отдельном потоке.  
  
 \<configuration>  
\<Среда выполнения >  
\<gcConcurrent>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, выполняет ли среда выполнения сборку мусора параллельно.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Сборка мусора не выполняется параллельно.|  
|`true`|Сборка мусора выполняется параллельно. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 До .NET Framework 4 сборка мусора рабочей станции поддерживала параллельную сборку мусора, которая выполнялась в фоновом режиме в отдельном потоке. В .NET Framework 4 параллельная сборка мусора была заменена фоновой сборкой мусора, которая также выполняется в фоновом режиме в отдельном потоке. Начиная с .NET Framework 4.5 фоновая сборка мусора стала доступна для сборки мусора сервера. Элемент `<gcConcurrent>` управляет тем, какую сборку мусора выполняет среда выполнения —параллельную или фоновую сборку мусора, если она доступна, либо сборку мусора на переднем плане.  
  
> [!WARNING]
>  Начиная с .NET Framework 4, параллельная сборка мусора заменена на фоновую сборку мусора. Условия *параллельных* и *фона* являются взаимозаменяемыми в документации по .NET Framework. Чтобы отключить фоновую сборку мусора, используйте элемент `<gcConcurrent>`, как описано в этом разделе.  
  
 По умолчанию среда выполнения использует параллельную или фоновую сборку мусора, которая оптимизирована по задержкам. Если приложение подразумевает активное взаимодействие с пользователем, рекомендуется использовать параллельную сборку мусора, чтобы сократить паузы в работе приложения, возникающие при сборке мусора. Если атрибут `enabled` элемента `<gcConcurrent>` имеет значение `false`, среда выполнения использует непараллельную сборку мусора, которая оптимизирована по производительности. В следующем файле конфигурации отключается фоновая сборка мусора.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Если в файле конфигурации компьютера имеется параметр `<gcConcurrentSetting>`, он определяет значение по умолчанию для всех приложений .NET Framework. Параметр в файле конфигурации компьютера переопределяет параметр в файле конфигурации приложения.  
  
 Дополнительные сведения о параллельной и фоновой сборки мусора, см. в разделе «параллельная сборка мусора» в [основы сборки мусора](../../../../../docs/standard/garbage-collection/fundamentals.md) раздела.  
  
## <a name="example"></a>Пример  
 В следующем примере включается параллельная сборка мусора.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Основы сборки мусора](../../../../../docs/standard/garbage-collection/fundamentals.md)
