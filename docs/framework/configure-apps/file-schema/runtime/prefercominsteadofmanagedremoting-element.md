---
title: Элемент <PreferComInsteadOfManagedRemoting>
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 47c568a8d6e89a195414552b3db5953ee61d1e55
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116020"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<Преферкоминстеадофманажедремотинг > элемент
Указывает, будет ли среда выполнения использовать COM-взаимодействие вместо удаленного взаимодействия для всех вызовов через границы домена приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<преферкоминстеадофманажедремотинг >**  
  
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
  
|значения|Описание|  
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
  
## <a name="remarks"></a>Заметки  
 Если для атрибута `enabled` задано значение `true`, среда выполнения ведет себя следующим образом:  
  
- Среда выполнения не вызывает [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) , когда интерфейс [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) входит в домен через интерфейс COM. Вместо этого он формирует [вызываемую оболочку времени выполнения](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) вокруг объекта.  
  
- Среда выполнения возвращает E_NOINTERFACE при получении вызова `QueryInterface` для интерфейса [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) для любой [вызываемой оболочки COM](../../../../standard/native-interop/com-callable-wrapper.md) (CCW), созданной в этом домене.  
  
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
