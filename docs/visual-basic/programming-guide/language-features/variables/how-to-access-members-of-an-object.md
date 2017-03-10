---
title: "Практическое руководство. Доступ к членам объекта (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "члены, доступ"
  - "объектные переменные, доступ к членам"
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Доступ к членам объекта (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Если имеется объектная переменная, которая ссылается на объект, часто требуется работать с членами этого объекта, например его методами, свойствами, полями и событиями.  Например, после создания нового объекта <xref:System.Windows.Forms.Form>, возможно, потребуется задать для него свойство <xref:System.Windows.Forms.Control.Text%2A> или вызвать его метод <xref:System.Windows.Forms.Control.Focus%2A>.  
  
## Доступ к членам  
 Доступ к членам объекта можно получить через переменную, которая ссылается на него.  
  
#### Чтобы получить доступ к членам объекта  
  
-   Используйте оператор доступа к членам \(`.`\) между именем переменной объекта и именем члена.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Если член является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), для доступа к нему переменная не требуется.  
  
## Доступ к членам объекта известного типа  
 Если во время компиляции известен тип объекта, можно использовать *раннее связывание* для переменной, которая ссылается на него.  
  
#### Доступ к членам объекта, тип которого известен во время компиляции  
  
1.  Объявите переменную объекта с типом объекта, который требуется присвоить переменной.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form   
    ```  
  
     С помощью команды `Option Strict On` можно назначить только объекты <xref:System.Windows.Forms.Form> \(или объекты типа, производного от <xref:System.Windows.Forms.Form>\) для `extraForm`.  Если класс или структура определены с помощью расширяющего преобразования `CType` в <xref:System.Windows.Forms.Form>, можно также назначить класс или структуру для `extraForm`.  
  
2.  Используйте оператор доступа к членам \(`.`\) между именем переменной объекта и именем члена.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Можно получить доступ ко всем методам и свойствам, характерным для класса <xref:System.Windows.Forms.Form>, независимо от параметра `Option Strict`.  
  
## Доступ к членам объекта неизвестного типа  
 Если тип объекта неизвестен во время компиляции, необходимо использовать *позднее связывание* для любой переменной, которая ссылается на него.  
  
#### Доступ к членам объекта, тип которого неизвестен во время компиляции  
  
1.  Объявите переменную объекта как [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).  Объявление переменной как `Object` совпадает с объявлением ее как <xref:System.Object?displayProperty=fullName>.  
  
    ```  
    Dim someControl As Object   
    ```  
  
     С помощью команды `Option Strict On` доступны только члены, определенные в классе <xref:System.Object>.  
  
2.  Используйте оператор доступа к членам \(`.`\) между именем переменной объекта и именем члена.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Чтобы иметь возможность доступа к членам из любого объекта, назначаемого переменной объекта, необходимо задать параметр `Option Strict Off`.  После этого компилятор не может гарантировать, что доступ к данному члену будет предоставляться с помощью объекта, назначаемого переменной.  Если объект не предоставляет член при попытке доступа, возникает исключение <xref:System.MemberAccessException>.  
  
## См. также  
 <xref:System.Object>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.MemberAccessException>   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)