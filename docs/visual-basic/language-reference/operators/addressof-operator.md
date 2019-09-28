---
title: Оператор AddressOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2ebadf5ded1a23fe46b8e16cf18ae265b5d3c255
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591656"
---
# <a name="addressof-operator-visual-basic"></a>Оператор AddressOf (Visual Basic)
Создает экземпляр делегата, который ссылается на определенную процедуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Части  
 `procedurename`  
 Обязательный. Задает процедуру, на которую ссылается только что созданный делегат.  
  
## <a name="remarks"></a>Примечания  
 Оператор `AddressOf` создает делегат, указывающий на подпрограмму или функцию, заданную параметром `procedurename`. Если указанная процедура является методом экземпляра, то делегат ссылается на экземпляр и метод. Затем при вызове делегата вызывается указанный метод указанного экземпляра.  
  
 Оператор `AddressOf` можно использовать в качестве операнда конструктора делегата или его можно использовать в контексте, в котором тип делегата может быть определен компилятором.  
  
## <a name="example"></a>Пример  
 В этом примере оператор `AddressOf` используется для обозначения делегата, обрабатывающего событие кнопки `Click`.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `AddressOf` используется для обозначения функции запуска для потока.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>См. также

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
