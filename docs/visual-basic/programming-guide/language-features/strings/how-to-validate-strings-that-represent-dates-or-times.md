---
title: Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
В следующем примере кода `Boolean` значение, указывающее, представляет ли строка допустимую дату или время.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` с указанием даты и времени, который требуется проверить. Можно заменить строки с другой строкой жестко `String` переменной, или с помощью метода, возвращающего строку, например `InputBox`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Используйте этот метод для проверки строки перед попыткой преобразования `String` для `DateTime` переменной. Проверив дату или время сначала, можно избежать возникновения исключений во время выполнения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
