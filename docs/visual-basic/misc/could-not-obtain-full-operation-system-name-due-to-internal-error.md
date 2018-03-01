---
title: "Не удалось получить полное имя операционной системы из-за внутренней ошибки"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6e90de5a2fd0699a449e05b9c32e7450b8bdc991
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Не удалось получить полное имя операционной системы из-за внутренней ошибки
Не удалось получить полное имя операционной системы из-за внутренней ошибки. Это может быть вызвано отсутствием WMI на текущем компьютере.  
  
 Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` . Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .  
  
2.  Дополнительные сведения об инструментарии WMI и для ее установки перейдите к и поиск «Основы инструментария управления Windows».  
  
## <a name="see-also"></a>См. также  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Исключения и обработка ошибок в Visual Basic](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Оператор Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
