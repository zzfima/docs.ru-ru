---
title: '&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; которого отличается от него только массивом типов параметров массива или рангом типов параметра массива'
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0f4eaa09c3d04af350637fba0d672f55040a6466
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626853"
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; не является CLS-совместимым, поскольку он перегружает &lt;proceduresignature2&gt; которого отличается от него только массивом типов параметров массива или рангом типов параметра массива
Процедура или свойство помечается как `<CLSCompliant(True)>` когда оно переопределяет другую процедуру или свойство, и единственное различие между их списки параметров — уровень вложенности массива массивов или ранг массива.  
  
 В следующих объявлениях второе и третье объявления вызвать эту ошибку.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Второе объявление изменяет исходный одномерный параметр `arrayParam` для массива массивов. Третье объявление превращает `arrayParam` двухмерный массив (ранг 2). Visual Basic позволяет перегрузки, отличающиеся только по одному из этих изменений, такая перегрузка не соответствует стандарту [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40035  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если требуется совместимость с CLS, определите перегрузки отличаются друг от друга в больше способов представлено на этой странице справки.  
  
-   Если требуется, чтобы перегрузки отличались только по признакам, описанным в этой справке странице, удалите <xref:System.CLSCompliantAttribute> из их определения или пометьте их как `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>См. также

- [Перегрузка процедур](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Перегрузки](../../../visual-basic/language-reference/modifiers/overloads.md)
