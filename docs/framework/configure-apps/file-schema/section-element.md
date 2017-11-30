---
title: "&lt;раздел&gt; элемент"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8ed8b0211c8366d799fe158d91dcb42f92ad0cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="section-element"></a>\<раздел > элемент

Содержит объявление раздела конфигурации.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<раздел >**

## <a name="syntax"></a>Синтаксис

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>Обязательные атрибуты

|           | Описание |
| --------- | ----------- |
| **name**  | Задает имя раздела конфигурации. |
| **type**  | Задает имя класса обработчика раздела конфигурации, который считывает раздел из файла конфигурации. Значение типа имеет синтаксис «fully-qualified-section-handler-class-name простое имя сборки». Простое имя сборки является имя корневого файла без *.dll* расширение имени файла. |

## <a name="optional-attributes"></a>Необязательные атрибуты

Следующие атрибуты применимы только для приложений ASP.NET. Система конфигурации пропускает эти атрибуты для других типов приложений.

|                     | Описание |
| ------------------- | ----------- |
| **allowDefinition** | Указывает, какой файл конфигурации, можно использовать в разделе. Необходимо использовать одно из следующих значений.<br><br>**Everywhere**<br>Разрешает раздела для использования в любом файле конфигурации. Это значение по умолчанию.<br>**MachineOnly**<br>Разрешает использовать только в файле конфигурации компьютера раздела (*Machine.config*).<br>**MachineToApplication**<br>Разрешает раздела для использования в файле конфигурации компьютера или в файле конфигурации приложения. |
| **allowLocation**   | Определяет, может ли использоваться в разделе  **\<расположение >** элемента. Необходимо использовать одно из следующих значений.<br><br>**true**<br>Разрешает использовать внутри раздела  **\<расположение >** элемента. Это значение по умолчанию.<br>**false**<br>Разрешает использование раздела для использования в  **\<расположение >** элемента. |

## <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<configSections >** элемент](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Содержит раздел конфигурации и пространства имен объявления. |
| [**\<sectionGroup >** элемент](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |

> [!NOTE]
> Объект  **\<раздел >** элемент является дочерним элементом любого  **\<configSections >** или  **\<sectionGroup >** , но не оба.

## <a name="child-elements"></a>Дочерние элементы

Нет

## <a name="remarks"></a>Примечания

Объявление раздела конфигурации фактически определяет новый элемент для файла конфигурации. Этот элемент содержит параметры, обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейса) считывает. Атрибуты и дочерние элементы, определяемые раздела зависят от обработчика раздела, используемого для чтения параметров.

Объявление обработчика раздела конфигурации в *Machine.config* файл позволяет использовать раздел конфигурации в любом файле конфигурации приложения на этом компьютере, если не **allowDefinition**указывает атрибут, в противном случае.

## <a name="example"></a>Пример

Приведенный ниже показан способ определения раздела конфигурации и его параметров.

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

## <a name="configuration-file"></a>файл конфигурации

Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.

## <a name="see-also"></a>См. также

[Схема файла конфигурации для платформы .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
