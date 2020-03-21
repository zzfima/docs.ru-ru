---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154534"
---
# <a name="remove-element-for-configsections"></a>\<удалить элемент \<> для> конфигураций

Удаляет заранее определенный раздел или группу раздела.

[**\<конфигурация>**](configuration-element.md)\
&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<удалить>**

## <a name="syntax"></a>Синтаксис

```xml
<remove name="section name or section group name" />
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

Элемент ** \<удаления>** можно удалить разделы и группы разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.

## <a name="example"></a>Пример

В следующем примере показано, как использовать ** \<элемент удаления>** в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации машины.

Следующий файл овый код конфигурации машины объявляет ** \<образец разделаРаздел>: **

```xml
<!-- Machine.config file -->
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

Следующий файл конфигурации приложения код удаляет ** \<образецРаздел>** раздел. После удаления приложение не может получить настройки в ** \<>sampleSection. **

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также раздел

- [Схема конфигурации файла для рамочного соглашения .NET](index.md)
