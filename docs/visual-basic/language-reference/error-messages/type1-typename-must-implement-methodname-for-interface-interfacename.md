---
title: '&lt;Тип 1&gt;&#39;&lt;typename&gt; &#39; необходимо реализовать &#39; &lt;имя_метода&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: daeeab853f6a7f582542fa15ffc09ce749731d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Тип 1&gt;&#39;&lt;typename&gt; &#39; необходимо реализовать &#39; &lt;имя_метода&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;
Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, определенную в интерфейсе. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30149  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите процедуру с тем же именем и сигнатурой, что определенный в интерфейсе. Не забудьте добавить по крайней мере `End Function` или `End Sub` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function` или `Sub` инструкции. Пример:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
