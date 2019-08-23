---
title: <clear>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927710"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a>\<Очистка элемента > для NameValueSectionHandler и DictionarySectionHandler

Удаляет все ранее определенные параметры в разделе.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**

## <a name="syntax"></a>Синтаксис

```xml
<clear />
```

## <a name="attributes"></a>Атрибуты

Отсутствуют

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ------------|
| [элемент  **>\<sectionName**](custom-element-2.md) | Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Примечания

С помощью  **\<элемента clear >** можно удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В этом примере определяются в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать **\<снимите>** элемент в файле конфигурации приложения для очистки разделов, определенных ранее в файл конфигурации компьютера.

Следующий код файла конфигурации компьютера объявляет раздел  **\<мисектион >** :

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

Следующий код файла конфигурации приложения удаляет все параметры из  **\<мисектион >** . Приложение не может получить параметры, которые были объявлены в, в  **\<разделе мисектион >** файла конфигурации компьютера.

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
