---
title: Элемент <assemblyBinding> для <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921277"
---
# <a name="assemblybinding-element-for-configuration"></a>\<Элемент > assemblyBinding для \<> конфигурации

Определяет политику привязки сборок на уровне конфигурации.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; **\<assemblyBinding >**

## <a name="syntax"></a>Синтаксис

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Атрибут

|           | Описание |
| --------- | ----------- |
| **xmlns** | Обязательный атрибут.<br><br>Задает пространство имен XML, необходимое для привязки сборок. Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения. |

## <a name="parent-element"></a>Родительский элемент

|     | Описание |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework. |

## <a name="child-element"></a>Дочерний элемент

|     | Описание |
| --- | ----------- |
| [ **\<Линкедконфигуратион >** ](linkedconfiguration-element.md) | Указание файла конфигурации, который следует включить. |

## <a name="remarks"></a>Примечания

Элемент [**линкедконфигуратион > упрощает управление сборками компонентов, позволяя файлам конфигурации приложения включать файлы конфигурации сборки в хорошо известные расположения, а не дублировать сборку. \<** ](linkedconfiguration-element.md) параметры конфигурации.

> [!NOTE]
> Элемент **линкедконфигуратион > не поддерживается для приложений с параллельными манифестами Windows. \<**

## <a name="example"></a>Пример

В следующем примере показано, как включить файл конфигурации на локальный жесткий диск:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема файла конфигурации для .NET Framework](index.md)
