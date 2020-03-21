---
title: Элемент <appDomainManagerType>
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154434"
---
# <a name="appdomainmanagertype-element"></a>\<appDomainManagerType> Элемент
Указывает тип, который служит диспетчером домена приложения для домена приложения, используемого по умолчанию.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`value`|Обязательный атрибут. Упогоняет имя типа, включая пространство имен, которое служит в качестве менеджера домена приложения для домена приложения по умолчанию в процессе.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 Чтобы указать тип менеджера домена приложения, необходимо указать как этот элемент, так и [ \<элемент appDomainManagerAssembly>](appdomainmanagerassembly-element.md) элемент. Если какой-либо из этих элементов не указан, другой игнорируется.  
  
 При загрузке <xref:System.TypeLoadException> домена приложения по умолчанию, если указанный тип не существует в сборке, указанной [ \<элементом appDomainManagerAssembly>;](appdomainmanagerassembly-element.md) и процесс не может начаться.  
  
 При указании типа менеджера домена приложения для домена приложения по умолчанию другие домены приложений, созданные из домена приложения по умолчанию, наследуют тип менеджера домена приложения. Используйте <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> и свойства, чтобы указать другой тип менеджера домена приложения для нового домена приложения.  
  
 Определение типа диспетчера домена приложения требует, чтобы приложение было полностью доверчиво. (Например, приложение, работая на рабочем столе, имеет полное доверие.) Если приложение не имеет полного <xref:System.TypeLoadException> доверия, a брошен.  
  
 Формат типа и пространства имен является тем же форматом, который используется для <xref:System.Type.FullName%2A?displayProperty=nameWithType> свойства.  
  
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
- [\<appDomainManagerСборка> Элемент](appdomainmanagerassembly-element.md)
- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
- [Метод SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
