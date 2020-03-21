---
title: Элемент <clear> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155431"
---
# <a name="clear-element-for-configsections"></a>\<четкий элемент \<> для конфигурации>

Очищает все ранее определенные разделы и группы разделов.

&nbsp; &nbsp; &nbsp; &nbsp; [** \<конфигурация**](configuration-element.md) &nbsp; &nbsp; [**>\<конфигурации>**](configsections-element-for-configuration.md) **ясной>\<**

## <a name="syntax"></a>Синтаксис

```xml
<clear/>
```

## <a name="attribute"></a>attribute

|           | Описание |
| --------- | ----------- |
| **name**  | Обязательный атрибут.<br><br>Уотек названия группы раздела или раздела для удаления. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [** \<конфигурации>** Элемент](configsections-element-for-configuration.md) | Содержит раздел конфигурации и декларации пространства имен. |

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

** \<Четкое>** элемент удаляет все разделы и группы разделов из приложения, которые были определены ранее в текущем файле конфигурации или на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

Этот пример определяет файл конфигурации машины и файл конфигурации приложения и показывает, как использовать ** \<элемент четкой>** в файле конфигурации приложения для очистки разделов, ранее определенных в файле конфигурации машины.

Следующий файл конфигурации машины код объявляет два раздела, ** \<sampleSection>** и ** \<другойSampleSection>**, которые читаются перед файлом конфигурации приложения:

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

Следующий файл конфигурации приложения очищает все ранее заявленные разделы. Приложение не может использовать или извлекать настройки ни в одном из разделов, которые были заявлены в файле конфигурации машины. Тем не менее, он может использовать настройки из ** \<другогораздела>,** потому что он приходит после ** \<четкого>** элемента.

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также раздел

- [Схема конфигурации файла для рамочного соглашения .NET](index.md)
