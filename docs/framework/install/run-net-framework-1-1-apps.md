---
title: "Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10"
ms.custom: 
ms.date: 05/26/2017
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
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: c7b53a842dc4f9b6bfc04e058411e4a6d11a7bd1
ms.contentlocale: ru-ru
ms.lasthandoff: 08/05/2017

---

# <a name="run-net-framework-11-apps-on-windows-8-windows-81-or-windows-10"></a><span data-ttu-id="c611f-102">Выполнение приложений .NET Framework 1.1 в Windows 8, Windows 8.1 или Windows 10</span><span class="sxs-lookup"><span data-stu-id="c611f-102">Run .NET Framework 1.1 apps on Windows 8, Windows 8.1, or Windows 10</span></span>

<span data-ttu-id="c611f-103">Платформа .NET Framework 1.1 не поддерживается в операционных системах [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c611f-103">The .NET Framework 1.1 is not supported on the [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or the Windows 10 operating systems.</span></span> <span data-ttu-id="c611f-104">В некоторых случаях явно указывается, что для работы приложения требуется именно .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="c611f-104">In some cases, the .NET Framework 1.1 is specifically identified as required for an app to run.</span></span> <span data-ttu-id="c611f-105">В этих случаях следует обратиться к независимому поставщику программного обеспечения, чтобы получить обновленную версию приложения для запуска с использованием [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] или более поздней версии платформы.</span><span class="sxs-lookup"><span data-stu-id="c611f-105">In those cases, you should contact your independent software vendor (ISV) to have the app upgraded to run on the [!INCLUDE[net_v35SP1_short](../../../includes/net-v35sp1-short-md.md)] or later version.</span></span> <span data-ttu-id="c611f-106">Дополнительные сведения см. в разделе [Миграция из .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="c611f-106">For additional information, see [Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>

## <a name="install-the-net-framework-11-from-a-cd-or-download-center"></a><span data-ttu-id="c611f-107">Установка .NET Framework 1.1 с компакт-диска или из Центра загрузки</span><span class="sxs-lookup"><span data-stu-id="c611f-107">Install the .NET Framework 1.1 from a CD or Download Center</span></span>

<span data-ttu-id="c611f-108">Платформу .NET Framework 1.1 невозможно установить вручную в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)] и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c611f-108">It isn't possible to manually install the .NET Framework 1.1 on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], [!INCLUDE[winserver8](../../../includes/winserver8-md.md)], [!INCLUDE[winblue_server_2](../../../includes/winblue-server-2-md.md)], or Windows 10.</span></span> <span data-ttu-id="c611f-109">Оно более не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c611f-109">It is no longer supported.</span></span> <span data-ttu-id="c611f-110">При попытке установить пакет отображается следующее сообщение об ошибке: "Невозможно продолжить установку, поскольку эта версия .NET Framework несовместима с ранее установленной версией".</span><span class="sxs-lookup"><span data-stu-id="c611f-110">If you try to install the package, the following error message is displayed: "Setup cannot continue because this version of the .NET Framework is incompatible with a previously installed one."</span></span> <span data-ttu-id="c611f-111">Чтобы решить эту проблему, установите [.NET Framework 3.5 с пакетом обновления 1 (SP1)](http://www.microsoft.com/download/details.aspx?id=22).</span><span class="sxs-lookup"><span data-stu-id="c611f-111">To solve this problem, install the [.NET Framework 3.5 SP1](http://www.microsoft.com/download/details.aspx?id=22).</span></span> <span data-ttu-id="c611f-112">Эта версия включает платформу .NET Framework 2.0 (выпуск, следующий за выпуском .NET Framework 1.1), поддерживаемую в [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c611f-112">This version includes the .NET Framework 2.0 (the release that follows the .NET Framework 1.1), which is supported on [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)], and Windows 10.</span></span> <span data-ttu-id="c611f-113">Сначала попробуйте установить приложение, чтобы проверить, будет ли оно автоматически обновлено до более поздней версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c611f-113">You should always try to install the app first to determine if it will automatically be updated to a later version of the .NET Framework.</span></span> <span data-ttu-id="c611f-114">Если этого не произойдет, обратитесь к независимому поставщику программного обеспечения за обновленной версией.</span><span class="sxs-lookup"><span data-stu-id="c611f-114">If it does not, contact your ISV for an app update.</span></span>

## <a name="see-also"></a><span data-ttu-id="c611f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c611f-115">See also</span></span>

<span data-ttu-id="c611f-116">[Миграция с .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Установка платформы .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span><span class="sxs-lookup"><span data-stu-id="c611f-116">[Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)
[Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)</span></span>

