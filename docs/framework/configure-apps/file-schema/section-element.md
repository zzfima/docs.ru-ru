---
title: <section> элемент
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 64556054df2689ff758f52c7e98556997a3e9d3d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301174"
---
# <a name="section-element"></a>\<раздел > элемент

Содержит объявление раздела конфигурации.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<раздел >**

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<раздел >**

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
| **type**  | Задает имя класса обработчика раздела конфигурации, изучает раздел из файла конфигурации. Значение типа имеет синтаксис «fully-qualified-section-handler-class-name, простое имя сборки». Простое имя сборки — это имя корневого файла без *.dll* расширение файла. |

## <a name="optional-attributes"></a>Необязательные атрибуты

Следующие атрибуты применимы только для приложений ASP.NET. Система конфигурации пропускает эти атрибуты для других типов приложений.

|                     | Описание |
| ------------------- | ----------- |
| **allowDefinition** | Указывает, какой файл конфигурации, можно использовать в разделе. Необходимо использовать одно из следующих значений.<br><br>**Везде**<br>Разрешает использовать в любом файле конфигурации раздела. Это значение по умолчанию.<br>**MachineOnly**<br>Разрешает использовать только в файле конфигурации компьютера раздела (*Machine.config*).<br>**MachineToApplication**<br>Разрешает раздела для использования в файле конфигурации компьютера или файле конфигурации приложения. |
| **allowLocation**   | Определяет, используется ли в разделе  **\<расположение >** элемент. Необходимо использовать одно из следующих значений.<br><br>**true**<br>Разрешает использовать внутри раздела  **\<расположение >** элемент. Это значение по умолчанию.<br>**false**<br>Не поддерживает раздел для использования внутри  **\<расположение >** элемент. |

## <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [ **\<configSections >** элемент](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | Содержит раздел конфигурации и пространства имен объявления. |
| [ **\<sectionGroup >** элемент](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | Определяет пространство имен для разделов конфигурации. |

> [!NOTE]
> Объект  **\<разделе >** элемент является дочерним элементом элемента либо  **\<configSections >** или  **\<sectionGroup >** , но не оба.

## <a name="child-elements"></a>Дочерние элементы

None

## <a name="remarks"></a>Примечания

По сути объявление раздела конфигурации определяет новый элемент для файла конфигурации. Новый элемент содержит параметры, что обработчик раздела конфигурации (то есть класс, реализующий <xref:System.Configuration.IConfigurationSectionHandler> интерфейс) считывает. Атрибуты и дочерние элементы раздела вами зависят от обработчика раздела, используемого для чтения параметров.

Объявление обработчик раздела конфигурации в *Machine.config* файла позволяет использовать раздел конфигурации в файле конфигурации приложения на этом компьютере, если не **allowDefinition**атрибут указано иное.

## <a name="example"></a>Пример

В следующем примере показано, как определения раздела конфигурации и его параметров:

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

Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
