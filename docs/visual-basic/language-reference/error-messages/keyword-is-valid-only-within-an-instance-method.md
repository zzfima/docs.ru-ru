---
title: "&#39; &lt;ключевое слово&gt;&#39; является допустимым только в методе экземпляра"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords: BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39; &lt;ключевое слово&gt;&#39; является допустимым только в методе экземпляра
`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на конкретные экземпляры класса. Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.  
  
 **Идентификатор ошибки:** BC30043  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.  
  
## <a name="see-also"></a>См. также  
 [Присваивание объектных переменных](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
