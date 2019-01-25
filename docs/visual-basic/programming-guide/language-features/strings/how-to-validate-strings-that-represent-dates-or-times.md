---
title: Как выполнить Проверка строк, представляющих дату или время (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685403"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Как выполнить Проверка строк, представляющих дату или время (Visual Basic)
В следующем примере кода `Boolean` значение, указывающее, представляет ли строка допустимой датой или временем.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` с датой и временем, нужно проверить. Можно заменить строку другой строкой, жестко `String` переменной, или с методом, возвращает строку, например `InputBox`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Используйте этот метод для проверки строки перед попыткой преобразования `String` для `DateTime` переменной. Сначала проверить дату или время, позволяет избежать возникновения исключений во время выполнения.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
