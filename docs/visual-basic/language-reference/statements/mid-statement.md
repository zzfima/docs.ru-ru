---
title: "Оператор Mid | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e385d6838daa16d45903c6b270fc47ad88797845
ms.lasthandoff: 03/13/2017

---
# <a name="mid-statement"></a>Оператор Mid
Заменяет указанное число знаков в `String` переменной на знаки из другой строки.  
  
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
 Обязательный. `Integer`выражение. Позиция знака в `Target` начинается замена текста. `Start`использует индекс от единицы.  
  
 `Length`  
 Необязательный. `Integer`выражение. Число знаков для замены. Если не указано, все `String` используется.  
  
 `StringExpression`  
 Обязательный. `String`выражение, которое заменяет часть `Target`.  
  
## <a name="exceptions"></a>Исключения  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException></xref:System.ArgumentException>|`Start`<= 0="" or=""></=>`Length`< 0.></ 0.>|  
  
## <a name="remarks"></a>Примечания  
 Число заменяемых знаков всегда будет меньше или равно числу символов в `Target`.  
  
 Visual Basic имеет <xref:Microsoft.VisualBasic.Strings.Mid%2A>функции и `Mid` инструкции.</xref:Microsoft.VisualBasic.Strings.Mid%2A> Эти элементы, как работают на указанное число знаков в строке, но `Mid` функция возвращает символы при `Mid` инструкция заменяет символы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A>  
  
> [!NOTE]
>  `MidB` Инструкции более ранних версиях Visual Basic заменяет подстроку в байтах, а не символы. Он используется главным образом для преобразования строк в приложениях с двухбайтовой кодировки (DBCS). Все строки Visual Basic кодируются в Юникоде, и `MidB` больше не поддерживается.  
  
## <a name="example"></a>Пример  
 В этом примере используется `Mid` инструкции для замены указанное число символов в строковой переменной на знаки из другой строки.  
  
 [!code-vb[VbVbalrStrings&#5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Модуль:**`Strings`  
  
 **Сборка:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
