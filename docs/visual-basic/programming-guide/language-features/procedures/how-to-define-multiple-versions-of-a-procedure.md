---
title: "Практическое руководство. Определение различных версий процедуры (Visual Basic) | Microsoft Docs"
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
  - "перегрузка процедур, несколько версий"
  - "процедуры, определение"
  - "процедуры, несколько версий"
  - "процедуры, перегрузка"
  - "код Visual Basic, процедуры"
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Определение различных версий процедуры (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Можно определить процедуру в нескольких версиях с помощью ее *перегрузки*, используя одно и то же имя, но разные списки параметров для каждой перегруженной версии.  Цель перегрузки заключается в том, чтобы определить несколько взаимосвязанных версий процедуры, не различая их по именам.  
  
 Дополнительные сведения см. в разделе [Перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
### Определение различных версий процедуры  
  
1.  Напишите оператор объявления `Sub` или `Function` для каждой версии процедуры, которую требуется определить.  Используйте одно и то же имя процедуры в каждом объявлении.  
  
2.  В каждом объявлении ключевому слову `Sub` или `Function` должно предшествовать ключевое слово [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md).  В объявлениях можно опускать `Overloads`, но если оно включено в одном из объявлений, то его необходимо включить во все объявления.  
  
3.  После каждого оператора объявления напишите код для обработки конкретных случаев, для которых код вызова предоставляет аргументы, соответствующие этому списку параметров данной версии процедуры.  Необязательно проверять, для каких параметров написан вызывающий код.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] передает управление соответствующей версии процедуры.  
  
4.  Завершайте каждую процедуру оператором `End Sub` или `End Function`.  
  
## Пример  
 В следующем примере определяется процедура `Sub` для учета транзакции по отношению к балансу клиента.  Используется ключевое слово `Overloads` для определения двух версий процедуры: первая процедура принимает клиента по имени, а другая — по номеру счета.  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Вызывающий код может получить идентификатор клиента как в качестве типа `String`, так и в качестве типа `Integer`, а затем использовать тот же вызывающий оператор в обоих случаях.  
  
 Сведения о том, как вызывать эти версии процедуры `post` см. в разделе [Практическое руководство. Вызов перегруженной процедуры](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md).  
  
## Компиляция кода  
 Убедитесь, что все перегруженные версии имеют одно и то же имя процедуры, но различные списки параметров.  
  
## См. также  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Устранение неполадок в процедурах](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Вопросы, связанные с перегрузкой процедур](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Разрешение перегрузки](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)