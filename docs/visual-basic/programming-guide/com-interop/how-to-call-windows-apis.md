---
title: "Практическое руководство. Вызов Windows API (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Практическое руководство. Вызов Windows API (Visual Basic)
В этом примере определяется и вызывается `MessageBox` функции в библиотеке user32.dll и передает строку.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Метод не является статическим, является абстрактным или было определено ранее. Родительский тип является интерфейсом или длина *имя* или *dllName* равно нулю. (<xref:System.ArgumentException>)  
  
-   *Имя* или *dllName* — `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Содержащий тип был создан ранее с помощью `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>См. также  
 [Подробный обзор вызова неуправляемого кода](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [Примеры вызовов неуправляемого кода](../../../framework/interop/platform-invoke-examples.md)  
 [Использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [Определение метода с отражением выпуска](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
