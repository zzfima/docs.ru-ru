---
title: '&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; , поскольку он расширяет доступ базового &lt;тип&gt; за пределами сборки'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: f747b2b24f5fecc22b9e1fbc6ba26b634e9ead2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; , поскольку он расширяет доступ базового &lt;тип&gt; за пределами сборки
Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.  
  
 Например `Public` интерфейс наследует от `Friend` интерфейса, или `Protected` класс наследует от `Private` класса. Это предоставляет базовый класс или интерфейс для доступа к выше установленного уровня.  
  
 **Идентификатор ошибки:** BC30910  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените уровень доступа производный класс или интерфейс был менее строгий, чем базового класса или интерфейса.  
  
     - или -  
  
-   Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции. Не может наследовать от более ограниченный базового класса или интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
