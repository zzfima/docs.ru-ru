---
title: Оператор Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604215"
---
# <a name="implements-statement"></a>Оператор Implements
Указывает один или несколько интерфейсов, или членов интерфейса, которые должны быть реализованы в классе или определение структуры, в котором он отображается.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Части  
 `interfacename`  
 Обязательно. Интерфейс, свойства, процедуры и события, должны быть реализованы соответствующие элементы в классе или структуре.  
  
 `interfacemember`  
 Обязательно. Член интерфейса, который реализуется.  
  
## <a name="remarks"></a>Примечания  
 Интерфейс — это коллекция прототипов, представляющих члены (свойства, процедуры и события) инкапсулирует интерфейс. Интерфейсы содержат только объявления членов. классы и структуры реализуют эти члены. Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Implements` Инструкции следует непосредственно за `Class` или `Structure` инструкции.  
  
 При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе. Пропуск любого элемента считается синтаксическую ошибку. Чтобы реализовать отдельные члены, необходимо указать [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) ключевое слово (отделен от `Implements` инструкции) при объявлении члена в классе или структуре. Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Классы могут использовать [закрытый](../../../visual-basic/language-reference/modifiers/private.md) реализации свойства и процедуры, однако эти члены доступны только путем приведения экземпляра реализующего класса в переменной, объявленной как типа интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `Implements` инструкции для реализации членов интерфейса. Он определяет интерфейс с именем `ICustomerInfo` с событием, свойства и процедуры. Класс `customerInfo` реализует все члены, определенные в интерфейсе.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Обратите внимание, что класс `customerInfo` использует `Implements` инструкции на отдельной строке исходного кода, чтобы указать, что класс реализует все члены `ICustomerInfo` интерфейса. Затем каждый член класса использует `Implements` ключевое слово как часть объявления, чтобы указать, что он реализует член этого интерфейса.  
  
## <a name="example"></a>Пример  
 В следующих двух процедурах показано, как можно использовать интерфейс, реализованный в предыдущем примере. Чтобы проверить реализацию, добавьте эти процедуры в проекте и вызовите `testImplements` процедуры.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
