---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: 6a418fc546313b74bb965a0b223eca9c2e5acc08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115791"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources > элемент
Оптимизирует поиск вспомогательных сборок.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<relativeBindForResources >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, оптимизирует ли среда CLR проверку на наличие вспомогательных сборок.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения не оптимизирует зонд для вспомогательных сборок. Это значение используется по умолчанию.|  
|`true`|Среда выполнения оптимизирует зонд для вспомогательных сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Заметки  
 Как правило, диспетчер ресурсов зонды для ресурсов, как описано в разделе [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) . Это означает, что при диспетчер ресурсов зондах для конкретной локализованной версии ресурса она может искать в глобальном кэше сборок, искать в папке, зависящей от языка и региональных параметров, в базе кода приложения, запрашивать установщик Windows для вспомогательных сборок и вызывать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие. Элемент `<relativeBindForResources>` оптимизирует способ, с помощью которого диспетчер ресурсов зонды для вспомогательных сборок. Это может повысить производительность при проверке ресурсов при следующих условиях.  
  
- При развертывании вспомогательной сборки в том же расположении, что и сборка кода. Иными словами, если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены там. Если сборка кода установлена в базе кода приложения, вспомогательные сборки также должны быть установлены в папке, зависящей от языка и региональных параметров, в базе кода.  
  
- Если установщик Windows не используется или используется редко для установки вспомогательных сборок по требованию.  
  
- Если код приложения не обрабатывает событие <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
 Установив атрибут `enabled` элемента `<relativeBindForResources>` в значение `true` оптимизирует зонд диспетчер ресурсов для вспомогательных сборок следующим образом:  
  
- Он использует расположение сборки родительского кода для проверки вспомогательной сборки.  
  
- Он не запрашивает установщик Windows для вспомогательных сборок.  
  
- Он не вызывает событие <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также

- [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
