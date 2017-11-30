---
title: "&lt;UseSmallInternalThreadStacks&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2558423b412333a4d6ac9f650ad8ff3dab449d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt; элемент
Запросы, что общеязыковой среды выполнения (CLR) уменьшение памяти использовать путем указания явных размеров стека при создании определенных потоков, используемых для внутренних целей, вместо того чтобы использовать размер стека по умолчанию для этих потоков.  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<UseSmallInternalThreadStacks > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает необходимость запроса, CLR используйте явные размеры стека вместо размер стека по умолчанию при создании определенных потоков, используемых для внутренних целей. Явные размеры стека, меньше, чем размер стека по умолчанию 1 МБ.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|Запросите явные размеры стека.|  
|false|Используйте размер стека по умолчанию. Это значение по умолчанию для [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации используется для запроса Использование ограниченной виртуальной памяти в процессе, так как явные размеры потоков, среда CLR использует для своих внутренних потоков, если запрос выполняется, меньше, чем размер по умолчанию.  
  
> [!IMPORTANT]
>  Этот элемент конфигурации — это запрос, среда CLR, а не обязательна. В [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], запрос выполняется только для x86 архитектуры. Этот элемент может полностью обрабатывается в будущих версиях среды CLR или заменены явные размеры стека, всегда используются для выбранного внутренние потоки.  
  
 Указание данного элемента конфигурации меняет надежность для меньшего использования виртуальной памяти, если среда CLR учитывает запрос, поскольку меньшие размеры стека могут сделать стека выходит за пределы более вероятно.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как для запроса, что CLR использование явных размеров стека для определенных потоков, используемых для внутренних целей.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
