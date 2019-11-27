---
title: Практическое руководство. Принудительная передача аргумента по значению
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 8261d126f988bdcf05b4a2af3106b38717e46bc8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344513"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Практическое руководство. Принудительная передача аргумента по значению (Visual Basic)
Объявление процедуры определяет механизм передачи. Если параметр объявлен как [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic предполагался передать соответствующий аргумент по ссылке. Это позволяет процедуре изменять значение программного элемента, лежащего в основе аргумента в вызывающем коде. Если вы хотите защитить базовый элемент от таких изменений, можно переопределить механизм передачи `ByRef` в вызове процедуры, заключив имя аргумента в круглые скобки. Эти скобки являются дополнением к круглым скобкам, включающим список аргументов в вызове.  
  
 Вызывающий код не может переопределить механизм [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) .  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Принудительная передача аргумента по значению  
  
- Если соответствующий параметр объявлен `ByVal` в процедуре, вам не нужно предпринимать никаких дополнительных действий. Visual Basic уже ждет передачи аргумента по значению.  
  
- Если соответствующий параметр объявлен `ByRef` в процедуре, заключите аргумент в круглые скобки в вызове процедуры.  
  
## <a name="example"></a>Пример  
 В следующем примере переопределяется объявление параметра `ByRef`. В вызове, который принудительно `ByVal`, обратите внимание на два уровня круглых скобок.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Если `str` заключаются в скобки в списке аргументов, процедура `setNewString` не может изменить ее значение в вызывающем коде, а `MsgBox` отображает "не может быть заменено, если передано ByVal". Если `str` не заключены в круглые скобки, процедура может изменить ее, а `MsgBox` выводит "это новое значение для аргумента строки".  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 При передаче переменной по ссылке необходимо использовать ключевое слово `ByRef` для указания этого механизма.  
  
 По умолчанию в Visual Basic передаются аргументы по значению. Однако рекомендуется включать ключевое слово [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) или [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) с каждым объявленным параметром. Это упрощает чтение кода.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если процедура объявляет параметр [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), правильное выполнение кода может зависеть от возможности изменения базового элемента в вызывающем коде. Если вызывающий код переопределяет этот механизм вызова, заключив аргумент в круглые скобки или передавая неизменяемый аргумент, процедура не может изменить базовый элемент. Это может привести к непредвиденным результатам в вызывающем коде.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Всегда существует потенциальный риск, позволяющий процедуре изменять значение, которое является базовым для аргумента в вызывающем коде. Убедитесь, что это значение было изменено, и будьте готовы проверить его на допустимость перед его использованием.  
  
## <a name="see-also"></a>См. также

- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Практическое руководство. Передача аргументов в процедуру](./how-to-pass-arguments-to-a-procedure.md)
- [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md)
- [Различия между изменяемыми и неизменяемыми аргументами](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Различия между передачей аргумента по значению и по ссылке](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Практическое руководство. Изменение значения аргумента процедуры](./how-to-change-the-value-of-a-procedure-argument.md)
- [Практическое руководство. Защита аргумента процедуры от изменений значения](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
