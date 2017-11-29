---
title: "Аргументы типа не могут быть выведены от делегата"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords: BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 57a3a24af32d9eb85a0f905aa3a73a956723b6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>Аргументы типа не могут быть выведены от делегата
Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.  
  
 Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом. Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов. Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.  
  
 **Идентификатор ошибки:** BC36564  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .  
  
## <a name="see-also"></a>См. также  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Универсальные процедуры в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)  
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
