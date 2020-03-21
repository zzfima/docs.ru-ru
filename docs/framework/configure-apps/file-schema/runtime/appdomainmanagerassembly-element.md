---
title: Элемент <appDomainManagerAssembly>
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154435"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerСборка> Элемент
Указывает сборку, предоставляющую диспетчер домена приложения для домена приложения, по умолчанию используемого в процессе.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerСборка>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут. Упогоняет имя дисплея сборки, которая обеспечивает менеджер домена приложения для домена приложения по умолчанию в процессе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 Чтобы указать тип менеджера домена приложения, необходимо указать как этот элемент, так и [ \<элемент appDomainManagerType>](appdomainmanagertype-element.md) элемент. Если какой-либо из этих элементов не указан, другой игнорируется.  
  
 При загрузке домена приложения <xref:System.TypeLoadException> по умолчанию, выбрасывается, если указанная сборка не существует или если сборка не содержит тип, указанный [ \<элементом appDomainManagerType>;](appdomainmanagertype-element.md) и процесс не может начаться. Если сборка найдена, но информация <xref:System.IO.FileLoadException> о версии не совпадает, a брошена.  
  
 При указании типа менеджера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип менеджера домена приложения. Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и свойства, чтобы указать другой тип менеджера домена приложения для нового домена приложения.  
  
 Определение типа диспетчера домена приложения требует, чтобы приложение было полностью доверчиво. (Например, приложение, работая на рабочем столе, имеет полное доверие.) Если приложение не имеет полного <xref:System.TypeLoadException> доверия, a брошен.  
  
 Для формата названия отображения сборки см. <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>  
  
 Этот элемент конфигурации доступен только в системе .NET 4 и позже.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что менеджер домена `MyMgr` приложения `AdMgrExample` для домена приложения приложения по умолчанию процесса — это тип сборки.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<appDomainManagerType> Элемент](appdomainmanagertype-element.md)
- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [Метод SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
