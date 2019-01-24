---
title: '&lt;gcAllowVeryLargeObjects&gt; элемент'
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16a6b497136b6cffabeb4151e54bec8d80928b5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549123"
---
# <a name="ltgcallowverylargeobjectsgt-element"></a>&lt;gcAllowVeryLargeObjects&gt; элемент
На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).  
  
 \<Конфигурация > элемент  
\<Среда выполнения > элемент  
\<gcAllowVeryLargeObjects > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, включены ли массивов, размер которых превышает 2 ГБ в общий размер на 64-разрядных платформах.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Больше, чем 2 ГБ, общий размер массивов не включены. Это значение по умолчанию.|  
|`true`|Больше, чем 2 ГБ, общий размер массивов включены на 64-разрядных платформах.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 С помощью этого элемента в файле конфигурации приложения позволяет использовать массивы, размер которых превышает 2 ГБ, но не изменяет другие ограничения на размер объекта или массива:  
  
-   Максимальное количество элементов в массиве является <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
-   Максимальный индекс в любом измерении единый — 2,147,483,591 (0x7FFFFFC7) для массивов байтов и массивы структур однобайтовых и 2,146,435,071 (0X7FEFFFFF) для других типов.  
  
-   Максимальный размер строки и другие не являющиеся массивами объекты не изменяется.  
  
> [!CAUTION]
>  Прежде чем включать эту функцию, убедитесь, что приложение не содержит небезопасный код, который предполагается, что все массивы меньше, чем размером 2 ГБ. Например небезопасный код, который использует массивы в качестве буфера, можно привести к переполнению буфера записывается на предположении, что массивы не может превышать 2 ГБ.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить эту функцию для приложения.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
