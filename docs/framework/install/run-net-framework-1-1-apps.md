---
title: Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1364eebf4d94a117a3ee7f0912b6ff4090e93853
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960032"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10

.NET Framework 1.1 не поддерживается в операционных системах Windows 8, Windows 8.1, Windows Server 2012, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10. В некоторых случаях явно указывается, что для работы приложения требуется именно .NET Framework 1.1. В этих случаях следует обратиться к независимому поставщику программного обеспечения, чтобы получить обновленную версию приложения для запуска с использованием .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии платформы. Дополнительные сведения см. в разделе [Миграция из .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Установка .NET Framework 1.1 с компакт-диска или из Центра загрузки

Платформу .NET Framework 1.1 невозможно установить вручную Windows 8, Windows 8.1, Windows Server 2012, [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10. Оно более не поддерживается. При попытке установить пакет отображается следующее сообщение об ошибке: "Невозможно продолжить установку, поскольку эта версия .NET Framework несовместима с ранее установленной версией". Чтобы решить эту проблему, установите [.NET Framework 3.5 с пакетом обновления 1 (SP1)](https://www.microsoft.com/download/details.aspx?id=22). Эта версия включает .NET Framework 2.0 (выпуск, следующий за выпуском .NET Framework 1.1), поддерживаемую в Windows 8, Windows 8.1 и Windows 10. Сначала попробуйте установить приложение, чтобы проверить, будет ли оно автоматически обновлено до более поздней версии .NET Framework. Если этого не произойдет, обратитесь к независимому поставщику программного обеспечения за обновленной версией.

## <a name="see-also"></a>См. также

- [Миграция из .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Установка .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8](dotnet-35-windows-10.md)
