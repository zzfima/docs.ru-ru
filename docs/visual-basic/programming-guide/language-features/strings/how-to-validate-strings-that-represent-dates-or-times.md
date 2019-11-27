---
title: Практическое руководство. Проверка строк, представляющих дату или время
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 34af6dffeb0d05eaeed38354f8007554b60e91b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344345"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
В следующем примере кода задается значение `Boolean`, указывающее, представляет ли строка допустимую дату или время.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` на дату и время, которые необходимо проверить. Строку можно заменить другой жестко заданной строкой, переменной `String` или методом, возвращающим строку, например `InputBox`.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Используйте этот метод для проверки строки перед попыткой преобразования `String` в переменную `DateTime`. При проверке даты или времени сначала можно избежать создания исключения во время выполнения.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
