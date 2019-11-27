---
title: Оператор TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 22af5b8f8488ca44e388596530decd52e33525dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350890"
---
# <a name="typeof-operator-visual-basic"></a>Оператор TypeOf (Visual Basic)
Проверяет, совместим ли тип среды выполнения результата выражения с указанным типом.
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Части  
 `result`  
 Возвращено. Значение `Boolean`.  
  
 `objectexpression`  
 Обязательно. Любое выражение, результатом которого является тип ссылки.  
  
 `typename`  
 Обязательно. Любое имя типа данных.  
  
## <a name="remarks"></a>Примечания  
 Оператор `TypeOf` определяет, совместим ли тип времени выполнения `objectexpression` с `typename`. Совместимость зависит от категории типа `typename`. В следующей таблице показано, как определяется совместимость.  
  
|Категория типа `typename`|Критерий совместимости|  
|---------------------------------|-----------------------------|  
|Class|`objectexpression` имеет тип `typename` или наследуется от `typename`|  
|Структура|`objectexpression` имеет тип `typename`|  
|Интерфейс|`objectexpression` реализует `typename` или наследует от класса, реализующего `typename`|  
  
 Если тип времени выполнения `objectexpression` удовлетворяет критерию совместимости, `result` является `True`. В противном случае `result` является `False`.  Если `objectexpression` имеет значение null, то `TypeOf`...`Is` возвращает `False`, а ...`IsNot` возвращает `True`.  
  
 `TypeOf` всегда используется вместе с ключевым словом `Is` для создания выражения `TypeOf`...`Is` или с ключевым словом `IsNot` для создания выражения `TypeOf`...`IsNot`.  
  
## <a name="example"></a>Пример  
 В следующем примере выражение `TypeOf`...`Is` используется для проверки на совместимость типов двух переменных ссылок на объекты с различными типами данных.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 Переменная `refInteger` имеет тип времени выполнения `Integer`. Она совместима с `Integer`, но не с `Double`. Переменная `refForm` имеет тип времени выполнения <xref:System.Windows.Forms.Form>. Она совместима с <xref:System.Windows.Forms.Form>, так как это ее тип, с <xref:System.Windows.Forms.Control>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.Windows.Forms.Control>, и с <xref:System.ComponentModel.IComponent>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.ComponentModel.Component>, который реализует <xref:System.ComponentModel.IComponent>. Однако `refForm` несовместима с <xref:System.Windows.Forms.Label>.  
  
## <a name="see-also"></a>См. также

- [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
