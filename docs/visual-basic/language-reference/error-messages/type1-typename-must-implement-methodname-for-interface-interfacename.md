---
title: '&lt;тип1&gt;&#39;&lt;typename&gt; &#39; должен реализовывать &#39; &lt;имя_метода&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642451"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;тип1&gt;&#39;&lt;typename&gt; &#39; должен реализовывать &#39; &lt;имя_метода&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;
Класс или структура объявляет о реализации интерфейса, но не реализует процедуры, определенные в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30149  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите процедуру с тем же именем и подписью, как определено в интерфейсе. Не забудьте включить по крайней мере `End Function` или `End Sub` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function` или `Sub` инструкции. Пример:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>См. также
- [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
