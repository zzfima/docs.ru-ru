---
title: '&lt;Тип 1&gt;&#39;&lt;typename&gt; &#39; необходимо реализовать &#39; &lt;membername&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 0f93bd137bdc21268cbca139ae739843561350ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596750"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Тип 1&gt;&#39;&lt;typename&gt; &#39; необходимо реализовать &#39; &lt;membername&gt; &#39; для интерфейса &#39; &lt;interfacename&gt;&#39;
"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >". Свойство реализации должно иметь соответствующие «ReadOnly» или «WriteOnly» спецификаторы.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите член с тем же именем и сигнатурой, что определенный в интерфейсе. Не забудьте добавить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции. Пример:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.  
  
4.  При реализации свойства объявить `Get` и `Set` соответствующим процедурам.  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
