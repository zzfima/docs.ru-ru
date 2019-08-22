---
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a71c2b87d0bcb488e4e8fa4de928a103a8e9dabd
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663544"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<Элемент > Преферкоминстеадофманажедремотинг
Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.  
  
 \<configuration>  
\<> среды выполнения  
\<Преферкоминстеадофманажедремотинг >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия через границы домена приложения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения будет использовать удаленное взаимодействие через границы домена приложения. Это значение по умолчанию.|  
|`true`|Среда выполнения будет использовать COM-взаимодействие через границы домена приложения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Если для `enabled` `true`атрибута задано значение, среда выполнения ведет себя следующим образом:  
  
- Среда выполнения не вызывает [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) входит в домен через интерфейс COM. Вместо этого он формирует вызываемую [оболочку времени выполнения](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.  
  
- Среда выполнения возвращает E_NOINTERFACE при получении `QueryInterface` вызова для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой вызываемой [оболочки COM](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.  
  
 Эти два поведения гарантируют, что все вызовы через COM-интерфейсы между управляемыми объектами в границах доменов приложений используют COM и COM-взаимодействие вместо удаленного взаимодействия.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что среда выполнения должна использовать COM-взаимодействие через границы изоляции:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
