---
title: '&lt;requiredRuntime&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7cb5e29f3d7fc1faffdba01a5322f1883fca8af0
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580359"
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt; элемент
Указывает, что приложение поддерживает только версию 1.0 среды CLR. Этот элемент устарел и больше не используется. [ `supportedRuntime` ](supportedruntime-element.md) Элемента, которые должны использоваться вместо нее.
  
 \<configuration>  
\<Startup >  
\<requiredRuntime >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`version`|Необязательный атрибут.<br /><br /> Строковое значение, указывающее версию платформы .NET Framework, которая поддерживается данным приложением. Строковое значение должно соответствовать имени каталога, найден в корневом каталоге установки .NET Framework. Содержимое строкового значения не анализируется.|  
|`safemode`|Необязательный атрибут.<br /><br /> Указывает, выполняет ли код запуска среды выполнения реестра для определения версии среды выполнения.|  
  
## <a name="safemode-attribute"></a>безопасный режим атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Код запуска среды выполнения ищет в реестре. Это значение по умолчанию.|  
|`true`|Код запуска среды выполнения не выглядит в реестре.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`startup`|Содержит `<requiredRuntime>` элемент.|  
  
## <a name="remarks"></a>Примечания  
 Приложения, созданные для поддержки только версии 1.0 среды выполнения, должны использовать `<requiredRuntime>` элемент. Приложения, созданные с помощью версии 1.1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.  
  
> [!NOTE]
>  Если вы используете [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) функции для указания файла конфигурации, необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения. `<supportedRuntime>` Элемент учитывается при использовании [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 `version` Строки атрибута должно соответствовать имени папки установки для указанной версии платформы .NET Framework. Эта строка не интерпретируется. Если код запуска среды выполнения не находит соответствующей папки, среда выполнения не загружается; код запуска, отобразится сообщение об ошибке и завершает работу.  
  
> [!NOTE]
>  Код запуска для приложения, размещенного в Microsoft Internet Explorer не учитывает `<requiredRuntime>` элемент.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как указать версию среды выполнения в файле конфигурации.  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров запуска](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Указание используемой версии среды выполнения](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
