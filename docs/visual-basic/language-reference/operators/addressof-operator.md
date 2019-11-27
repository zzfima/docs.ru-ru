---
title: Оператор AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: e88520bd7e731a35b98c1d40c5210dc5d1314911
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350279"
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата, который ссылается на определенную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательно. Задает процедуру, на которую ссылается только что созданный делегат.  
  
## <a name="remarks"></a>Заметки  
 Оператор `AddressOf` создает делегат, указывающий на подпрограмму или функцию, указанную в `procedurename`. Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод. Затем при вызове делегата вызывается указанный метод указанного экземпляра.  
  
 Оператор `AddressOf` можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.  
  
## <a name="example"></a>Пример  
 В этом примере оператор `AddressOf` используется для обозначения делегата, обрабатывающего событие `Click` кнопки.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `AddressOf` используется для обозначения функции запуска для потока.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
