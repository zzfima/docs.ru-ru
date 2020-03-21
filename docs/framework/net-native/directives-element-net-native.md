---
title: <Directives>Элемент (.NET Родной)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181045"
---
# <a name="directives-element-net-native"></a>\<Директивы> Элемент (.NET Родной)
Корневой элемент в каждом файле директив времени выполнения для .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`xmlns`|Пространство имен XML. Его ценность всегда **"http://schemas.microsoft.com/netfx/2013/01/metadata**.|  
  
## <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Применение>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.|  
|[\<Библиотечная>](library-element-net-native.md)|Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.|  
  
## <a name="remarks"></a>Remarks  
 Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.  
  
 Элемент `<Directives>` может содержать ноль или одно [ \<приложение>](application-element-net-native.md) элемент, а также ноль, один или несколько [ \<](library-element-net-native.md) элементов библиотеки>.  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
