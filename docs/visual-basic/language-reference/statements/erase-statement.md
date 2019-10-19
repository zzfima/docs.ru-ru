---
title: Оператор Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583390"
---
# <a name="erase-statement-visual-basic"></a>Оператор Erase (Visual Basic)
Используется для высвобождения переменных массива и освобождения памяти, используемой для их элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Части  
 `arraylist`  
 Обязательный. Список переменных массива для удаления. Переменные разделяются запятыми.  
  
## <a name="remarks"></a>Заметки  
 Оператор `Erase` может использоваться только на уровне процедуры. Это означает, что массивы можно освобождать внутри процедуры, но не на уровне класса или модуля.  
  
 Оператор `Erase` эквивалентен назначению `Nothing` каждой переменной массива.  
  
## <a name="example"></a>Пример  
 В следующем примере используется оператор `Erase` для очистки двух массивов и освобождения памяти (1000 и 100, соответственно). Затем оператор `ReDim` присваивает новый экземпляр массива трехмерному массиву.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>См. также

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)
