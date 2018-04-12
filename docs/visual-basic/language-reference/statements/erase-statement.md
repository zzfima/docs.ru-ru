---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для выпуска переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Части  
 `arraylist`  
 Обязательный. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 `Erase` Оператор может присутствовать только на уровне процедуры. Это означает, что освобождением массивы внутри процедуры, но не на уровне класса или модуля.  
  
 `Erase` Оператор эквивалентен назначение `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Erase` инструкции для удаления двух массивов и высвобождения памяти (1000 и 100 элементов, соответственно). `ReDim` Оператора затем присваивается новый экземпляр массива трехмерного массива.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
