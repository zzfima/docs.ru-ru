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
ms.openlocfilehash: ff3b908e2805f4d51463a82d90f2305efc9f1608
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041580"
---
# <a name="mid-statement"></a>Оператор Mid
Заменяет указанное число символов в `String` переменной с символами из другой строки.  
  
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
 Обязательный. Имя `String` переменная, подлежащая изменению.  
  
 `Start`  
 Обязательный. `Integer` выражение. Позиция знака в `Target` которой начинается замена текста. `Start` использует однобазовый индекс.  
  
 `Length`  
 Необязательный параметр. `Integer` выражение. Число символов для замены. Если не указано, все `String` используется.  
  
 `StringExpression`  
 Обязательный. `String` выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Примечания  
 Число заменяемых знаков всегда будет меньше или равно числу символов в `Target`.  
  
 Visual Basic имеет <xref:Microsoft.VisualBasic.Strings.Mid%2A> функции и `Mid` инструкции. Эти элементы, которые работают на указанное число знаков в строке, но `Mid` функция возвращает символов при `Mid` инструкция заменяет символы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  `MidB` Инструкция из более ранних версиях Visual Basic заменяет подстроки в байтах, а не символы. Он используется главным образом для преобразования строк в приложениях двухбайтовой кодировки (DBCS). Все строки Visual Basic, в формате Юникод, и `MidB` больше не поддерживается.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` инструкцию, чтобы заменить указанное число символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Strings`  
  
 **Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
