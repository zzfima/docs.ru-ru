---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153738"
---
# <a name="section-element"></a>\<раздел> элемент

Содержит декларацию раздела конфигурации.

[**\<конфигурация>**](configuration-element.md)\
&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел>**

[**\<конфигурация>**](configuration-element.md)\
&nbsp;&nbsp;[**\<конфигурации>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<разделГруппа>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел>**

## <a name="syntax"></a>Синтаксис

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Требуемые атрибуты

|           | Описание |
| --------- | ----------- |
| **name**  | Упогоняет название раздела конфигурации. |
| **тип**  | Упогоняет название класса обработчика раздела конфигурации, который читает раздел из файла конфигурации. Значение типа имеет синтаксис "полностью квалифицированный раздел-обработчик-класс-имя, просто-сборка-имя". Простое имя сборки — это корневое имя файла без расширения файла *.dll.* |

## <a name="optional-attributes"></a>Дополнительные атрибуты

Следующие атрибуты применимы только для ASP.NET приложений. Система конфигурации игнорирует эти атрибуты для других типов приложений.

|                     | Описание |
| ------------------- | ----------- |
| **allowDefinition** | Определяет, в какой конфигурации можно использовать файл раздела. Используйте одно из следующих значений:<br><br>**Везде**<br>Позволяет использовать раздел в любом файле конфигурации. Это значение по умолчанию.<br>**МашинаТолько**<br>Позволяет использовать раздел только в файле конфигурации машины *(Machine.config).*<br>**Машинное применение**<br>Позволяет использовать раздел в файле конфигурации машины или файле конфигурации приложения. |
| **allowLocation**   | Определяет, можно ли использовать раздел в ** \<пределах элемента>местоположения.** Используйте одно из следующих значений:<br><br>**true**<br>Позволяет использовать раздел в ** \<пределах элемента>местоположения.** Это значение по умолчанию.<br>**false**<br>Не позволяет использовать раздел в ** \<элементе>местоположения.** |

## <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [** \<конфигурации>** Элемент](configsections-element-for-configuration.md) | Содержит раздел конфигурации и декларации пространства имен. |
| [** \<разделГруппа>** Элемент](sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |

> [!NOTE]
> ** \<Раздел>** элемент является элементом ребенка либо ** \<configSections>** или ** \<разделаГруппа>** но не оба.

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Remarks

Объявление раздела конфигурации по существу определяет новый элемент для файла конфигурации. Новый элемент содержит настройки, которые читает обработчик раздела <xref:System.Configuration.IConfigurationSectionHandler> конфигурации (т.е. класс, реализующий интерфейс). Атрибуты и элементы ребенка в определенном разделе зависят от обработчика раздела, который вы используете для чтения настроек.

Объявление обработчика раздела конфигурации в файле *Machine.config* позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если атрибут **allowDefinition** не указывает обратное.

## <a name="example"></a>Пример

В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела:

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler"
             allowLocation="false" />
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
