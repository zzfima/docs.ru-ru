---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155353"
---
# <a name="configsections-element-for-configuration"></a>\<конфигурация> элемента для \<> конфигурации

Содержит раздел конфигурации и декларации пространства имен.

конфигурация &nbsp; &nbsp; [** \<>**](configuration-element.md) ** \<конфигурация>**

## <a name="attributes"></a>Атрибуты

None

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<конфигурация>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<раздел>**](section-element.md) | Содержит декларацию раздела конфигурации. |
| [**\<разделГруппа>**](sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |
| [**\<удалить>**](remove-element-for-configsections.md) | Удаляет заранее определенный раздел или группу раздела. |
| [**\<ясно>**](clear-element-for-configsections.md) | Очищает все ранее определенные разделы и группы разделов. |

## <a name="remarks"></a>Remarks

Если этот элемент находится в файле конфигурации, он должен быть первым элементом элемента ** \<>конфигурации.**

## <a name="example"></a>Пример

В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела:

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

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.

## <a name="see-also"></a>См. также раздел

- [Схема конфигурации файла для рамочного соглашения .NET](index.md)
