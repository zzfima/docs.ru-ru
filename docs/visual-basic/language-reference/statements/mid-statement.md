---
title: "Оператор Mid"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 Обязательный. Имя `String` переменной для изменения.  
  
 `Start`  
 Обязательный. `Integer`выражение. Позиция знака в `Target` где начинается замена текста. `Start`использует однобазовый индекс.  
  
 `Length`  
 Необязательно. `Integer`выражение. Число символов для замены. Если не указано, все `String` используется.  
  
 `StringExpression`  
 Обязательный. `String`выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 или `Length` < 0.|  
  
## <a name="remarks"></a>Примечания  
 Число заменяемых знаков, всегда меньше или равно количество символов в `Target`.  
  
 Visual Basic использует <xref:Microsoft.VisualBasic.Strings.Mid%2A> функции и `Mid` инструкции. Эти элементы, они работают на указанное число знаков в строке, но `Mid` функция возвращает символов при `Mid` инструкция заменяет символы. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  `MidB` Оператором в более ранних версиях Visual Basic заменяет подстроку в байтах, а не символы. Он используется главным образом для преобразования строк в приложениях с двухбайтовой кодировки (DBCS). Все строки Visual Basic кодируются в Юникоде, и `MidB` больше не поддерживается.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` инструкцию, чтобы заменить указанное число символов в строковой переменной символами из другой строки.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:**`Strings`  
  
 **Сборка:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
