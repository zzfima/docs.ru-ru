---
title: "Не удалось получить полное имя операционной системы из-за внутренней ошибки"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65796c41d2a9fbd03517e7b15bc6b566ba4364fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Не удалось получить полное имя операционной системы из-за внутренней ошибки
Не удалось получить полное имя операционной системы из-за внутренней ошибки. Это может быть вызвано отсутствием WMI на текущем компьютере.  
  
 Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` . Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .  
  
2.  Дополнительные сведения об инструментарии WMI и для ее установки перейдите к и поиск «Основы инструментария управления Windows».  
  
## <a name="see-also"></a>См. также  
 [Свойство My.Computer.Info.OSFullName](http://msdn.microsoft.com/en-us/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)  
 [Исключения и обработка ошибок в Visual Basic](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Оператор Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
