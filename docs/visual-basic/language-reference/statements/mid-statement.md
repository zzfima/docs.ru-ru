---
title: Оператор Mid
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
ms.openlocfilehash: 90b805df902dcdfebe85421583dd54e9af04bec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602269"
---
# <a name="mid-statement"></a>Оператор Mid
Заменяет указанное число символов в `String` переменной символами из другой строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Части  
 `Target`  
 Обязательно. Имя `String` переменной для изменения.  
  
 `Start`  
 Обязательно. `Integer` Выражение. Позиция знака в `Target` где начинается замена текста. `Start` использует однобазовый индекс.  
  
 `Length`  
 Необязательный. `Integer` Выражение. Число символов для замены. Если не указано, все `String` используется.  
  
 `StringExpression`  
 Обязательно. `String` выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Примечания  
 Число заменяемых знаков, всегда меньше или равно количество символов в `Target`.  
  
 Visual Basic использует <xref:Microsoft.VisualBasic.Strings.Mid%2A> функции и `Mid` инструкции. Эти элементы, они работают на указанное число знаков в строке, но `Mid` функция возвращает символов при `Mid` инструкция заменяет символы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  `MidB` Оператором в более ранних версиях Visual Basic заменяет подстроку в байтах, а не символы. Он используется главным образом для преобразования строк в приложениях с двухбайтовой кодировки (DBCS). Все строки Visual Basic кодируются в Юникоде, и `MidB` больше не поддерживается.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` инструкцию, чтобы заменить указанное число символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Strings`  
  
 **Сборка:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
