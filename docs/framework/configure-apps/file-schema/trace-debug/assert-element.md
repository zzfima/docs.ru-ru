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
ms.openlocfilehash: 5ba781598542d271f41476b1a1e9d61faeb6ff74
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927186"
---
# <a name="assert-element"></a>\<Assert >, элемент
Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.  
  
 \<configuration>  
\<> System. Diagnostics  
\<утверждение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`assertuienabled`|Необязательный атрибут.<br /><br /> Указывает, следует ли отображать окно сообщения, если метод **Debug. Assert** возвращает **значение false**.|  
|`logfilename`|Необязательный атрибут.<br /><br /> Указывает имя файла, в который будет записано сообщение, если **Debug. Assert** имеет значение **false**.|  
  
## <a name="assertuienabled-attribute"></a>Атрибут ассертуиенаблед  
  
|Значение|Описание|  
|-----------|-----------------|  
|`true`|Отображает окно сообщения. Это значение по умолчанию.|  
|`false`|Не отображает окно сообщения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Оба атрибута в  **\<элементе Assert >** являются необязательными. Можно отключить окна сообщений, не указывая файл для записи в него, или указать файл для записи сообщений при включении входящих в него окон сообщений.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить отображение окон сообщений при вызове **Debug. Assert** и записи сообщений в `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Debug>
- [Схема параметров трассировки и отладки](index.md)
