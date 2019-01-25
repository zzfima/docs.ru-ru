---
title: '&lt;тип1&gt;&#39;&lt;typename&gt; &#39; должен реализовывать &#39; &lt;membername&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 14e7bd199215764676a4b563eafc68bd6dabadc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574746"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;тип1&gt;&#39;&lt;typename&gt; &#39; должен реализовывать &#39; &lt;membername&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;
"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >". Реализация свойства должен иметь совпадающие «ReadOnly» или «WriteOnly» спецификаторы.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойства или события, определенные в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите член с тем же именем и подписью, как определено в интерфейсе. Не забудьте включить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции. Пример:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.  
  
4.  При реализации свойства объявить `Get` и `Set` процедуры, соответствующим образом.  
  
## <a name="see-also"></a>См. также
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
