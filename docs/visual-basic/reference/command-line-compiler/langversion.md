---
title: "/langversion (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/langversion - параметр компилятора [Visual Basic]"
  - "langversion - параметр компилятора [Visual Basic]"
  - "-langversion - параметр компилятора [Visual Basic]"
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /langversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает компилятору принимать только синтаксис, входящий в заданную версию языка Visual Basic.  
  
## Синтаксис  
  
```  
/langversion:version  
```  
  
## Аргументы  
 `version`  
 Обязательный.  Версия языка, которая должна использоваться в процессе компиляции.  Допустимыми являются значения: `9`, `9.0`, `10` и `10.0`.  
  
## Заметки  
 Параметр `/langversion` служит для указания того, какой синтаксис принимает компилятор.  Например, если указать версию языка 9.0, компилятор будет создавать сообщения об ошибках для синтаксиса, применимого только в версии 10.0 или более поздней.  
  
 Этот параметр может применяться при разработке приложений, ориентированных на различные версии платформы .NET Framework.  Например, если создается приложение для платформы .NET Framework 3.5, этот параметр позволит гарантировать, что не будет использоваться синтаксис из версии языка 10.0.  
  
 Напрямую задать значение `/langversion` можно только с помощью командной строки.  Дополнительные сведения см. в разделе [Настройка конкретной версии платформы .NET Framework](/visual-studio/ide/targeting-a-specific-dotnet-framework-version).  
  
## Пример  
 Нижеприведенный код `sample.vb` компилируется для Visual Basic 9.0.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Настройка конкретной версии платформы .NET Framework](/visual-studio/ide/targeting-a-specific-dotnet-framework-version)