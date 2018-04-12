---
title: '&lt;Тип 1&gt;&#39;&lt; TypeName&gt;&#39; необходимо реализовать &#39;&lt; имя пользователя&gt;&#39; для интерфейса &#39;&lt; Имя интерфейса&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05e0229d0259c519d4db265c017a5040b425c79a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmembernamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;Тип 1&gt;&#39;&lt; TypeName&gt;&#39; необходимо реализовать &#39;&lt; имя пользователя&gt;&#39; для интерфейса &#39;&lt; Имя интерфейса&gt;&#39;
"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >". Свойство реализации должно иметь соответствующие «ReadOnly» или «WriteOnly» спецификаторы.  
  
 Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойство или событие, определенные интерфейсом. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30154  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Объявите член с тем же именем и сигнатурой, что определенный в интерфейсе. Не забудьте добавить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.  
  
2.  Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции. Например:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.  
  
4.  При реализации свойства объявить `Get` и `Set` соответствующим процедурам.  
  
## <a name="see-also"></a>См. также  
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
