---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51129f9bb3a278d32a5da723dcc339f5e918c0f4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289813"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources > элемент
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, является ли среда CLR оптимизирует поиск вспомогательных сборок.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Среда выполнения не Оптимизируйте поиск вспомогательных сборок. Это значение по умолчанию.|  
|`true`|Среда выполнения оптимизирует поиск вспомогательных сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Как правило, Resource Manager проверяет наличие ресурсов, как описано в статье [упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) раздела. Это означает, что при Resource Manager проверяет наличие некоторой локализованной версии ресурса, он может выглядеть в глобальном кэше сборок, поиск вспомогательных сборок в папке для определенного языка и региональных параметров в запросе базовый, код приложения установщика Windows и инициации <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий. `<relativeBindForResources>` Элемент оптимизирует процесс, в которой диспетчер ресурсов выполняет поиск вспомогательных сборок. Он может повысить производительность, если проверка для ресурсов при следующих условиях:  
  
-   Когда вспомогательная сборка развертывается в том же расположении, что и сборка кода. Другими словами Если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки должны также быть там установлены. Если сборка кода установлена в базе кода приложения, вспомогательные сборки также устанавливается в папке для определенного языка и региональных параметров в базе кода.  
  
-   Если установщик Windows не используется или используется лишь изредка для установки вспомогательных сборок по требованию.  
  
-   Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.  
  
 Установка `enabled` атрибут `<relativeBindForResources>` элемент `true` оптимизирует зонда диспетчера ресурсов для вспомогательных сборок следующим образом:  
  
-   Он использует расположение родительской сборки кода для проверки вспомогательной сборки.  
  
-   Он не запрашивает установщик Windows для вспомогательных сборок.  
  
-   Не вызывалось <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событий.  
  
## <a name="see-also"></a>См. также
- [Упаковка и развертывание ресурсов](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
