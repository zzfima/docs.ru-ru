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
ms.openlocfilehash: 865e99aa0e27591d10fde1465047a2e6bf183bbf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581792"
---
# <a name="implements-statement"></a>Оператор Implements
Указывает один или несколько интерфейсов или элементов интерфейса, которые должны быть реализованы в определении класса или структуры, в котором они отображаются.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Части  
 `interfacename`  
 Обязательный. Интерфейс, свойства, процедуры и события которого должны быть реализованы соответствующими элементами в классе или структуре.  
  
 `interfacemember`  
 Обязательный. Член реализуемого интерфейса.  
  
## <a name="remarks"></a>Заметки  
 Интерфейс — это коллекция прототипов, представляющих члены (свойства, процедуры и события), которые инкапсулирует интерфейс. Интерфейсы содержат только объявления для членов; классы и структуры реализуют эти члены. Дополнительные сведения см. в статье [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Оператор `Implements` должен следовать непосредственно за инструкцией `Class` или `Structure`.  
  
 При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе. Пропуск любого члена считается синтаксической ошибкой. Для реализации отдельного элемента необходимо указать ключевое слово [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) (отдельно от оператора `Implements`) при объявлении члена в классе или структуре. Дополнительные сведения см. в статье [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Классы могут использовать [закрытые](../../../visual-basic/language-reference/modifiers/private.md) реализации свойств и процедур, но эти члены доступны только путем приведения экземпляра реализующего класса к переменной, объявленной как тип интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать оператор `Implements` для реализации членов интерфейса. Он определяет интерфейс с именем `ICustomerInfo` с событием, свойством и процедурой. Класс `customerInfo` реализует все члены, определенные в интерфейсе.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Обратите внимание, что класс `customerInfo` использует инструкцию `Implements` в отдельной строке исходного кода, чтобы указать, что класс реализует все члены интерфейса `ICustomerInfo`. Затем каждый член класса использует ключевое слово `Implements` как часть его объявления члена, чтобы указать, что он реализует этот член интерфейса.  
  
## <a name="example"></a>Пример  
 В следующих двух процедурах показано, как можно использовать интерфейс, реализованный в предыдущем примере. Чтобы протестировать реализацию, добавьте эти процедуры в проект и вызовите процедуру `testImplements`.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также

- [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
