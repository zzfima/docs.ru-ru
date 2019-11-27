---
title: Оператор Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343701"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для высвобождения переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Части  
 `arraylist`  
 Обязательное. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Примечания  
 Оператор `Erase` может использоваться только на уровне процедуры. Это означает, что массивы можно освобождать внутри процедуры, но не на уровне класса или модуля.  
  
 Оператор `Erase` эквивалентен назначению `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере используется оператор `Erase` для очистки двух массивов и освобождения памяти (1000 и 100, соответственно). Затем оператор `ReDim` присваивает новый экземпляр массива трехмерному массиву.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также:

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
