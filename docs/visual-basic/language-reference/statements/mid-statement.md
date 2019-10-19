---
title: Оператор Mid (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581474"
---
# <a name="mid-statement"></a>Оператор Mid
Заменяет указанное число символов в переменной `String` символами из другой строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Части  
 `Target`  
 Обязательный. Имя изменяемой переменной `String`.  
  
 `Start`  
 Обязательный. выражение `Integer`. Позицию символа в `Target`, где начинается замена текста. `Start` использует индекс, отсчитываемый от единицы.  
  
 `Length`  
 Необязательный. выражение `Integer`. Число символов для замены. Если этот параметр опущен, используется все `String`.  
  
 `StringExpression`  
 Обязательный. `String` выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Заметки  
 Число заменяемых символов всегда меньше или равно числу символов в `Target`.  
  
 Visual Basic содержит функцию <xref:Microsoft.VisualBasic.Strings.Mid%2A> и инструкцию `Mid`. Эти элементы работают с указанным числом символов в строке, но функция `Mid` возвращает символы, пока оператор `Mid` заменяет символы. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> @No__t_0ная инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы. Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS). Все строки Visual Basic в Юникоде, а `MidB` больше не поддерживаются.  
  
## <a name="example"></a>Пример  
 В этом примере используется оператор `Mid` для замены указанного числа символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Strings`  
  
 **Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
