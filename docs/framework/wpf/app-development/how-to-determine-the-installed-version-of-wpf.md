---
title: Практическое руководство. Определение установленной версии WPF
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768024"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="26be0-102">Практическое руководство. Определение установленной версии WPF</span><span class="sxs-lookup"><span data-stu-id="26be0-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="26be0-103">Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в **реестра**.</span><span class="sxs-lookup"><span data-stu-id="26be0-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="26be0-104">Чтобы найти номер версии:</span><span class="sxs-lookup"><span data-stu-id="26be0-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="26be0-105">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="26be0-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="26be0-106">В **откройте**, тип **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="26be0-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="26be0-107">Откройте следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="26be0-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="26be0-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.</span><span class="sxs-lookup"><span data-stu-id="26be0-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
