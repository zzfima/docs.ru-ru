---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6fc5fb006b36cda1b6ad0e128604bc3bb427fd94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Указывает, что свойство или процедура не может переопределяться в производном классе.  
  
## <a name="remarks"></a>Примечания  
 `NotOverridable` Модификатор не позволяет переопределять свойства или метода в производном классе.  [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) модификатор разрешает свойства или метода в классе для переопределения в производном классе. Дополнительные сведения см. в статье [Inheritance Basics (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) (Основная информация о наследовании в Visual Basic).  
  
 Если `Overridable` или `NotOverridable` модификатор не указан, значение по умолчанию зависит от того, является ли метод или свойство переопределяет свойство базового класса или метода. Если метод или свойство переопределяет свойство базового класса или метода, значение по умолчанию — `Overridable`; в противном случае он является `NotOverridable`.  
  
 Элемент, который не может быть переопределен, иногда называется *запечатанный* элемента.  
  
 `NotOverridable` можно использовать только в операторе объявления свойства или процедуры. Можно указать `NotOverridable` только для свойства или процедуры, которая переопределяет другое свойство или процедура, то есть только в сочетании с `Overrides`.  
  
## <a name="combined-modifiers"></a>Комбинированные модификаторы  
 Нельзя указать `Overridable` или `NotOverridable` для `Private` метод.  
  
 Нельзя указать `NotOverridable` вместе с `MustOverride`, `Overridable`, или `Shared` в одном объявлении.  
  
## <a name="usage"></a>Использование  
 Модификатор `NotOverridable` можно использовать в следующих контекстах:  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Модификаторы](../../../visual-basic/language-reference/modifiers/index.md)  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [Переопределяемые](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [Переопределения](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)  
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
