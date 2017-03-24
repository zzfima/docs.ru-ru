---
title: "Для необязательных параметров должно быть задано значение по умолчанию | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30812"
  - "bc30812"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30812"
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Для необязательных параметров должно быть задано значение по умолчанию
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Для необязательных параметров должны быть заданы значения по умолчанию, которые будут использоваться при отсутствии параметра в вызывающей процедуре.  
  
 **Идентификатор ошибки:** BC30812  
  
### Чтобы исправить эту ошибку  
  
-   Для необязательных параметров укажите значение по умолчанию, например:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## См. также  
 [Optional](../../../visual-basic/language-reference/modifiers/optional.md)