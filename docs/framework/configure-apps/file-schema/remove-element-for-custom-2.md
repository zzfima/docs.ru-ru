---
title: <remove>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920951"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Удаление элемента > для NameValueSectionHandler и DictionarySectionHandler

Удаляет ранее определенный параметр.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**

## <a name="syntax"></a>Синтаксис

```xml
<add remove="key" />
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **key**   | Обязательный атрибут.<br><br>Задает имя удаляемого параметра. |

## <a name="parent-element"></a>Родительский элемент

| Элемент | Описание |
| ------- | ------------|
| [элемент  **>\<sectionName**](custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Примечания

Элемент  **\<Remove >** можно использовать для удаления из приложения параметров, определенных на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В следующем примере показано,  **\<** как использовать элемент remove > в файле конфигурации приложения для удаления параметров, ранее определенных в файле конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел  **\<мисектион >** и `key1` добавляет в него `key2`два параметра:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

Следующий код файла конфигурации приложения удаляет `key2` параметр из  **\<мисектион >** :

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
