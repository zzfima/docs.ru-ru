---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840410"
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
