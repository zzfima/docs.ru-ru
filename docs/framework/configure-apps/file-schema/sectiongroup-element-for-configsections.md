---
title: Элемент <sectionGroup> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4e28e8ccea1090e6a5704b541e09dc11681278ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920653"
---
# <a name="sectiongroup-element-for-configsections"></a>\<элемент sectionGroup > для \<> configSections

Определяет пространство имен для разделов конфигурации.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<> configSections**](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**

## <a name="syntax"></a>Синтаксис

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Указывает имя определяемой группы разделов. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [элемент  **>\<configSections**](configsections-element-for-configuration.md) | Содержит раздел конфигурации и объявления пространств имен. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<раздел >** ](section-element.md) | Содержит объявление раздела конфигурации. |

## <a name="remarks"></a>Примечания

Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными другими пользователями. Элементы  **\<sectionGroup >** можно вкладывать друг в друга.

## <a name="example"></a>Пример

В следующем примере показано, как объявить группу разделов и объявить разделы в группе разделов:

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
