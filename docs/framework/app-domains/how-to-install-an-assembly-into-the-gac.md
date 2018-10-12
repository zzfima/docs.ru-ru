---
title: Установка сборки в глобальный кэш сборок
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584585"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Практическое руководство. Установка сборки в глобальный кэш сборок

Существует два способа установки сборки со строгим именем в глобальный кэш сборок (GAC).

> [!IMPORTANT]
> В кэш могут быть установлены только сборки со строгими именами. Сведения о создании сборки со строгим именем см. в разделе [Практическое руководство. Подписание сборки строгим именем](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Установщик Windows

[Установщик Windows](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache) — средство установки Windows, которое рекомендуется использовать для добавления сборок в GAC. Установщик Windows предоставляет возможность подсчета ссылок на сборки в GAC и другие дополнительные возможности. Создать пакет установщика для установщика Windows можно с помощью [расширения Wix Toolset для Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

## <a name="global-assembly-cache-tool"></a>Средство глобального кэша сборок

[Средство глобального кэша сборок (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) можно использовать для добавления сборок со строгими именами в глобальный кэш сборок и для просмотра содержимого указанного кэша.

   > [!NOTE]
   > Программа Gacutil.exe предназначена только для использования в процессе разработки и не должна использоваться для установки рабочих сборок в глобальный кэш сборок.

Средство gacutil имеет следующий синтаксис:

```shell
gacutil -i <assembly name>
```

В этой команде *имя сборки* представляет собой имя сборки, устанавливаемой в глобальный кэш сборок.

В следующем примере выполняется установка сборки с именем файла `hello.dll` в глобальный кэш сборок.

```shell
gacutil -i hello.dll
```

> [!NOTE]
> В предыдущих версиях .NET Framework расширение оболочки Windows Shfusion.dll позволяло устанавливать сборки, перетаскивая их в **проводнике**. Начиная с версии .NET Framework 4, расширение оболочки Shfusion.dll является устаревшим.

## <a name="see-also"></a>См. также

- [Работа со сборками и глобальным кэшем сборок](working-with-assemblies-and-the-gac.md)
- [Практическое руководство. Удаление сборки из глобального кэша сборок](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (программа глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md)
- [Практическое руководство. Подписание сборки строгим именем](how-to-sign-an-assembly-with-a-strong-name.md)