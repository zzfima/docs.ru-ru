---
title: "&lt;PreferComInsteadOfManagedRemoting&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad60d73e30bf02fd52f9c8f3bd707b571959bdd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; элемент
Указывает, использует ли среда выполнения COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.  
  
 \<configuration>  
\<Среда выполнения >  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, использует ли среда выполнения COM-взаимодействия вместо удаленное взаимодействие через границы домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения. Это значение по умолчанию.|  
|`true`|Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 При задании `enabled` атрибут `true`, среда выполнения ведет себя следующим образом:  
  
-   Среда выполнения не вызывает [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) для [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) интерфейс при [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) интерфейс входит в домен через COM-интерфейса. Вместо этого она создает [вызываемой оболочки времени выполнения](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (времени выполнения RCW) для объекта.  
  
-   Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) интерфейс для любого [вызываемая оболочка COM](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), будет создана в этом домене.  
  
 Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами через границы домена приложения используют COM и COM-взаимодействие вместо удаленного взаимодействия.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что среда выполнения должна использовать COM взаимодействия через границы изоляции:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
