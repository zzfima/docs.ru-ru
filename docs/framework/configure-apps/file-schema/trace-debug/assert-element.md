---
title: Элемент <assert>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: 2f3823265e358976f970cdfa36772d2251894280
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197611"
---
# <a name="assert-element"></a>\<Assert > элемент
Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.  
  
 \<configuration>  
\<system.diagnostics>  
\<assert>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`assertuienabled`|Необязательный атрибут.<br /><br /> Указывает, является ли чтобы отобразить окно сообщения при **Debug.Assert** метод, результатом которого является **false**.|  
|`logfilename`|Необязательный атрибут.<br /><br /> Указывает имя файла для записи сообщения, если **Debug.Assert** принимает значение **false**.|  
  
## <a name="assertuienabled-attribute"></a>assertuienabled атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`true`|Отображает окно сообщения. Это значение по умолчанию.|  
|`false`|Не отображает окно сообщения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Оба атрибута в  **\<assert >** являются необязательными. Вы можете отключить окон сообщений без указания файла для записи сообщений в, или можно указать файл для записи, что при этом не отключать окна сообщений.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить отображение окон сообщений при вызове **Debug.Assert** и записи сообщений `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Debug>
- [Схема параметров трассировки и отладки](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
