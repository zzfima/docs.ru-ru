---
title: элемент <clear> для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fff5a5c2a523480f2eaebb127ec98ff6e9908acf
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088716"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Clear > элемента для NameValueSectionHandler и DictionarySectionHandler

Удаляет все ранее определенные параметры в разделе.

[ **\<configuration>** ](configuration-element.md)\
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**

## <a name="syntax"></a>Синтаксис

```xml
<clear />
```

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ------------|
| [ **\<sectionName >** Дерев](custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>. |

## <a name="child-elements"></a>Дочерние элементы

Отсутствуют

## <a name="remarks"></a>Заметки

Можно использовать элемент **\<clear >** , чтобы удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В этом примере определяется файл конфигурации компьютера и файл конфигурации приложения, а также демонстрируется использование элемента **\<clear >** в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации компьютера.

В следующем коде файла конфигурации компьютера объявляется раздел **\<мисектион >** :

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

Следующий код файла конфигурации приложения удаляет все параметры из **\<мисектион >** . Приложение не может получить параметры, которые были объявлены в, в разделе **\<мисектион >** файла конфигурации компьютера.

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a>файл конфигурации

Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
