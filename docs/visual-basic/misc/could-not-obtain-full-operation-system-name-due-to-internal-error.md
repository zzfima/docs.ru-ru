---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 192033348a779591a54860505d5d707a802c415a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199054"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Не удалось получить полное имя операционной системы из-за внутренней ошибки
Не удалось получить полное имя операционной системы из-за внутренней ошибки. Это может быть вызвано отсутствием WMI на текущем компьютере.  
  
 Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` . Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .  
  
2.  Дополнительные сведения о WMI и его установке перейдите и искать «Основы инструментария управления Windows».  
  
## <a name="see-also"></a>См. также  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Исключения и обработка ошибок в Visual Basic](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Оператор Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
