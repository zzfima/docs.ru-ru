---
title: Практическое руководство. Определение различных версий процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 83e96e271f6613aa325d59a0ca2fce9fc69fe059
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350490"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Практическое руководство. Определение различных версий процедуры (Visual Basic)
Вы можете определить процедуру в нескольких версиях, *перегружая* ее, используя одно и то же имя, но различные списки параметров для каждой версии. Целью перегрузки является определение нескольких тесно связанных версий процедуры без необходимости отличать их по имени.  
  
 Дополнительные сведения см. в разделе [Procedure Overloading](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Определение нескольких версий процедуры  
  
1. Напишите `Sub` или `Function` оператор объявления для каждой версии процедуры, которую необходимо определить. Используйте одно и то же имя процедуры в каждом объявлении.  
  
2. Перед ключевым словом `Sub` или `Function` в каждом объявлении с ключевым словом [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) . При необходимости можно опустить `Overloads` в объявлениях, но если включить его в любое из объявлений, необходимо включить его в каждое объявление.  
  
3. После каждого оператора объявления напишите код процедуры для обработки конкретного случая, когда вызывающий код предоставляет аргументы, соответствующие списку параметров этой версии. Нет необходимости проверять, какие параметры предоставил вызывающий код. Visual Basic передает управление соответствующей версии процедуры.  
  
4. Завершите каждую версию процедуры с помощью инструкции `End Sub` или `End Function`.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется процедура `Sub` для публикации транзакции по балансу клиента. В нем используется ключевое слово `Overloads` для определения двух версий процедуры, одна из которых принимает клиента по имени, а другая — по номеру счета.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 Вызывающий код может получить идентификатор клиента в виде `String` или `Integer`, а затем использовать тот же оператор вызова в обоих случаях.  
  
 Сведения о том, как вызывать эти версии `post` процедуры, см. [в разделе как вызвать перегруженную процедуру](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Убедитесь, что Каждая перегруженная версия имеет одно и то же имя процедуры, но другой список параметров.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Разрешение перегрузки](./overload-resolution.md)
