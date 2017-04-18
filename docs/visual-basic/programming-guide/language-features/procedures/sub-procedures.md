---
title: "Процедуры (Visual Basic) Sub | Документы Microsoft"
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
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: d224fa3338ca707070ee431380578a8fdde47e07
ms.lasthandoff: 03/13/2017

---
# <a name="sub-procedures-visual-basic"></a>Подпрограммы (Visual Basic)
Объект `Sub` процедура представляет собой ряд [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] операторы заключены в `Sub` и `End Sub` инструкции. `Sub` Процедура выполняет задачу и возвращает управление вызывающему коду, но не возвращает значения в вызывающий код.  
  
 При каждом вызове процедуры ее инструкции выполняются, начиная с первого исполняемого оператора после `Sub` инструкции и заканчивая первым `End Sub`, `Exit Sub`, или `Return` обнаружен оператор.  
  
 Можно определить `Sub` процедуру в модули, классы и структуры. По умолчанию является `Public`, означает, что можно вызывать из любого места в приложении, которое имеет доступ к модуля, класса или структуры, в котором она определена. Термин, *метод*, описание `Sub` или `Function` процедуры, к которому осуществляется из вне модуля, класса или структуры. Дополнительные сведения см. в разделе [процедуры](./index.md).  
  
 A `Sub` процедура может принимать аргументы, например константы, переменные или выражения, которые передаются ей вызывающим кодом.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Синтаксис объявления `Sub` используется следующая процедура:  
  
 `[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 `modifiers` Можно указать уровень доступа и сведения о перегрузке, переопределении, общем доступе и затенение. Дополнительные сведения см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Объявление параметра  
 Объявите каждый параметр процедуры аналогично как объявить переменную, указав параметр имя и тип данных. Можно также указать механизм передачи и параметр является необязательным или массивом параметров.  
  
 Синтаксис для каждого параметра в списке параметров выглядит следующим образом:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *имя_параметра*`As`*тип данных    *  
  
 Если аргумент является необязательным, необходимо также указать значение по умолчанию как часть его объявления. Синтаксис для указания значения по умолчанию выглядит следующим образом:  
  
 `Optional [ByVal | ByRef]`  *имя_параметра*`As`*datatype*`=`*defaultvalue        *  
  
### <a name="parameters-as-local-variables"></a>Параметры как локальные переменные  
 Когда управление передается в процедуру, каждый параметр рассматривается как локальная переменная. Это означает, что время существования совпадает, процедуры и ее область действия является вся процедура.  
  
## <a name="calling-syntax"></a>Синтаксис вызова  
 Вызвать `Sub` процедуру явным образом с помощью отдельного вызывающего оператора. Нельзя вызвать, указав ее имя в выражении. Необходимо указать значения для всех аргументов, которые не являются необязательными, и список аргументов должен быть заключен в круглые скобки. Если не указано никаких аргументов, скобки можно опустить. Использование `Call` ключевое слово, но это не рекомендуется.  
  
 Синтаксис для вызова `Sub` используется следующая процедура:  
  
 `[Call]`  *дополнительное_имя* `[(` *argumentlist*`)]`  
  
 Можно вызвать `Sub` методу извне определяющего его класса. Во-первых, необходимо использовать `New` ключевое слово для создания экземпляра класса, или вызвать метод, который возвращает экземпляр класса. Дополнительные сведения см. в разделе [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md). Затем можно использовать следующий синтаксис для вызова `Sub` метода для экземпляра объекта:  
  
 *Object*.* methodName*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Пример объявления и вызова  
 Следующие `Sub` процедура показывает оператору компьютера, какое задание приложение собирается выполнить, а также отображает отметку времени. Вместо дублирования этого кода в начале каждой задачи, приложение вызывает `tellOperator` из различных расположений. Каждый вызов передает строку в `task` , указывающий, запущенную задачу.  
  
 [!code-vb[VbVbcnProcedures&#2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 В следующем примере показано типичный вызов `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures&#3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Процедуры функций](./function-procedures.md)   
 [Процедуры свойств](./property-procedures.md)   
 [Процедуры операторов](./operator-procedures.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Практическое руководство: вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [Практическое руководство: вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)
