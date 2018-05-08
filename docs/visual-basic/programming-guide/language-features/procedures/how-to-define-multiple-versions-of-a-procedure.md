---
title: Практическое руководство. Определение различных версий процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a4d0c5bbb07dd5433ff62179fc10a6274bf19364
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Практическое руководство. Определение различных версий процедуры (Visual Basic)
Можно определить процедуру в нескольких версиях по *перегрузка* его, используя то же имя, но другим списком параметров для каждой версии. Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры, не различая их по имени.  
  
 Дополнительные сведения см. в разделе [перегрузка процедур](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Определение различных версий процедуры  
  
1.  Запись `Sub` или `Function` оператор объявления для каждой версии процедуры, необходимо определить. Используйте то же имя процедуры в каждом объявлении.  
  
2.  Перед `Sub` или `Function` ключевое слово в каждое объявление с [перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово. Можно опустить `Overloads` в объявлениях, но если оно включено в одном из объявлений, необходимо включить его в каждое объявление.  
  
3.  После каждого оператора объявления напишите код процедуры для обработки случая, когда вызывающий код предоставляет аргументы, соответствующие этой версии список параметров. У вас тестирование для параметров, который поставляет вызывающий код. Visual Basic передает управление соответствующей версии процедуры.  
  
4.  Завершайте каждую процедуру с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Sub` процедуры для публикации транзакций с сальдо клиента. Она использует `Overloads` ключевое слово для определения двух версий процедуры, принимающую клиента по имени, а другая — по номер счета.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем использовать тот же вызывающий оператор в любом случае.  
  
 Сведения о том, как вызывать эти версии `post` процедуры, в разделе [как: вызов процедуры перегружены](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что каждый перегруженные версии имеет то же имя процедуры, но с другим списком параметров.  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)  
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)  
 [Разрешение перегрузки](./overload-resolution.md)
