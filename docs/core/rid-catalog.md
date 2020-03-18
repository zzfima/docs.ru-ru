---
title: Каталог идентификаторов сред выполнения (RID) в .NET Core
description: Сведения об идентификаторах сред выполнения и их использовании в .NET Core.
ms.date: 02/22/2019
ms.openlocfilehash: feb19632f16a047ecfb2dcb697a9b837824a1929
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451737"
---
# <a name="net-core-rid-catalog"></a>Каталог идентификаторов сред выполнения (RID) в .NET Core

RID — это сокращение от *Runtime IDentifier* (идентификатор среды выполнения). Идентификаторы RID служат для идентификации целевых платформ, на которых выполняется приложение.
Они используются пакетами .NET для представления ресурсов, специфичных для платформы, в пакетах NuGet. Некоторые примеры идентификаторов RID: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` или `osx.10.12-x64`.
Для пакетов с собственными зависимостями они указывают, на каких платформах можно восстановить пакет.

Один идентификатор RID можно задать в элементе `<RuntimeIdentifier>` вашего файла проекта. Несколько идентификаторов RID можно определить в виде списка, разделенного точкой с запятой, в элементе `<RuntimeIdentifiers>` файла проекта. Они также используются с помощью параметра `--runtime` со следующими [командами интерфейса командной строки .NET Core](./tools/index.md):

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

Идентификаторы RID, представляющие отдельные операционные системы, обычно имеют следующий формат: `[os].[version]-[architecture]-[additional qualifiers]`, где:

- `[os]` — это моникер платформы или операционной системы. Например, `ubuntu`.

- `[version]` — это версия операционной системы в виде номера, разделенного точкой (`.`). Например, `15.10`.

  - Это **не должен быть** коммерческий номер версии, так как такой номер часто представляет отдельные версии операционной системы с различными контактными зонами API.

- `[architecture]` — это архитектура процессора. Например, `x86`, `x64`, `arm` или `arm64`.

- `[additional qualifiers]` дополнительно дифференцируют разные платформы. Пример: `aot`.

## <a name="rid-graph"></a>Схема RID

Схема RID или резервная схема среды выполнения — это список идентификаторов RID, которые совместимы друг с другом. Идентификаторы RID определены в пакете [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/). Список поддерживаемых идентификаторов RID и схема RID содержатся в файле [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json), который находится в репозитории `dotnet/runtime`. В этом файле можно увидеть, что все идентификаторы RID, кроме основного, содержат оператор `"#import"`. Эти операторы указывают совместимые RID.

Когда NuGet восстанавливает пакеты, он пытается найти точное совпадение для указанной среды выполнения.
Если его не удается найти, NuGet проходит схему до тех пор, пока не найдет ближайшую совместимую систему в соответствии со схемой RID.

Ниже приведена запись для идентификатора RID `osx.10.12-x64`:

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

Приведенный выше идентификатор RID указывает, что `osx.10.12-x64` импортирует `osx.10.11-x64`. Таким образом, когда NuGet восстанавливает пакеты, он пытается найти в пакете точное совпадение для `osx.10.12-x64`. Например, если NuGet не удается найти определенную среду выполнения, он может восстановить пакеты, которые определяют среды выполнения `osx.10.11-x64`.

В следующем примере показана немного большая схема RID, которая также указана в файле *runtime.json*:

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

Все идентификаторы RID в конечном итоге сопоставляются с корневым идентификатором RID `any`.

При работе с идентификаторами RID следует учитывать некоторые моменты:

- RID являются **непрозрачными строками**, и их следует рассматривать как "черные ящики".
- Не следует создавать идентификаторы RID программным способом.
- Используйте только те идентификаторы RID, которые уже определены для платформы.
- Идентификаторы RID должны указываться точно. Предположения недопустимы.

## <a name="using-rids"></a>Использование идентификаторов RID

Для использования идентификаторов RID необходимо знать, какие идентификаторы RID существуют. В платформу регулярно добавляются новые идентификаторы.
Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории `dotnet/runtime`.

SDK для .NET Core 2.0 представляет концепцию переносных идентификаторов RID. Это новые значения, добавленные в граф RID, которые не привязаны к конкретной версии или дистрибутиву ОС и рекомендуются для использования с .NET Core 2.0 и более поздних версий. Они особенно удобны во время работы с несколькими дистрибутивами Linux, так как большинство идентификаторов RID дистрибутивов сопоставлено с переносными идентификаторами RID.

Ниже представлена небольшая выборка наиболее распространенных RID, используемых для каждой ОС.

## <a name="windows-rids"></a>Идентификаторы RID для Windows

Перечислены только распространенные значения. Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории `dotnet/runtime`.

- Переносные (.NET Core 2.0 или более поздние версии):
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- Windows 7 или Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8.1 или Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10 или Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

Дополнительные сведения см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-windows).

## <a name="linux-rids"></a>Идентификаторы RID для Linux

Перечислены только распространенные значения. Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории `dotnet/runtime`. Устройства с дистрибутивами, не перечисленными ниже, могут работать с одним из переносных идентификаторов RID. Например, для устройств Raspberry Pi с дистрибутивом Linux, которого нет в списке, можно использовать `linux-arm`.

- Переносные (.NET Core 2.0 или более поздние версии):
  - `linux-x64` (большинство дистрибутивов для компьютеров, например CentOS, Debian, Fedora, Ubuntu и производные от них);
  - `linux-musl-x64` (упрощенные дистрибутивы, которые используют [musl](https://wiki.musl-libc.org/projects-using-musl.html), например Alpine Linux);
  - `linux-arm` (дистрибутивы Linux, которые работают на архитектуре ARM, например Raspberry Pi).
- Red Hat Enterprise Linux
  - `rhel-x64` (заменен на `linux-x64` для RHEL новее версии 6);
  - `rhel.6-x64` (.NET Core 2.0 или более поздние версии)
- Tizen (.NET Core 2.0 или более поздние версии)
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

Дополнительные сведения см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-linux).

## <a name="macos-rids"></a>Относительные идентификаторы macOS

Относительные идентификаторы macOS используют старую фирменную символику "OSX". Перечислены только распространенные значения. Последнюю и полную версию см. в файле [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) в репозитории `dotnet/runtime`.

- Переносные (.NET Core 2.0 или более поздние версии):
  - `osx-x64` (минимальная версия — macOS 10.12 Sierra).
- macOS 10.10 Yosemite:
  - `osx.10.10-x64`
- macOS 10.11 El Capitan:
  - `osx.10.11-x64`
- macOS 10.12 Sierra (.NET Core 1.1 или более поздние версии):
  - `osx.10.12-x64`
- macOS 10.13 High Sierra (.NET Core 1.1 или более поздние версии):
  - `osx.10.13-x64`
- macOS 10.14 Mojave (.NET Core 1.1 или более поздние версии):
  - `osx.10.14-x64`

Дополнительные сведения см. в статье [Зависимости и требования для .NET Core](install/dependencies.md?pivots=os-macos).

## <a name="see-also"></a>См. также раздел

- [Идентификаторы среды выполнения](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
