---
title: Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10
description: Описание размещения приложений, требующих .NET Framework 1.1, которые больше не поддерживаются во многих версиях операционной системы Windows.
ms.date: 05/26/2017
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
ms.openlocfilehash: 6d1cb2f9251bba96d0a378bf4dbab9f7da267037
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111794"
---
# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10

.NET Framework 1.1 не поддерживается в Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 и Windows 10. В некоторых случаях для запуска приложения требуется .NET Framework версии 1.1. В этих случаях, чтобы получить обновленную версию приложения для запуска с использованием .NET Framework 3.5 с пакетом обновления 1 (SP1) или более поздней версии платформы, нужно обратиться к независимому поставщику программного обеспечения. Дополнительные сведения см. в статье [Миграция из .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-net-framework-11-from-a-cd-or-download-center"></a>Установка .NET Framework 1.1 с компакт-диска или из центра загрузки

Платформу .NET Framework 1.1 невозможно установить вручную в Windows 8, Windows 8.1, Windows Server 2012, Windows Server 2012 R2 и Windows 10 с компакт-диска или центра загрузки. Это больше не поддерживается. При попытке установить пакет отображается следующее сообщение об ошибке: "Невозможно продолжить установку, поскольку эта версия .NET Framework несовместима с ранее установленной версией". Чтобы решить эту проблему, установите [.NET Framework 3.5 с пакетом обновления 1 (SP1)](https://www.microsoft.com/download/details.aspx?id=22). Эта версия включает версию .NET Framework 2.0 (выпуск, следующий за выпуском .NET Framework 1.1), поддерживаемую в Windows 8, Windows 8.1 и Windows 10. Сначала попробуйте установить приложение, чтобы проверить, будет ли оно автоматически обновлено до более поздней версии .NET Framework. Если этого не произойдет, обратитесь к независимому поставщику программного обеспечения за обновленной версией.

## <a name="see-also"></a>См. также

- [Миграция из .NET Framework 1.1](../migration-guide/migrating-from-the-net-framework-1-1.md)
- [Установка .NET Framework 3.5 на Windows 10, Windows 8.1 и Windows 8](dotnet-35-windows-10.md)
