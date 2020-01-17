---
title: Критические изменения, миграция с .NET Framework на .NET Core
description: Список критических изменений, миграция с .NET Framework на .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900124"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>Критические изменения для миграции с .NET Framework на .NET Core

Если вы переносите приложение с .NET Framework на .NET Core, критические изменения, перечисленные в этой статье, могут повлиять на работу приложения. Критические изменения группируются по категориям.

> [!NOTE]
> Эта статья не является исчерпывающим списком критических изменений между .NET Framework и .NET Core. Здесь добавляются самые важные критические изменения, как только мы о них узнаем.

## <a name="corefx"></a>CoreFX

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a>Windows Forms

Сведения о критических изменениях при переносе приложения Windows Forms из .NET Framework в .NET Core 3.0 или более поздней версии см. в разделе [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md) (Критические изменения в Windows Forms (из .NET Framework в .NET Core)).

## <a name="see-also"></a>См. также

- [API, которые всегда создают исключения в .NET Core](unsupported-apis.md)
- [Технологии .NET Framework, недоступные в .NET Core](../porting/net-framework-tech-unavailable.md)
