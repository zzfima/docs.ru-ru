---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153910"
---
# <a name="relativebindforresources-element"></a>\<относительныеBindForРесурсы> Элемент
Оптимизирует поиск вспомогательных сборок.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<родственникБюдфорРесурсы>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, оптимизирует ли общее время выполнения языка зонд для спутниковых сборок.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Время выполнения не оптимизирует зонд для спутниковых сборок. Это значение по умолчанию.|  
|`true`|Время выполнения оптимизирует зонд для спутниковых сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Remarks  
 Как правило, ресурсный менеджер проверяет ресурсы, как это описано в теме [упаковки и развертывания ресурсов.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Это означает, что, когда диспетчер ресурсов зондирует конкретную локализованную версию ресурса, он может заглянуть в кэш глобальной сборки, заглянуть в папку для <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> конкретной культуры в кодовой базе приложения, запросить установку Windows для спутниковых сборок и поднять событие. Элемент `<relativeBindForResources>` оптимизирует способ зондирования ресурсного менеджера для спутниковых сборок. Это может повысить производительность при зондирования ресурсов при следующих условиях:  
  
- При развертывании сборки спутника в том же месте, что и сборка кода. Другими словами, если сборка кода установлена в кэше глобальной сборки, то там должны быть установлены и сборки спутников. Если сборка кода установлена в кодовой базе приложения, сборки спутников также должны быть установлены в папке, предназначенной для культуры, в базе кода.  
  
- Когда Установка Windows не используется или используется только редко для установки спутниковых сборок по требованию.  
  
- Когда код приложения не <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> обрабатывает событие.  
  
 Установка `enabled` атрибута `<relativeBindForResources>` элемента `true` для оптимизации зонда Resource Manager для спутниковых сборок следующим образом:  
  
- Он использует расположение родительского кода для зондирования для сборки спутника.  
  
- Он не задает запрос установки Windows для спутниковых сборок.  
  
- Это не поднимает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.  
  
## <a name="see-also"></a>См. также раздел

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)
