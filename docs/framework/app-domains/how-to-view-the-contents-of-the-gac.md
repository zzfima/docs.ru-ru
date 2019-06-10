---
title: Практическое руководство. Просмотр содержимого глобального кэша сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c319c5f7c9bb808b2ce7ee10178722287e456339
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486425"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Практическое руководство. Просмотр содержимого глобального кэша сборок

Используйте [средство глобального кэша сборок (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) для просмотра содержимого глобального кэша сборок (GAC).

## <a name="view-the-assemblies-in-the-gac"></a>Просмотр сборок в GAC

Чтобы просмотреть список сборок в GAC, откройте [командную строку разработчика для Visual Studio](../tools/developer-command-prompt-for-vs.md), а затем введите следующую команду:

```shell
gacutil -l
```

- или -

```shell
gacutil /l
```

> [!NOTE]
> В предыдущих версиях .NET Framework с помощью расширения оболочки Windows [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) можно было просматривать глобальный кэш сборок в проводнике. Начиная с версии .NET Framework 4, расширение оболочки Shfusion.dll является устаревшим.

## <a name="see-also"></a>См. также

- [Работа со сборками и глобальным кэшем сборок](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (программа глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md)
