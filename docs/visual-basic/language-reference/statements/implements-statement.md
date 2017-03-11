---
title: "Оператор Implements | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Implements"
  - "Implements"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements - оператор"
  - "Implements - оператор, синтаксис"
  - "реализация интерфейсов, Implements - оператор"
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор Implements
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает один или несколько интерфейсов или членов интерфейса, реализуемых в определении класса или структуры, в которых появляется этот оператор.  
  
## Синтаксис  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## Части  
 `interfacename`  
 Обязательный.  Интерфейс, свойства, методы и события которого должны реализовываться соответствующими членами в классе или структуре.  
  
 `interfacemember`  
 Обязательный.  Реализуемый член интерфейса.  
  
## Заметки  
 Интерфейс — это коллекция прототипов, которые представляют собой инкапсулированные интерфейсом члены \(свойства, методы и события\).  Интерфейсы содержат только объявления членов. Классы и структуры реализуют эти члены.  Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Оператор `Implements` должен следовать непосредственно за операторами `Class` или `Structure`.  
  
 Для реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе.  Пропуск какого\-либо члена считается синтаксической ошибкой.  Для реализации отдельного члена необходимо указать ключевое слово [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)\(которое отличается от оператора `Implements`\) при объявлении члена в классе или структуре.  Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Классы могут использовать реализации свойств и методов с уровнем доступа [Private](../../../visual-basic/language-reference/modifiers/private.md), однако эти члены доступны только путем приведения экземпляра реализующего класса к переменной типа интерфейса.  
  
## Пример  
 В следующем примере показано использование оператора `Implements` для реализации членов интерфейса.  Этот оператор определяет интерфейс `ICustomerInfo` с событием, свойством и процедурой.  Класс `customerInfo` реализует все члены, определенные в интерфейсе.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/implements-statement_1.vb)]  
  
 Обратите внимание, что класс `customerInfo` использует оператор `Implements` в отдельной строке исходного кода, чтобы указать, что класс реализует все члены интерфейса `ICustomerInfo`.  Затем, чтобы указать, что он реализует член интерфейса, каждый член класса использует ключевое слово `Implements` как часть объявления этого члена.  
  
## Пример  
 Следующие две процедуры показывают, как можно использовать интерфейс, реализованный в предыдущем примере.  Для поверки реализации интерфейса добавьте эти процедуры в проект и вызовите процедуру `testImplements`.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/implements-statement_2.vb)]  
  
## См. также  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)