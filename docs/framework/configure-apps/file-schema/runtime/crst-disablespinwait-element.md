---
title: < Crst_DisableSpinWait > элемент
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663842"
---
# <a name="crst_disablespinwait-element"></a>\<Элемент > Crst_DisableSpinWait

Указывает, следует ли отключать режим ожидания для критической секции, если это не так.  
  
 \<configuration>  
\<> среды выполнения  
\<Crst_DisableSpinWait >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**доступной**|Указывает, отключен ли режим ожидания для критических разделов, если они не включены.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|1|Отключите режим ожидания, если критическая секция не может быть получена.|  
|0|Не отключайте режим ожидания, если критическая секция не может быть получена. Это значение по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о различных параметрах конфигурации среды выполнения.|  
  
## <a name="example"></a>Пример  

В следующем примере отключается ожидание в критических разделах, если это не так.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
