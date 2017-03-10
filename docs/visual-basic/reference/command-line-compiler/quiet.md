---
title: "/quiet | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/quiet"
  - "quiet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/quiet - параметр компилятора [Visual Basic]"
  - "quiet - параметр компилятора [Visual Basic]"
  - "-quiet - параметр компилятора [Visual Basic]"
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /quiet
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает компилятору не выделять код, в котором обнаружены синтаксические ошибки или предупреждения.  
  
## Синтаксис  
  
```  
/quiet  
```  
  
## Заметки  
 По умолчанию параметр `/quiet` не действует.  Если компилятор сообщает об ошибках или предупреждениях, которые связаны с синтаксисом, он выводит и соответствующие строки кода.  Если приложение анализирует выходные данные компилятора, удобнее, когда компилятор выводит только результат диагностики.  
  
 В следующем примере `Module1` выводит информацию об ошибке, содержащую исходный код при компиляции без `/quiet`.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Результат  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 При компиляции с использованием `/quiet` компилятор выводит следующие данные.  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  Параметр `/quiet` недоступен из среды разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## Пример  
 Следующий код компилирует `T2.vb` и не отображает код для синтаксической диагностики компилятора.  
  
```  
vbc /quiet t2.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)