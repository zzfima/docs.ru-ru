---
title: Практическое руководство. Вызов Windows API (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 739516e86917ac24a81cd6387af5576c512ecbc2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515921"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Практическое руководство. Вызов Windows API (Visual Basic)
В этом примере определяется и вызывается `MessageBox` функция в библиотеке user32.dll, а затем передается строка.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Метод не является статическим, является абстрактным или было определено ранее. Родительский тип является интерфейсом, или длина *имя* или *dllName* равно нулю. (<xref:System.ArgumentException>)  
  
-   *Имя* или *dllName* является `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Содержащий тип был создан ранее с помощью `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>См. также  
 [Подробный обзор вызова неуправляемого кода](https://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [Примеры вызовов неуправляемого кода](../../../framework/interop/platform-invoke-examples.md)  
 [Использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [Определение метода с помощью отражения порождаемого](https://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
