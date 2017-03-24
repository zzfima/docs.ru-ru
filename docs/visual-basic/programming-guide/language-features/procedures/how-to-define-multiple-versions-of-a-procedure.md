---
title: "Практическое руководство: определение различных версий процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0228083ce00a0f552227fd7ae8f0f5a24f65148e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Практическое руководство. Определение различных версий процедуры (Visual Basic)
Можно определить процедуру в нескольких версиях с *перегрузка* его, используя то же имя, но другой список параметров для каждой версии. Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры, не различая их по имени.  
  
 Дополнительные сведения см. в разделе [перегрузка процедур](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Определение различных версий процедуры  
  
1.  Запись `Sub` или `Function` оператор объявления для каждой версии процедуры, необходимо определить. Используйте то же имя процедуры в каждом объявлении.  
  
2.  Перед `Sub` или `Function` ключевое слово в каждом объявлении [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово. Можно опустить `Overloads` в объявлениях, но если оно включено в одном из объявлений, необходимо включить его в каждом объявлении.  
  
3.  После каждого оператора объявления напишите код процедуры для обработки определенного случая, когда вызывающий код предоставляет аргументы, соответствующие этой версии списка параметров. Не нужно проверить для каких параметров вызывающий код имеет указанный. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]передает управление соответствующей версии процедуры.  
  
4.  Завершайте каждую процедуру с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Sub` процедура проводки транзакции по балансу клиента. Он использует `Overloads` ключевое слово для определения двух версий процедуры, принимающую клиента по имени, а другая — по номеру счета.  
  
 [!code-vb[VbVbcnProcedures&#72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем использовать тот же вызывающий оператор в обоих случаях.  
  
 Сведения о том, как вызывать эти версии `post` процедура, в разделе [как: вызов процедуры перегруженные](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что каждый перегруженные версии имеет то же имя процедуры, но с другим списком параметров.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)   
 [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)   
 [Разрешение перегрузки](./overload-resolution.md)
