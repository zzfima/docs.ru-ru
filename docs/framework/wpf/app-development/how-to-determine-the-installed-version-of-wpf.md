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
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Практическое руководство. Определение установленной версии WPF
Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в папке **реестра**.  
  
 Чтобы найти номер версии:  
  
1.  В меню **Пуск** выберите пункт **Выполнить**.  
  
2.  В **откройте**, тип **regedit.exe**.  
  
3.  Откройте следующий раздел:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.
