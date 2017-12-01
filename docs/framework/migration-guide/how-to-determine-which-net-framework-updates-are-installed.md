---
title: "Как: определить, какие обновления для системы безопасности .NET Framework и исправления установлены"
description: "Узнайте, как определить, какие обновления для системы безопасности .NET Framework и исправлений, установленных на компьютере."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Как: определить, какие обновления для системы безопасности .NET Framework и исправления установлены

В этой статье показано, как узнать обновлений безопасности .NET Framework и исправления установлены на компьютере.

> [!NOTE]
> Все методы, представленные в этой статье требуется учетная запись с правами администратора.

## <a name="to-find-installed-updates-using-the-registry"></a>Поиск установленных обновлений с помощью реестра

Установленных обновлений и исправлений для каждой версии платформы .NET Framework, установленной на компьютере, перечислены в реестре Windows. Можно использовать редактор реестра (*regedit.exe*) программы для просмотра этих сведений.

1. Откройте программу **regedit.exe**. В Windows 8 и более поздних версиях, щелкните правой кнопкой мыши **запустить** ![логотип Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), а затем выберите **запуска**. В **откройте** введите **regedit** и выберите **ОК**.

2. В редакторе реестра откройте следующий подраздел:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Установленные обновления перечислены в подразделах, соответствующих версии .NET Framework, к которой они относятся. Каждому обновлению присваивается номер базы знаний Microsoft (KB).

В редакторе реестра версии .NET Framework и установленные обновления для каждой версии хранятся в разных подразделах. Сведения об обнаружении номеров установленных версий см. в разделе [как: определить, какие версии .NET Framework установлены](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Чтобы найти установленных обновлений с помощью запроса в реестр

В следующем примере определяется программным образом обновления для системы безопасности .NET Framework и исправлений, установленных на компьютере:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

В примере результат, аналогичный приведенному ниже:

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Чтобы найти установленных обновлений с помощью запроса в реестр с помощью PowerShell

В следующем примере показано определение обновления для системы безопасности .NET Framework и исправлений, установленных на компьютере, с помощью PowerShell:

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

В примере результат, аналогичный приведенному ниже:

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>См. также

[Как: Определение установленных версий .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Установите .NET Framework для разработчиков](../../../docs/framework/install/guide-for-developers.md)  
[Версии и зависимости](../../../docs/framework/migration-guide/versions-and-dependencies.md)
