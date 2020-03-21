---
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155483"
---
# <a name="assemblybinding-element-for-configuration"></a>\<сборкаСвязы> \<элемент для> конфигурации

Определяет политику привязки сборок на уровне конфигурации.

конфигурация &nbsp; &nbsp; [** \<>**](configuration-element.md) ** \<сборкиОбязательная>**

## <a name="syntax"></a>Синтаксис

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | Описание |
| --------- | ----------- |
| **xmlns** | Обязательный атрибут.<br><br>Задает пространство имен XML, необходимое для привязки сборок. Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [**\<конфигурация>**](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-element"></a>Дочерний элемент

|     | Описание |
| --- | ----------- |
| [**\<связаныКонфигурация>**](linkedconfiguration-element.md) | Указание файла конфигурации, который следует включить. |

## <a name="remarks"></a>Remarks

[** \<LinkedConfiguration>**](linkedconfiguration-element.md) элемент упрощает управление сборками компонентов, позволяя файлам конфигурации приложений включать файлы конфигурации сборки в хорошо известных местах, а не дублировать настройки конфигурации сборки.

> [!NOTE]
> ** \<Элемент linkedConfiguration>** не поддерживается для приложений с windows бок о бок.

## <a name="example"></a>Пример

Ниже приводится следующий пример, как включить файл конфигурации на локальном жестком диске:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>См. также раздел

- [Схема конфигурации файла для рамочного соглашения .NET](index.md)
