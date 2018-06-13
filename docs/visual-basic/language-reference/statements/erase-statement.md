---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 317e2a7dc5facb08388f3a3e635734e4daed5eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601797"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для выпуска переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Части  
 `arraylist`  
 Обязательно. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 `Erase` Оператор может присутствовать только на уровне процедуры. Это означает, что освобождением массивы внутри процедуры, но не на уровне класса или модуля.  
  
 `Erase` Оператор эквивалентен назначение `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Erase` инструкции для удаления двух массивов и высвобождения памяти (1000 и 100 элементов, соответственно). `ReDim` Оператора затем присваивается новый экземпляр массива трехмерного массива.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
