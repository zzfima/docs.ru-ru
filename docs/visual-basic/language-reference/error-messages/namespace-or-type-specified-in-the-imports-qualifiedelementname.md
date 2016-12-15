---
title: "Пространство имен или тип, указанный в Imports &lt;уточненноеИмяЭлемента&gt;, не содержит общих членов или не найден | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40056"
  - "vbc40056"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40056"
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пространство имен или тип, указанный в Imports &lt;уточненноеИмяЭлемента&gt;, не содержит общих членов или не найден
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Пространство имен или тип, указанный в Imports '\<qualifiedelementname\>', не содержит общих элементов или не найден.Убедитесь, что пространство имен или тип определен и содержит хотя бы один открытый элемент.Убедитесь, что имя псевдонима не содержит других псевдонимов.  
  
 Оператор `Imports` задает содержащий элемент, который либо не может быть найден, либо не определяет какие\-либо элементы `Public`.  
  
 *Содержащий элемент* может быть пространством имен, классом, структурой, модулем, интерфейсом или перечислением.  Содержащий элемент содержит такие элементы, как переменные, процедуры или другие содержащие элементы.  
  
 Импорт нужен для того, чтобы разрешить коду доступ к пространству имен или элементам типа без их уточнения.  В проекте может также потребоваться добавить ссылку на пространство имен или тип.  Дополнительные сведения содержатся в разделе "Импорт содержащих элементов" в [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Если компилятор не может найти указанный содержащий элемент, то он не может разрешить ссылки, которые используют его.  Если он находит элемент, но элемент не предоставляет никаких `Public`\-элементов, то ни одна ссылка не может быть рабочей.  В любом случае нет смысла в импорте элемента.  
  
 Имейте в виду, что, если импортировать содержащий элемент и присвоить ему псевдоним импорта, нельзя будет использовать этот псевдоним импорта для импорта другого элемента.  Следующий код создает ошибку компилятора.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Идентификатор ошибки:**: BC40056  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что содержащий элемент является доступным из проекта.  
  
2.  Убедитесь, что спецификация содержащего элемента не включает какие\-либо псевдонимы импорта из другого импорта.  
  
3.  Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` элемент.  
  
## См. также  
 [Оператор Imports \(пространство имен .NET и тип\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)