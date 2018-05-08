---
title: Практическое руководство. Определение установленной версии WPF
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: c59fa0d0a4d94c6e6a2ab72a4cd7a3c066649fb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a>Практическое руководство. Определение установленной версии WPF
Номер версии для текущей установленной версии [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находится в папке **реестра**.  
  
 Чтобы найти номер версии:  
  
1.  В меню **Пуск** выберите пункт **Выполнить**.  
  
2.  В **откройте**, тип **regedit.exe**.  
  
3.  Откройте следующий раздел:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Номер версии хранится в **версии** значение.
