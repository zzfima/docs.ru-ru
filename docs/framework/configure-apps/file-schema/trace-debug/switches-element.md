---
title: Элемент <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088805"
---
# <a name="switches-element"></a>\<ные переключатели > элемента
Содержит ключи трассировки и уровень, на котором они установлены.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<коммутаторы >**

## <a name="syntax"></a>Синтаксис  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|Задает уровень, на котором установлен ключ трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`System.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Заметки  
 Уровень переключателя трассировки можно изменить, поместив его в файл конфигурации. Если параметр является <xref:System.Diagnostics.BooleanSwitch>, его можно включить и отключить. Если параметр является <xref:System.Diagnostics.TraceSwitch>, можно назначить ему разные уровни, чтобы указать типы трассировки или сообщения отладки, выданные приложением.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать элемент **\<switch >** , чтобы установить переключение трассировки `General` на уровень <xref:System.Diagnostics.TraceLevel> и включить `Data` логический параметр трассировки.  
  
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
