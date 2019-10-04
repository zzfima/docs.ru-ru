---
title: Практическое руководство. Удаление сборки из глобального кэша сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a085ff6955f706bcd90f895c42e6405a28d408a
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834042"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a>Практическое руководство. Удаление сборки из глобального кэша сборок

Существует два способа удаления сборки из глобального кэша сборок.

- С помощью [средства глобального кэша сборок (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md). Этот вариант можно использовать для удаления сборок, помещенных в глобальный кэш сборок во время разработки и тестирования.

- С помощью [установщика Windows](/windows/desktop/Msi/windows-installer-portal). Этот вариант следует использовать для удаления сборок при тестировании пакетов установки и для рабочих систем.

## <a name="removing-an-assembly-with-gacutilexe"></a>Удаление сборки с помощью Gacutil.exe

В командной строке введите следующую команду:

**gacutil –u** \<*имя_сборки*>

В этой команде *имя_сборки* представляет собой имя сборки, удаляемой из глобального кэша сборок.

> [!WARNING]
> Не следует использовать Gacutil.exe для удаления сборок в рабочих системах, так как есть вероятность того, что некоторым приложениям эта сборка все еще нужна. Вместо этого следует использовать установщик Windows, который ведет счетчик ссылок для каждой сборки, устанавливаемой в глобальном кэше сборок.

В следующем примере удаляется сборка с именем `hello.dll` из глобального кэша сборок:

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a>Удаление сборки с помощью установщика Windows

В разделе **Программы и компоненты** на **панели управления** выберите приложение, которое нужно удалить. Если пакет установки разместил сборки в глобальном кэше сборок, установщик Windows удалит их, если они не используются другим приложением.

> [!NOTE]
> Установщик Windows ведет счетчик ссылок для сборок, установленных в глобальном кэше сборок. Сборка удаляется из глобального кэша сборок только в том случае, если число ссылок на нее достигает нуля, то есть если она не используется ни одним приложением, установленным с помощью пакета установщика Windows.

## <a name="see-also"></a>См. также

- [Работа со сборками и глобальным кэшем сборок](working-with-assemblies-and-the-gac.md)
- [Практическое руководство. Установка сборки в глобальный кэш сборок](install-assembly-into-gac.md)
- [Gacutil.exe (программа глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md)
