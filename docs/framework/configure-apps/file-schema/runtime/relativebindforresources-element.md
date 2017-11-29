---
title: "&lt;relativeBindForResources&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ffd5b62e0759b3a4f97e105e884912a41f0117de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltrelativebindforresourcesgt-element"></a>&lt;relativeBindForResources&gt; элемент
Оптимизирует поиск вспомогательных сборок.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<relativeBindForResources > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, является ли среда оптимизирует поиск вспомогательных сборок.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения не Оптимизируйте поиск вспомогательных сборок. Это значение по умолчанию.|  
|`true`|Среда выполнения оптимизирует поиск вспомогательных сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Как правило, диспетчер ресурсов проверяет наличие ресурсов, как описано в [упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) раздела. Это означает, что при Resource Manager проверяет наличие определенного локализованную версию ресурса, он может поиск в глобальном кэше сборок, поиск вспомогательных сборок в папке для определенного языка и региональных параметров в запросе базу кода приложения установщика Windows и вызова <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> события. `<relativeBindForResources>` Элемент оптимизирует процесс, в котором диспетчер ресурсов выполняет поиск вспомогательных сборок. Это может повысить производительность при поиске ресурсов при следующих условиях:  
  
-   При развертывании вспомогательную сборку в том же расположении, что и сборка кода. Другими словами Если код сборки, которая установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены существует. Если сборка кода устанавливается в базу кода приложения, вспомогательных сборок также устанавливается в папке для определенного языка и региональных параметров в базе кода.  
  
-   Когда установщика Windows не используется или редко используется для установки вспомогательных сборок по требованию.  
  
-   Когда код приложения не может обрабатывать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.  
  
 Установка `enabled` атрибут `<relativeBindForResources>` элемент `true` оптимизирует пробы диспетчера ресурсов для вспомогательных сборок следующим образом:  
  
-   Она использует расположение родительской сборки кода для проверки для вспомогательной сборки.  
  
-   Он не запрашивает установщик Windows для вспомогательных сборок.  
  
-   Не вызывалось <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.  
  
## <a name="see-also"></a>См. также  
 [Упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
