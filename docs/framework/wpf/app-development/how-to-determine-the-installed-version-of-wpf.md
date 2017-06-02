---
title: "Практическое руководство. Определение установленной версии WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "version, поиск"
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Практическое руководство. Определение установленной версии WPF
Номер текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в **реестре**.  
  
 Чтобы найти номер версии, выполните следующие действия:  
  
1.  В меню **Пуск** выберите команду **Выполнить**.  
  
2.  В поле **Открыть** введите **regedit.exe**.  
  
3.  Откройте следующий ключ:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 Номер версии [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] хранится в значении параметра **Version**.