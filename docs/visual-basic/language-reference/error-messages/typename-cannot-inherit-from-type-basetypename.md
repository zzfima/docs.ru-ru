---
title: '&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; поскольку он расширяет доступ базового &lt;тип&gt; за пределы данной сборки'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556487"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; поскольку он расширяет доступ базового &lt;тип&gt; за пределы данной сборки
Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.  
  
 Например `Public` интерфейс наследует от `Friend` интерфейс, или `Protected` класс наследует от `Private` класса. Этот класс представляет базовый класс или интерфейс для доступа к выше установленного уровня.  
  
 **Идентификатор ошибки:** BC30910  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените уровень доступа производный класс или интерфейс был менее строгий, как и для базового класса или интерфейса.  
  
     - или -  
  
-   Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции. Не может наследовать от более ограниченных базового класса или интерфейса.  
  
## <a name="see-also"></a>См. также
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
