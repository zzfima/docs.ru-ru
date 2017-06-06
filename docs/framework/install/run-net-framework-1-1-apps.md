---
title: "Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10 | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows 8, running .NET Framework 1.1 apps
- .NET Framework 1.1, running on Windows 8
ms.assetid: fb14e195-fea5-4561-b9a8-60a67283edb9
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: fe9ab371ab8d3eee3778412e446b7aa30b42476b
ms.openlocfilehash: d1480f28a1df94011f32c1597c1d90df3fee466b
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---

# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a>Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10

Платформа .NET Framework 1.1 не поддерживается в операционных системах [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10. В некоторых случаях явно указывается, что для работы приложения требуется именно .NET Framework 1.1. Тогда следует обратиться к независимому поставщику программного обеспечения, чтобы получить обновленную версию приложения на базе [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] или более поздней версии. Дополнительные сведения см. в разделе [Миграция из .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a>Установка .NET Framework 1.1 с компакт-диска или из Центра загрузки

Платформу .NET Framework 1.1 невозможно установить вручную в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10. Оно более не поддерживается. При попытке установить пакет отображается следующее сообщение об ошибке: "Невозможно продолжить установку, поскольку эта версия .NET Framework несовместима с ранее установленной версией". Чтобы решить эту проблему, установите [.NET Framework 3.5 с пакетом обновления 1 (SP1)](http://www.microsoft.com/download/details.aspx?id=22). Эта версия включает платформу .NET Framework 2.0 (выпуск, следующий за выпуском .NET Framework 1.1), поддерживаемую в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] и Windows 10. Рекомендуется сперва пробовать установить приложение — возможно, оно обновится автоматически и будет использовать последнюю версию платформы .NET Framework. Если этого не произойдет, обратитесь к независимому поставщику программного обеспечения за обновленной версией.

## <a name="see-also"></a>См. также

[Миграция с .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Установка платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)
