---
title: Практическое руководство. Определение установленной версии WPF
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: ffbd9a4c7f66dff9c8773dff4259551e20aa963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052460"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="cf3b7-102">Практическое руководство. Определение установленной версии WPF</span><span class="sxs-lookup"><span data-stu-id="cf3b7-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="cf3b7-103">Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в **реестра**.</span><span class="sxs-lookup"><span data-stu-id="cf3b7-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="cf3b7-104">Чтобы найти номер версии:</span><span class="sxs-lookup"><span data-stu-id="cf3b7-104">To find the version number:</span></span>  
  
1. <span data-ttu-id="cf3b7-105">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="cf3b7-105">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="cf3b7-106">В **откройте**, тип **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="cf3b7-106">In **Open**, type **regedit.exe**.</span></span>  
  
3. <span data-ttu-id="cf3b7-107">Откройте следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="cf3b7-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="cf3b7-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.</span><span class="sxs-lookup"><span data-stu-id="cf3b7-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
