---
title: Элемент <add> для <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 8fcd5cbe63a323a7509f5ff8c615364295c244d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920548"
---
# <a name="add-element-for-switches"></a>\<Добавьте элемент > для \<переключателей >
Задает уровень, на котором установлен ключ трассировки.  
  
 \<configuration>  
\<> System. Diagnostics  
\<переключатели >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**name**|Обязательный атрибут.<br /><br /> Указывает имя переключателя. Значение этого атрибута соответствует параметру *DisplayName* , переданному в конструктор переключателя.|  
|**value**|Обязательный атрибут.<br /><br /> Задает уровень переключателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`switches`|Содержит ключи трассировки и уровень, на котором они установлены.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации. Если параметр имеет <xref:System.Diagnostics.BooleanSwitch>значение, его можно включить и отключить. Если параметр имеет <xref:System.Diagnostics.TraceSwitch>значение, можно назначить для него разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.  
  
## <a name="example"></a>Пример  
 В следующем примере показано <xref:System.Diagnostics.TraceLevel> использование `Data` `General`  **\<элемента Add >** для задания переключателя трассировки на уровне и включения логического переключателя трассировки.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Схема параметров трассировки и отладки](index.md)
