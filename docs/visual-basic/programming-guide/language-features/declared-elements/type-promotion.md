---
title: Повышение типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 02d53770186f7600b190231dc73938ff1589cef6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610360"
---
# <a name="type-promotion-visual-basic"></a>Повышение типа (Visual Basic)
При объявлении элемента программирования в модуле Visual Basic повышает уровень своей области, в пространство имен, содержащей модуль. Этот процесс называется *повышение типа*.  
  
 Следующий пример показывает определение схемы модуля и двух членов этого модуля.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 В рамках `projModule`программирования элементы, объявленные на уровне модуля повышаются до `projNamespace`. В приведенном выше примере `basicEnum` и `innerClass` повышаются, но `numberSub` — нет, поскольку он не объявлен на уровне модуля.  
  
## <a name="effect-of-type-promotion"></a>Эффект повышения типа  
 Повышение типа применяется что уточняющей строке не нужно включать имя модуля. Следующий пример делает два вызова процедуры в предыдущем примере.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 В предыдущем примере первый вызов используются полные квалификационные строки. Тем не менее это не необходимо из-за повышение типа. Второй вызов также доступ к членам модуля без включения `projModule` в строки квалификации.  
  
## <a name="defeat-of-type-promotion"></a>Отмена повышения типа  
 Если пространство имен уже содержит член с тем же именем члена модуля, повышение типа для члена модуля отменяется. Следующий пример показывает определение схемы перечисления и модуль в рамках одного пространства имен.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 В приведенном выше примере Visual Basic невозможно повысить уровень класс `abc` для `thisNameSpace` так, как перечисление с тем же именем на уровне пространства имен уже существует. Чтобы получить доступ к `abcSub`, необходимо использовать полной строки `thisNamespace.thisModule.abc.abcSub`. Тем не менее, класс `xyz` по-прежнему может повышаться, и вы можете получить доступ к `xyzSub` с более короткая строка квалификации `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Отмена повышения типа для разделяемых типов  
 Если класс или структуру в модуле, использует [частичного](../../../../visual-basic/language-reference/modifiers/partial.md) ключевое слово, повышение типа автоматически отменяется для этого класса или структуры, независимо от того, имеется ли пространство имен имеет член с тем же именем. Другие элементы в модуле, по-прежнему смогут воспользоваться повышение типа.  
  
 **Последствия.** Отмена повышения типа частичного определения может привести к непредсказуемым результатам и даже ошибкам компилятора. Следующий пример показывает скелет разделяемые определения класса, один из которых находится внутри модуля.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 В предыдущем примере разработчик может ожидать, что компилятор объединить два частичных определения из `sampleClass`. Однако компилятор не учитывает предложения в течение частичное определение внутри `sampleModule`. Таким образом, он попытается скомпилировать два отдельных и различных класса, и именованные `sampleClass` , но с другой квалификации пути.  
  
 Компилятор объединяет частичные определения, только если их полные пути идентичны.  
  
## <a name="recommendations"></a>Рекомендации  
 Следующие рекомендации представляют хорошим стилем программирования.  
  
- **Уникальные имена.** Если у вас есть полный контроль над именованием элементов программирования, рекомендуется всегда использовать уникальные имена везде. Одинаковые имена требуют дополнительного уточнения и делает код труднее читаться. Они также может привести к ошибкам и непредвиденным результатам.  
  
- **Полное имя пространства имен.** При работе с модулями и другие элементы в одном пространстве имен, безопаснее всегда используйте полное имя для всех элементов программирования. Если для члена модуля отменяется повышение типа и не полностью уточнить этот член, может случайно доступ к другому элементу программирования.  
  
## <a name="see-also"></a>См. также

- [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Оператор Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Практическое руководство. Управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
