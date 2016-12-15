---
title: "Другие структуры управления (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "управляющие структуры"
  - "операторы [Visual Basic], поток управления"
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Другие структуры управления (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] предоставляет структуры элементов управления, которые используются для удаления ресурсов или уменьшения числа повторений ссылок на объект.  
  
## Конструкция Using...End Using  
 Конструкция `Using...End Using` устанавливает блок операторов, в котором следует использовать ресурсы, например SQL\-соединение.  При необходимости можно запросить ресурс с помощью оператора `Using`.  После выхода из блока `Using`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] автоматически удаляет ресурс, чтобы он был доступен для использования другим кодом.  Ресурс должен быть локальным и допускать удаление.  Дополнительные сведения см. в разделе [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## Конструкция With...End With  
 Конструкция `With...End With` позволяет указать ссылку на объект один раз, и затем запустить последовательность операторов, с помощью которых осуществляется доступ к ее членам.  Это может упростить код и повысить производительность, так как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не восстанавливает ссылку для каждого оператора, который обращается к ней.  Дополнительные сведения см. в разделе [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## См. также  
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)