---
title: Практическое руководство. Вызов API Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: e7b76495b83cb9a1dfe7629a1d82695d2046eac2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61818720"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Практическое руководство. Вызов API Windows (Visual Basic)
В этом примере определяется и вызывается `MessageBox` функция в библиотеке user32.dll, а затем передается строка.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- Метод не является статическим, является абстрактным или было определено ранее. Родительский тип является интерфейсом, или длина *имя* или *dllName* равно нулю. (<xref:System.ArgumentException>)  
  
- *Имя* или *dllName* является `Nothing`. (<xref:System.ArgumentNullException>)  
  
- Содержащий тип был создан ранее с помощью `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>См. также

- [Подробный обзор вызова неуправляемого кода](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Примеры вызовов неуправляемого кода](../../../framework/interop/platform-invoke-examples.md)
- [Использование неуправляемых функций DLL](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Определение метода с помощью отражения порождаемого](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Пошаговое руководство: Вызов API Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [COM-взаимодействие](../../../visual-basic/programming-guide/com-interop/index.md)
