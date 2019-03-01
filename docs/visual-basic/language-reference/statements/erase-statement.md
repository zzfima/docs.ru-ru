---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 5828e28b84ec62c7ed674757090806d73c61caea
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966740"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для удаления переменных массива и освободить память, используемая для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Части  
 `arraylist`  
 Обязательный. Список переменных массива. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 `Erase` Оператор может присутствовать только на уровне процедуры. Это означает, что вы можете выпустить массивы внутри процедуры, но не на уровне класса или модуля.  
  
 `Erase` Инструкция эквивалентна присваиванию `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Erase` инструкцию, чтобы очистить два массива и освободить память (1000 и 100 элементов, соответственно). `ReDim` Оператора затем присваивается новый экземпляр массива трехмерный массив.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
