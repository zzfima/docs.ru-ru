---
title: "Практическое руководство. Определение установленной версии WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf58e8e8ade7382d8a897a3ec59bef0c810a48bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="c75f5-102">Практическое руководство. Определение установленной версии WPF</span><span class="sxs-lookup"><span data-stu-id="c75f5-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="c75f5-103">Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в папке **реестра**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="c75f5-104">Чтобы найти номер версии:</span><span class="sxs-lookup"><span data-stu-id="c75f5-104">To find the version number:</span></span>  
  
1.  <span data-ttu-id="c75f5-105">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="c75f5-106">В **откройте**, тип **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="c75f5-106">In **Open**, type **regedit.exe**.</span></span>  
  
3.  <span data-ttu-id="c75f5-107">Откройте следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="c75f5-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="c75f5-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.</span><span class="sxs-lookup"><span data-stu-id="c75f5-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
