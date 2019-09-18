---
title: <Directives>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049881"
---
# <a name="directives-element-net-native"></a>\<Директивы > элемент (.NET Native)
Корневой элемент в каждом файле директив среды выполнения для .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`xmlns`|Пространство имен XML. Его значение всегда равно **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .|  
  
## <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.|  
|[\<Library>](library-element-net-native.md)|Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.  
  
 Элемент `<Directives>` может содержать ноль или один элемент [\<Application>](application-element-net-native.md) и ноль, один или более элементов [\<Library>](library-element-net-native.md).  
  
## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
