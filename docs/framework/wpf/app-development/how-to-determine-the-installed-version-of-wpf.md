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
ms.openlocfilehash: 60f2dd65702a5dfcff4cbafa97e5a48080b8e5be
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Практическое руководство. Определение установленной версии WPF
Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в папке **реестра**.  
  
 Чтобы найти номер версии:  
  
1.  В меню **Пуск** выберите пункт **Выполнить**.  
  
2.  В **откройте**, тип **regedit.exe**.  
  
3.  Откройте следующий раздел:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.
