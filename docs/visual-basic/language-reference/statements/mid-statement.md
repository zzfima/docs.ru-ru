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
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963547"
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
 Обязательный. `String` Имя переменной, которую необходимо изменить.  
  
 `Start`  
 Обязательный. `Integer`выражение. Место в символах, с `Target` которого начинается замена текста. `Start`использует индекс, отсчитываемый от единицы.  
  
 `Length`  
 Необязательный параметр. `Integer`выражение. Число символов для замены. Если этот параметр опущен, используются `String` все.  
  
 `StringExpression`  
 Обязательный. `String`выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Примечания  
 Число заменяемых символов всегда меньше или равно числу символов в `Target`.  
  
 Visual Basic содержит <xref:Microsoft.VisualBasic.Strings.Mid%2A> функцию `Mid` и оператор. Эти элементы работают с указанным числом символов в строке, но `Mid` функция возвращает символы, `Mid` пока оператор заменяет символы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> `MidB` Инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы. Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS). Все строки Visual Basic в Юникоде и `MidB` больше не поддерживаются.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` оператор для замены указанного числа символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:** `Strings`  
  
 **Сборок** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
