---
title: Практическое руководство. Проверка строк, представляющих дату или время
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348404"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
В следующем примере кода задается значение `Boolean`, указывающее, представляет ли строка допустимую дату или время.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Компиляция кода  
 Замените `("01/01/03")` и `"9:30 PM"` на дату и время, которые необходимо проверить. Строку можно заменить другой жестко заданной строкой, переменной `String` или методом, возвращающим строку, например `InputBox`.  
  
## <a name="robust-programming"></a>Надежное программирование  
 Используйте этот метод для проверки строки перед попыткой преобразования `String` в переменную `DateTime`. При проверке даты или времени сначала можно избежать создания исключения во время выполнения.  
  
## <a name="see-also"></a>См. также:

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Проверка строк в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
