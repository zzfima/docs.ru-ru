---
title: Оператор Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 1f0c6b052ead303e0b43465dac2067422abc4ef8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818877"
---
# <a name="implements-statement"></a>Оператор Implements
Указывает один или несколько интерфейсов, или члены интерфейса, которые должны быть реализованы в классе или определение структуры, в котором он находится.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Части  
 `interfacename`  
 Обязательный. Интерфейс, свойства, процедуры и события должны реализовываться соответствующими членами в классе или структуре.  
  
 `interfacemember`  
 Обязательный. Член интерфейса, который реализуется.  
  
## <a name="remarks"></a>Примечания  
 Интерфейс является коллекцией прототипов, представляющих члены (свойства, процедуры и события) инкапсулирует интерфейс. Интерфейсы содержат только объявления членов. классы и структуры реализуют эти члены. Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Implements` Оператора должно следовать сразу `Class` или `Structure` инструкции.  
  
 При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе. Пропуск любого члена считается синтаксическую ошибку. Чтобы реализовать отдельные члены, необходимо указать [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) ключевое слово (отдельными от `Implements` инструкции) при объявлении члена в классе или структуре. Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Классы могут использовать [частного](../../../visual-basic/language-reference/modifiers/private.md) реализации свойства и процедуры, однако эти члены доступны только путем приведения экземпляра реализации класса в переменной, объявленной как типа интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `Implements` инструкцию, чтобы реализовать члены интерфейса. Он определяет интерфейс с именем `ICustomerInfo` события, свойства и процедуры. Класс `customerInfo` реализует все члены, определенные в интерфейсе.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Обратите внимание, что класс `customerInfo` использует `Implements` оператором в отдельной строке исходного кода для указания, что данный класс реализует все члены `ICustomerInfo` интерфейс. Затем каждый член в класс использует `Implements` ключевое слово как часть объявления для указания, что он реализует член этого интерфейса.  
  
## <a name="example"></a>Пример  
 В следующих двух процедурах показано, как использовать интерфейс, реализованный в предыдущем примере. Чтобы протестировать реализацию, добавьте эти процедуры в свой проект и вызовите `testImplements` процедуры.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также

- [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
