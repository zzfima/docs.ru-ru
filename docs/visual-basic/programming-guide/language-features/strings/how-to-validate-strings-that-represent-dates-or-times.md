---
title: Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: c1a3f14354e36dec91aca3afbe8470eff7146318
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970414"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
В следующем примере кода `Boolean` значение, указывающее, представляет ли строка допустимой датой или временем.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` с датой и временем, нужно проверить. Можно заменить строку другой строкой, жестко `String` переменной, или с методом, возвращает строку, например `InputBox`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Используйте этот метод для проверки строки перед попыткой преобразования `String` для `DateTime` переменной. Сначала проверить дату или время, позволяет избежать возникновения исключений во время выполнения.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
