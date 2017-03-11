---
title: "/verbose | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/verbose - параметр компилятора [Visual Basic]"
  - "verbose - параметр компилятора [Visual Basic]"
  - "-verbose - параметр компилятора [Visual Basic]"
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /verbose
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает компилятору выводить подробные сообщения о состоянии и ошибках.  
  
## Синтаксис  
  
```  
/verbose[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Необязательный.  Задание параметра `/verbose` равносильно заданию `/verbose+`, который указывает компилятору выводить подробные сообщения.  Значением по умолчанию для этой опции является `/verbose-`.  
  
## Заметки  
 Опция `/verbose` отображает информацию обо всех ошибках, выдаваемых компилятором, сообщает сведения о сборках, загружаемых модулях, а также показывает компилируемые файлы.  
  
> [!NOTE]
>  Параметр `/verbose` недоступен из среды разработки Visual Studio. Он доступен только при выполнении компиляции из командной строки.  
  
## Пример  
 Следующий код компилирует `In.vb`, а компилятор отображает подробные сведения о состоянии.  
  
```  
vbc /verbose in.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)