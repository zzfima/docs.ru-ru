---
title: "Практическое руководство. Доступ к членам объекта (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 85fa4932b449bf7b9ecb3902fc17fd954ea8cfac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Практическое руководство. Доступ к членам объекта (Visual Basic)
При наличии объектную переменную, которая ссылается на объект, часто требуется работать с членами этого объекта, например методы, свойства, поля и события. Например, после создания нового <xref:System.Windows.Forms.Form> объекта, может потребоваться установить его <xref:System.Windows.Forms.Control.Text%2A> свойства или вызов его <xref:System.Windows.Forms.Control.Focus%2A> метод.  
  
## <a name="accessing-members"></a>Доступ к членам  
 Доступ к членам объекта осуществляется через переменную, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object"></a>Для доступа к членам объекта  
  
-   Используйте оператор доступа к членам (`.`) между именем переменной объекта и имя элемента.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Если член является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), переменная для доступа к нему не требуется.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Доступ к членам объекта известного типа  
 Если вы знаете тип объекта во время компиляции, можно использовать *раннее связывание* для переменной, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Для доступа к членам объекта, для которого тип известен во время компиляции  
  
1.  Объявите переменную объекта с типом объекта, который требуется присвоить переменной.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     С `Option Strict On`, можно назначить только <xref:System.Windows.Forms.Form> объектов (или объекты типа, производным от <xref:System.Windows.Forms.Form>) для `extraForm`. Если вы определили класс или структуру с помощью расширяющего `CType` преобразование <xref:System.Windows.Forms.Form>, можно также назначить класс или структуру для `extraForm`.  
  
2.  Используйте оператор доступа к членам (`.`) между именем переменной объекта и имя элемента.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Можно получить доступ ко всем методы и свойства, относящиеся к <xref:System.Windows.Forms.Form> класса, ни при каких обстоятельствах `Option Strict` параметр.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Доступ к членам объекта неизвестного типа.  
 Если вы не знаете тип объекта во время компиляции, необходимо использовать *позднего связывания* для любой переменной, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Для доступа к членам объекта, для которого вы не знаете тип во время компиляции  
  
1.  Объявите переменную объекта [тип данных объекта](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Объявление переменной как `Object` совпадает со значением его объявление как <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     С `Option Strict On`, доступны только члены, определенные на <xref:System.Object> класса.  
  
2.  Используйте оператор доступа к членам (`.`) между именем переменной объекта и имя элемента.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Чтобы иметь возможность доступа к членам объекта, можно присвоить переменной объекта, необходимо задать `Option Strict Off`. При этом компилятор не гарантирует, что и данный элемент предоставляется объекта, к которому можно присвоить переменной. Если объект не предоставляет член, при попытке получить доступ к, <xref:System.MemberAccessException> возникает исключение.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
