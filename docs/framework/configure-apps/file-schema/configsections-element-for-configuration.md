---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 31b53837e24029fc7ff0b576d95c0213041a434e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927669"
---
# <a name="configsections-element-for-configuration"></a>\<Элемент > configSections для \<> конфигурации

Содержит раздел конфигурации и объявления пространств имен.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<> configSections**

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<раздел >** ](section-element.md) | Содержит объявление раздела конфигурации. |
| [ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |
| [ **\<remove>** ](remove-element-for-configsections.md) | Удаляет предопределенный раздел или группу разделов. |
| [ **\<clear>** ](clear-element-for-configsections.md) | Удаляет все ранее определенные разделы и группы разделов. |

## <a name="remarks"></a>Примечания

Если этот элемент находится в файле конфигурации, он должен быть первым дочерним элементом  **\<элемента Configuration >** .

## <a name="example"></a>Пример

В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
