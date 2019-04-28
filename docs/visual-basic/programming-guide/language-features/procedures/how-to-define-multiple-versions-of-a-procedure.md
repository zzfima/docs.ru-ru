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
ms.openlocfilehash: fc7a8e18394b904f0c22a80f71dee091d4f786ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863835"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Практическое руководство. Определение различных версий процедуры (Visual Basic)
Можно определить процедуру в нескольких версиях, *перегрузка* его с помощью тем же именем, но другим списком параметров для каждой версии. Перегрузка предназначена для определения несколько взаимосвязанных версий процедуры без необходимости различать их по имени.  
  
 Дополнительные сведения см. в разделе [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Определение различных версий процедуры  
  
1. Запись `Sub` или `Function` оператор объявления для каждой версии процедуры, необходимо определить. Используйте то же имя процедуры в каждом объявлении.  
  
2. Перед `Sub` или `Function` ключевое слово в каждом объявлении [перегружает](../../../../visual-basic/language-reference/modifiers/overloads.md) ключевое слово. Можно опустить `Overloads` в объявлениях, но если оно включено в одном из объявлений, необходимо включить его в каждое объявление.  
  
3. После каждого оператора объявления писать код процедуры для обработки определенного случая, где вызывающий код предоставляет аргументы, соответствующие этой версии списка параметров. У вас нет для тестирования для каких параметров поставляет вызывающий код. Visual Basic передает управление соответствующей версии процедуры.  
  
4. Завершайте каждую процедуру с `End Sub` или `End Function` инструкцию соответствующим образом.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `Sub` процедуры для публикации транзакций с сальдо клиента. Она использует `Overloads` ключевое слово для определения двух версий процедуры, принимающую клиента по имени, а другая по номеру счета.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Вызывающий код может получить идентификатор клиента как `String` или `Integer`, а затем использовать тот же вызывающий оператор в любом случае.  
  
 Сведения о том, как вызывать эти версии `post` процедуры, см. в разделе [как: Вызов перегруженной процедуры](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что каждый перегруженные версии имеет то же имя процедуры, но другим списком параметров.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Разрешение перегрузки](./overload-resolution.md)
